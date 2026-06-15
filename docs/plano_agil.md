# Plano ágil — Rede social de avaliação (Transcendence)

## Descrição

Rede social de **avaliação de pessoas e empresas**. Pessoas recebem notas 0–10 por categoria (personalidade, aparência, estilo…), com média geral e nº de avaliações; têm feed estilo Twitter, DM e busca com filtros. Empresas se cadastram como estabelecimentos (módulo Organizações), recebem notas com fotos e definem preferências de cliente. App gratuito, sem planos pagos.

**Decisões fechadas:** escopo enxuto (~15 pts) · empresas = módulo Organizações · GDPR/LGPD · login só email+senha (sem OAuth/2FA).

---

## ⚠️ Riscos a resolver ANTES de codar

1. **Conflito subject × avaliação.** `subject_*.md` = versão nova (app livre, 14 pts, módulos). `avaliacao_*.md` = parece template antigo (Pong, OAuth 42, 2FA, canais), de onde veio a stack NestJS+PostgreSQL. **Confirmar com o staff qual avaliação vale.** Este plano segue o subject novo + stack NestJS/Postgres (atende ambos).
2. **Risco ético/legal (LGPD/GDPR).** Avaliar pessoas sem consentimento é dado sensível. Mitigações no E8: só avalia quem tem conta e aceitou os Termos, direito de resposta, bloqueio, denúncia + moderação admin, rate limiting, GDPR export/delete. Vira ponto a favor (Privacy/Terms são obrigatórios e checados).

---

## Combinação de módulos — 15 pontos (Maior=2 / Menor=1)

| # | Categoria | Módulo | Tipo | Pts |
|---|---|---|---|---|
| 1 | Web | Framework front **e** back (NestJS + React) | Maior | 2 |
| 2 | Web | Tempo real com WebSockets (chat + feed + notificações) | Maior | 2 |
| 3 | Web | Interação entre usuários (chat básico + perfil + amigos) | Maior | 2 |
| 4 | Web | ORM (Prisma) | Menor | 1 |
| 5 | Web | Busca avançada (filtros + ordenação + paginação) | Menor | 1 |
| 6 | Web | Upload e gerenciamento de arquivos (fotos, avatares) | Menor | 1 |
| 7 | Web | Notificações para create/update/delete | Menor | 1 |
| 8 | Gerenciamento de usuários | Gerenciamento padrão (perfil, avatar, amigos, status online) | Maior | 2 |
| 9 | Gerenciamento de usuários | Sistema de organizações (empresas/estabelecimentos) | Maior | 2 |
| 10 | Dados e análise | GDPR/LGPD (exportar/excluir dados) | Menor | 1 |
| | | **TOTAL** | | **15** |

**Riscos de pontuação:**
- Módulos **3** e **8** se sobrepõem. Na defesa, deixar nítido: **8** = perfil editável + avatar default + amigos + status online; **3** = chat real + ver perfil de terceiros + bloqueio. A margem de 1 ponto (15 vs 14) cobre caso um seja contestado.
- Módulo **9** exige **multiusuário dentro da org** (adicionar/remover membros, papéis) — precisa de tela de gestão de membros, senão não valida.

---

## Stack técnica

- **Backend:** NestJS (TS) modular, REST + 1 WebSocket Gateway (socket.io). `class-validator`/DTO + `ValidationPipe` global. `helmet`, `@nestjs/throttler`, `argon2`. JWT (access em memória + refresh em cookie httpOnly+Secure).
- **ORM:** Prisma. **Banco:** PostgreSQL (`citext`, `pg_trgm`).
- **Frontend:** React + Vite + TS + Tailwind. React Router (Voltar/Avançar nativos). TanStack Query + Zustand. Formulários react-hook-form + zod.
- **Infra:** Docker Compose na raiz (Nginx TLS + NestJS + Postgres + frontend), `docker-compose up --build`. WS sobre `wss://`. `.env` (gitignored) + `.env.example`.

### Schema (resumo — fonte da verdade em `backend/prisma/schema.prisma`)
- `users` (single-table, `account_type PERSON|COMPANY`, `is_admin`, status online) + `person_profiles` / `company_profiles` (1:1).
- Avaliação: `rating_categories` (scope PERSON/ESTABLISHMENT) → `rating_items`; `person_reviews` + `person_review_scores`; `establishment_reviews` + `establishment_review_scores` + `establishment_review_photos`. **`UNIQUE(rater_id, ratee_id)`** (1 avaliação/par, base anti-race via upsert).
- **Médias materializadas** (`avg_overall`, `ratings_count`) recalculadas por **trigger** em `*_review_scores`.
- Organizações: `establishments` + `establishment_members` (OWNER/MANAGER/STAFF) + `client_preferences` (`min/max_client_score`).
- Social: `friendships`, `posts` (keyset pagination), `conversations`+`messages`, `blocks`, `notifications` (jsonb), `files`, `gdpr_requests`.
- **Regra "teto ≤ média do estabelecimento":** validação no service **+ trigger**. Quando a média cai, rebaixar `max_client_score` ao novo teto e notificar a empresa.

