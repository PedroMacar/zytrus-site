# 002 - Cabeçalho com menus e rodapé

## Objectivo
Todas as páginas partilham o cabeçalho com menus em painel e o rodapé de
cinco colunas, como nos desenhos "Menu · Produto aberto", "Menu · Recursos
aberto" e "Início".

## Passo-a-passo
1. Um ficheiro único com a estrutura de navegação (menus, colunas, textos e
   destinos), usado pelo cabeçalho, pelo rodapé e pelo `sitemap.xml`.
2. Cabeçalho: Produto, Integrações, Preços, Recursos, Empresa; à direita
   "Entrar" (`NEXT_PUBLIC_APP_URL` + `/login`) e "Falar connosco".
3. Painéis de Produto, Recursos e Empresa: abrem com clique e com teclado
   (Enter, Espaço, Escape fecha, Tab percorre), `aria-expanded` no botão,
   fecham ao clicar fora. Sem abrir só com o rato por cima.
4. Telemóvel: botão de menu que abre a navegação em lista, com as secções
   a expandir.
5. Rodapé: marca e contactos, colunas Produto, Plataforma, Recursos e
   Empresa, linha final com direitos, Termos e Privacidade.
6. Uma ligação só aparece quando a página de destino existe.
7. Testes: abrir e fechar por teclado; ligações do rodapé geradas a partir
   da estrutura de navegação.

## Registo do que foi concluído
_(por preencher)_
