# 001 - Estrutura do projecto do site

## Objectivo
Existe um projecto `site/` que gera o site público do Zytrus em ficheiros
estáticos, com o estilo aprovado e as regras de trabalho escritas.

Plano: `docs/00-visao-geral.md`.

## Passo-a-passo
1. Repositório git próprio em `site/`, com os ramos e as regras de
   versionamento dos outros dois repositórios (`dev`, `feature/NNN-slug`,
   Conventional Commits).
2. Next.js na mesma versão do `frontend/` (16.3.5), TypeScript, Tailwind,
   com `output: 'export'` e `trailingSlash: true` (cada página fica numa
   pasta com `index.html`, que o Apache serve sem regras extra).
3. Tokens do estilo aprovado em `globals.css` (`@theme`): cores, fonte
   Ubuntu via `next/font/google`, largura de 1200 px.
4. Variáveis de build: `NEXT_PUBLIC_APP_URL` (para "Entrar" e "Criar conta";
   em produção `https://zytrus-erp.kutomahosting.com/app`) e
   `NEXT_PUBLIC_API_URL` (`https://api.zytrus-erp.kutomahosting.com/api`).
5. Desenvolvimento local na porta 3001, para não chocar com o `frontend/`
   (3000).
6. `AGENTS.md` do site: sem dados inventados, caminhos reservados, só
   módulos em produção, textos em português de Moçambique, acessibilidade
   (contraste 4,5:1, navegação por teclado), tarefa antes de código.
7. Vitest + Testing Library para componentes; `next build` sem erros como
   verificação mínima de cada tarefa.

## Registo do que foi concluído
- 12/11/2026: repositório git criado em `site/` só com a documentação
  (`docs/00-visao-geral.md` e as tarefas `site/001`–`010`), com os ramos
  `main` e `dev`. Ainda sem remoto e sem projecto Next.js: o resto do
  passo 1 (regras de versionamento escritas) e os passos seguintes ficam
  por fazer. A tarefa continua aberta.