---

## Plano ágil: Epic → Feature → Story → Task

> Personas: **Pessoa** (PERSON), **Empresa** (COMPANY), **Admin** (moderação), **Dev**.

### E0 — Fundação & DevOps · destrava #1, #4
**F0.1 Containerização (1 comando)**
- Story: *Como Dev, quero subir o stack com `docker-compose up --build`.*
  - T: `docker-compose.yml` na raiz (nginx-tls, backend, frontend, postgres, volumes).
  - T: Nginx reverse proxy TLS (cert autoassinado dev) → HTTPS/WSS.
  - T: `.env.example` + `.env` no `.gitignore`; segredos fora do git.
**F0.2 Scaffold backend** — NestJS + Prisma + Postgres; `main.ts` (helmet, ValidationPipe, CORS, throttler); `PrismaService`; migration inicial.
**F0.3 Scaffold frontend** — React+Vite+TS+Tailwind; React Router (rotas públicas×privadas); cliente API tipado; ESLint `--max-warnings 0`.
**F0.4 CI básico** — lint + build no GitHub Actions; bloquear merge com warning.

### E1 — Autenticação & Contas (login duplo) · base de #8
**F1.1 Cadastro/login email+senha**
- Story: *Como visitante, quero criar conta Pessoa OU Empresa e logar com segurança.*
  - T: DTOs + validação (email, força de senha); hash `argon2`.
  - T: `POST /auth/register/person`, `/register/company`, `/login`, `/refresh`, `/logout`; JWT access+refresh (cookie httpOnly+Secure).
  - T: `JwtAuthGuard`, `RolesGuard` (PERSON/COMPANY/ADMIN); `WsJwtGuard`.
**F1.2 Onboarding 1º login** — apelido único + avatar (default se vazio).
**F1.3 Sessão no front** — Zustand + interceptor de refresh em 401; `<RequireAuth>` por role.

### E2 — Avaliação de Pessoas (núcleo) · reforça #3/#8
**F2.1 Categorias & itens** — seed `rating_categories`(PERSON) + `rating_items`; endpoint de leitura.
**F2.2 Perfil de pessoa**
- Story: *Como Pessoa, quero ver meu perfil com notas por categoria, média geral e nº de avaliações.*
  - T: `GET /users/:id` agregando scores por categoria; exibir médias materializadas.
  - T: tela de perfil (privado editável / público read-only).
**F2.3 Avaliar uma pessoa**
- Story: *Como Pessoa, quero dar notas 0–10 por item + comentário a outra pessoa.*
  - T: `POST /ratings/person/:id` com **upsert** (`ON CONFLICT (rater_id,ratee_id)`); validação `@Min(0)@Max(10)`.
  - T: trigger SQL de recálculo de média (anti-race).
  - T: gera notificação `NEW_REVIEW` (E7).

### E3 — Empresas (Organizações) & Avaliação de Estabelecimentos · #9, #6
**F3.1 Organização + membros**
- Story: *Como Empresa, quero criar/editar/excluir estabelecimentos e gerir membros (OWNER/MANAGER/STAFF).*
  - T: CRUD `establishments`; CRUD `establishment_members` (adicionar/remover usuário) — **requisito do módulo 9**.
  - T: guard de papel na org (`@EstablishmentRole`).
**F3.2 Avaliar estabelecimento com fotos**
- Story: *Como Pessoa, quero avaliar um estabelecimento com nota e fotos.*
  - T: `FilesModule` (upload multipart, validação tipo/tamanho, storage em volume, `DELETE`); avatares + `establishment_review_photos`.
  - T: `POST /ratings/establishment/:id` (upsert + trigger de média + fotos).
**F3.3 Preferências de cliente**
- Story: *Como Empresa, quero definir faixa de nota de cliente, sem exigir mais que minha própria média.*
  - T: `PATCH /establishments/:id/preferences` validando `max ≤ avg_overall` (service **+ trigger**).
  - T: política de rebaixar `max` + notificar quando a média cair.
**F3.4 Selo de compatibilidade (extra)** — badge "elegível / não elegível" comparando média da Pessoa logada com a faixa.

