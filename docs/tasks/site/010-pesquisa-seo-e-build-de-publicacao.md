# 010 - Pesquisa, SEO e build de publicação

## Objectivo
O site encontra-se nos motores de busca, tem pesquisa nos recursos e
publica-se com um comando.

Depende de: backend `nucleo/071` (proxy por caminho no servidor).

## Passo-a-passo
1. Título e descrição por página, Open Graph, `sitemap.xml` e `robots.txt`
   gerados no build. O `robots.txt` exclui `/app`, `/admin` e
   `/app-static`.
2. Página 404 própria.
3. Favicon e ícones a partir do `favicon.svg` do `frontend/`.
4. Pesquisa nos recursos (blog, guias, perguntas) com índice gerado no
   build e procura no browser.
5. Script de publicação: `next build` e envio da pasta `out/` por rsync
   para a pasta pública do domínio, sem apagar o `.htaccess` dos
   redireccionamentos (`nucleo/071`).
6. Passos de publicação do site acrescentados a
   `backend/docs/deploy/PROCESSO-DEPLOY.md`.

## Registo do que foi concluído
_(por preencher)_
