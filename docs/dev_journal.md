# Dev Journal

Registro breve das mudanças significativas do projeto. Entrada mais recente no topo.

Formato: `## AAAA-MM-DD — título curto` seguido de bullets do que mudou e por quê.

---

## 2026-06-15 — `subject` definido como regra oficial

- Decisão: **`subject_*.md` é a regra do projeto**; `avaliacao_*.md` está obsoleto (template antigo do Pong) e não vale como requisito. Resolve a pendência bloqueante.
- `CLAUDE.md` atualizado: stack deixa de ser "obrigatória pelos avaliadores" e passa a ser "escolhida pelo time" (NestJS + Prisma + PostgreSQL + React/Vite/Tailwind).

---

## 2026-06-15 — Definição do produto e plano ágil

- Produto escolhido: **rede social de avaliação de pessoas e empresas** (notas 0–10, feed, DM, busca, estabelecimentos com preferências de cliente).
- Combinação de **15 pontos** definida (login só email+senha; empresas como módulo Organizações; GDPR/LGPD).
- Criado `docs/plano_agil.md` com stack, schema resumido e backlog Epic → Feature → Story → Task.
- Pendência bloqueante registrada: confirmar com o staff se vale `subject` novo ou `avaliacao` antigo.

---

## 2026-06-15 — Setup inicial da documentação

- Criado o `CLAUDE.md` local com preferências, stack obrigatória (NestJS + PostgreSQL + frontend TS), checklist de requisitos de defesa, módulos e workflow de git.
- Registrada a preferência de focar a pontuação na categoria de módulos **Web** (subject IV.1).
- Criado este `dev_journal.md` para registrar mudanças significativas.
