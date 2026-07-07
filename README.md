# Code Connect

Workspace monorepo usando **pnpm workspaces**, com dois projetos independentes que compartilham as mesmas dependências instaladas na raiz.

## Estrutura

\\\
code-connect/
├── apps/
│   ├── web/    → Frontend em React, criado com Vite
│   └── api/    → Backend em NestJS
├── package.json          → scripts (atalhos) para rodar cada app
├── pnpm-workspace.yaml   → declara quais pastas fazem parte do workspace
└── pnpm-lock.yaml        → lockfile único, compartilhado entre os dois apps
\\\

## Por que um workspace?

Em vez de ter dois projetos separados, cada um com seu próprio \
ode_modules\, o pnpm centraliza tudo num só lugar na raiz. Isso economiza espaço em disco e facilita rodar comandos sem precisar navegar entre pastas.

## Pré-requisitos

- Node.js 22+
- pnpm (\
pm install -g pnpm\)

## Como rodar

Instale as dependências uma única vez, na raiz:

\\\ash
pnpm install
\\\

Depois, use os atalhos definidos no \package.json\ da raiz:

\\\ash
# Frontend (React) — http://localhost:5173
pnpm web:dev

# Backend (NestJS) — http://localhost:3000
pnpm api:dev
\\\

Cada comando precisa ser rodado em um terminal separado, já que ambos ficam escutando por mudanças.

## Scripts disponíveis

| Comando | O que faz |
|---|---|
| \pnpm web:dev\ | Sobe o frontend em modo desenvolvimento |
| \pnpm web:build\ | Gera o build de produção do frontend |
| \pnpm api:dev\ | Sobe o backend em modo desenvolvimento (watch) |
| \pnpm api:build\ | Compila o backend para produção |