### E4 — Social: Amizades & Feed · #8, #3
**F4.1 Amizades + status online**
- Story: *Como Pessoa, quero adicionar/remover amigos e ver quem está online.*
  - T: `friendships` (request/accept/remove), aresta única; presença via gateway (E5).
**F4.2 Feed estilo Twitter**
- Story: *Como Pessoa, quero um feed com posts dos meus amigos.*
  - T: `POST /posts`; `GET /feed` keyset pagination; fan-out on write → `feed:new` p/ amigos (E5).

### E5 — Chat / DM em tempo real (WebSockets) · #2, #3
**F5.1 Gateway WS único** — `EventsGateway` (`/ws`), `WsJwtGuard`, rooms `user:{id}`/`feed:{id}`; presença no connect/disconnect.
**F5.2 DM 1:1**
- Story: *Como Pessoa, quero conversar por DM em tempo real, respeitando bloqueios.*
  - T: `conversations`+`messages`; histórico (REST) + `dm:send`/`dm:new` (WS).
  - T: ocultar mensagens de bloqueados; extra: `dm:typing` + `read_at`.

### E6 — Busca & Descoberta · #5
**F6.1 Busca com filtros**
- Story: *Como Pessoa, quero buscar pessoas/empresas com filtros de nota, tipo e ordenação, paginado.*
  - T: `GET /search?type=&q=&minScore=&maxScore=&sort=&page=`; `ILIKE`+`pg_trgm`; filtro por faixa via índice em `avg_overall`; paginação.

### E7 — Notificações · #7
**F7.1 Sistema de notificações**
- Story: *Como Pessoa/Empresa, quero ser notificado de nova avaliação, amigo, DM e post.*
  - T: `notifications` CRUD; push em tempo real `notification:new` (WS); badge no front.

### E8 — Privacidade, Compliance & Confiança · #10 + mitigação ética
**F8.1 Privacy & Terms** — páginas com **conteúdo real**, link no rodapé. *Obrigatório — ausência = rejeição.*
**F8.2 GDPR/LGPD**
- Story: *Como usuário, quero exportar e excluir meus dados.*
  - T: `GET /gdpr/export` (JSON); `DELETE /gdpr/account` (soft delete + purge); `gdpr_requests` auditoria.
**F8.3 Moderação & segurança** (não-módulo) — bloqueio, **denúncia** (`reported` + admin remove), rate limiting, sanitização XSS, **direito de resposta** a avaliações (`review_replies`).

### E9 — UX, Acessibilidade & Entrega final
**F9.1 Responsivo + design consistente** — footer com links legais.
**F9.2 Validação no front** — todos os formulários (zod) + erros inline.
**F9.3 Hardening de defesa** — **console zero erros/warnings**, Voltar/Avançar, multiusuário sem race, sem 500/crash.
**F9.4 README completo** — equipe+funções, gestão do projeto, stack justificada, schema, features com autor, módulos com pontos, contribuições individuais, 1ª linha em itálico, uso de IA.

---

## Sequenciamento (dependências)
**E0 → E1** destravam tudo. Depois, em paralelo: **E2** e **E3** | **E5** habilita **E4** e **E7** | **E6** e **E8** após dados | **E9** transversal. Divisão p/ time de 4–5: (a) Infra/Auth, (b) Avaliação Pessoa+Empresa, (c) Social+Chat+Notif, (d) Busca+GDPR+UX/README.

## Verificação (end-to-end)
- **Subir:** `docker-compose up --build` → app em `https://localhost` sem erro.
- **Smoke (Chrome, console aberto — deve ficar limpo):** cadastrar Pessoa + Empresa → avaliar pessoa e estabelecimento (com foto) → médias atualizam → criar post e ver no feed → DM em 2 abas (tempo real) → buscar com filtro de nota → notificações → exportar/excluir dados (GDPR) → Privacy/Terms pelo rodapé → Voltar/Avançar.
- **Concorrência:** 2 avaliações simultâneas do mesmo par → 1 registro (upsert) e média correta.
- **Regra de negócio:** empresa média 7 tentando `max_client_score=8` → rejeitado (400 + trigger).
- **Automatizado:** unit (rating/preferências), e2e Nest (auth, ratings, search); `eslint --max-warnings 0` no CI.

## Pendências para o time decidir
1. Confirmar **qual avaliação vale** (subject novo × avaliacao antigo) — bloqueante.
2. Framework front definitivo (React recomendado) e ORM (Prisma recomendado).
3. Política exata quando a média da empresa cai abaixo do `max_client_score` já definido.
