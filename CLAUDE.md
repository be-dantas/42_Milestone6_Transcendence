# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

> Este é o **Transcendence**, projeto final do Common Core da 42 (em grupo, 4-5 pessoas): uma aplicação web "do mundo real". Este `CLAUDE.md` é o guia local do projeto e tem prioridade sobre o `CLAUDE.md` da home ao trabalhar aqui.

## Como responder (preferências fixas)

- **Sempre em português pt-br.**
- Linguagem prática, direta, sem encheção de saco. Use emojis. 🚀
- **Nada de placeholders, TODOs ou código incompleto sem avisar claramente.** Se algo ficar pela metade, diga explicitamente.
- Priorize soluções **simples, robustas, legíveis e prontas para rodar**.
- Aponte explicitamente erros, problemas de arquitetura, segurança, performance ou más decisões técnicas — **mesmo que ela queira seguir assim**. Explique riscos e trade-offs, mas continue ajudando.
- **Sempre inclua como testar** o que foi feito.
- **Não remova funcionalidades existentes sem avisar.**
- Ao escrever código, **preserve o padrão existente do projeto**.
- Identidade git: `be-dantas` — commits saem como `be-dantas <226878089+be-dantas@users.noreply.github.com>`. Remote: `git@github.com:be-dantas/42_Milestone6_Transcendence.git`.

## Workflow de git (commits ao finalizar tarefa)

- **Sempre que finalizar uma tarefa**, rode: `git add .` → `git commit` → `git push` na branch **`BIA`** (criar/trocar para ela se não estiver nela; push para `origin BIA`).
- Mensagens no padrão **Conventional Commits**: `tipo(escopo opcional): descrição` — ex.: `feat:`, `fix:`, `docs:`, `chore:`, `refactor:`, `test:`, `style:`, `perf:`, `build:`, `ci:`.
- **NÃO** incluir nenhuma menção de que o Claude/Claude Code fez o commit (sem `Co-Authored-By`, sem "Generated with Claude" etc.). Commits saem como `be-dantas`.
- **Sempre que fizer alterações significativas no projeto, documente brevemente as mudanças em `docs/dev_journal.md`** (entrada mais recente no topo, com data).

## Específico deste projeto

- **Este NÃO é um projeto da norma norminette.** Esqueça norminette/header 42 aqui — vale o padrão de código do framework escolhido (lint/format de TS/NestJS).
- **A regra oficial do projeto é o `docs/subject_pt.md` / `docs/subject_en.md`** (versão nova: aplicação web livre, 14 pontos, módulos). Sempre que houver dúvida sobre o que fazer ou se algo é permitido, consulte o subject.
- **⚠️ `docs/avaliacao_pt.md` / `docs/avaliacao_en.md` estão OBSOLETOS** — são o template antigo do Transcendence (Pong, OAuth 42, 2FA, canais de chat) e **não valem** como regra. Não use para decidir requisitos. Mantidos só por referência histórica.

## Estado atual

- **Só documentação — ainda sem código.** Há `docs/` e um `README.md` de uma linha. Quando o código começar, atualize a seção "Comandos" abaixo com os comandos reais de build/lint/test do framework escolhido.

## Stack escolhida pelo time

Pelo subject a stack é **livre** (basta um framework no front e um no back + um banco). O time escolheu:

- **Backend: NestJS** (framework TypeScript) + **Prisma** (ORM).
- **Banco: PostgreSQL.**
- **Frontend: React + Vite + TypeScript + Tailwind.**
- **Deploy: Docker Compose na raiz do repo, subindo com um único comando** (exigência do subject: conteinerização rodando com 1 comando).

Detalhes de arquitetura, schema e backlog em `docs/plano_agil.md`.

## Comandos

- **Subir tudo:** `docker-compose up --build` — o `docker-compose.yml` **deve** ficar na raiz do repositório.
- Build / lint / testes por serviço (frontend, backend): **a definir quando a stack for scaffoldada.** Preencher aqui assim que existir `package.json`/scripts (ex.: `npm run lint`, `npm test`, rodar um teste único com `npm test -- <arquivo>`).

## Requisitos obrigatórios que NÃO podem falhar (checklist de defesa)

Tirados do subject. Qualquer um destes quebrado pode zerar/rejeitar o projeto:

- **Console do navegador limpo:** zero erros ou warnings não tratados, em toda a navegação.
- **HTTPS em todo o backend.**
- **Validação/sanitização de TODA entrada de usuário no front E no back** (o subject exige validação nas duas pontas).
- **Senhas com hash + salt** no banco. Sem credenciais/API keys no Git — tudo em `.env` (gitignored) com um `.env.example` versionado.
- **SPA:** botões Voltar/Avançar do navegador devem funcionar.
- **Multiusuário simultâneo** sem corrupção de dados nem race conditions; atualizações em tempo real refletidas para todos quando aplicável.
- **Páginas de Política de Privacidade e Termos de Serviço** acessíveis (ex.: rodapé) e com conteúdo real — não placeholder. Ausência = rejeição.
- **Compatível com a última versão estável do Chrome.**
- **Git:** commits de todos os membros, mensagens claras, trabalho bem distribuído.
- **Sem segfault/crash/erro 500** durante a defesa.

## Módulos e pontuação

- Meta: **≥ 14 pontos** (Maior = 2pts, Menor = 1pt). Mirar acima de 14 é recomendado (margem se algum módulo não validar).
- **Só conta módulo 100% funcional e demonstrável.** Incompleto = 0.
- Há dependências entre módulos (ex.: torneio/IA/espectador exigem um jogo implementado primeiro; chat avançado exige chat básico). Confira as notas no subject antes de declarar um módulo.

### Preferência da Beatriz: foco na categoria Web (subject IV.1)

A preferência é concentrar a pontuação na categoria **Web**. Módulos disponíveis nela (ainda a confirmar com o time):

- **Maiores (2pts):** framework front + back · tempo real com WebSockets · interação entre usuários (chat básico + perfil + amigos) · API pública (key segura, rate limiting, docs, ≥5 endpoints CRUD).
- **Menores (1pt):** framework frontend · framework backend · ORM · notificações para todo create/update/delete · colaboração em tempo real · SSR · PWA · design system (≥10 componentes reutilizáveis) · busca avançada (filtros/ordenação/paginação) · upload e gerenciamento de arquivos.

Como o backend NestJS + frontend TS já são obrigatórios, o módulo Maior "framework front + back" (2pts) basicamente já vem de graça. Dá pra fechar os 14 pontos sem depender de implementar um jogo — mas confirme as combinações com o time e veja se vale puxar pontos de outras categorias (ex.: Gerenciamento de usuários, Cibersegurança) para ter margem.

## README do projeto (parte avaliada)

O `README.md` atual é só o título — **precisa ser construído**. O subject (seção "Requisitos do README") exige, além do básico (Descrição, Instruções com `.env`, Recursos):
- **Informações da equipe** com funções (PO, PM/Scrum, Tech Lead, Devs) e responsabilidades.
- **Gerenciamento do projeto** (organização, ferramentas, canais de comunicação).
- **Pilha técnica** com justificativa das escolhas.
- **Esquema do banco** (tabelas, relações, campos).
- **Lista de funcionalidades** e **módulos** (com cálculo de pontos), cada um atribuído a quem implementou.
- **Contribuições individuais** por membro.
- Primeira linha em itálico: _Este projeto foi criado como parte do currículo da 42 por login1, login2..._
- Descrição de **como a IA foi usada** (quais tarefas/partes).
