@AGENTS.md

# app-agendamentos

## Sobre o projeto

Aplicação web de agendamento de horários, com funcionalidades de IA usando o Claude (API da Anthropic). As funcionalidades de IA ainda serão definidas.

## Stack

- Next.js com App Router, TypeScript, Tailwind CSS, ESLint
- Código-fonte em `src/`, alias de import `@/*`
- Gerenciador de pacotes: npm
- SDK: `@anthropic-ai/sdk` (já instalado)

## Regras de IA (Claude API)

- Ainda NÃO há chave de API. Não fazer chamadas reais à API.
- Toda funcionalidade de IA deve usar respostas simuladas (mock) até a chave existir, estruturadas para trocar o mock pela chamada real com mudança mínima.
- Chamadas ao Claude sempre no servidor (Route Handlers em `src/app/api/` ou Server Actions). Nunca no código do cliente.
- A chave fica em `ANTHROPIC_API_KEY` no `.env.local`. Nunca expor, logar ou comitar.
- Priorizar modelos menores e baratos (família Haiku) e prever limite de requisições por usuário.
- Enviar à IA apenas os dados pessoais estritamente necessários (LGPD).

## Fluxo Git

- Branches: `staging` (desenvolvimento) e `main` (produção).
- Todo trabalho e commit acontece na `staging`. Nunca comitar ou fazer push direto na `main`.
- O merge `staging` → `main` é feito por mim, via Pull Request no GitHub.
- Mensagens no padrão Conventional Commits (`feat:`, `fix:`, `chore:`, `refactor:`, `docs:`).
- Antes de comitar, conferir que `.env*` e `node_modules` não estão no staging do git.
- Mostrar o que será comitado e pedir confirmação antes de commit e push.

## Comunicação

- Responder em português.
- Ser objetivo, mas sempre sinalizar o que eu preciso saber: riscos, decisões com impacto futuro, custos e segurança.
