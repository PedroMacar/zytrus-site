# Site público do Zytrus - visão geral e plano

Decidido com o Pedro a 11/11/2026. Até aqui o Zytrus não tinha site: o
cliente entrava em contacto e recebia links.

## Endereços

| Endereço | O que é | Quem serve |
|---|---|---|
| `zytrus-erp.kutomahosting.com/` | Site público | Este projecto (`site/`), ficheiros estáticos |
| `zytrus-erp.kutomahosting.com/app` | Aplicação do cliente e autenticação | `frontend/` (Next.js, porta 3000) |
| `zytrus-erp.kutomahosting.com/admin` | Backoffice (não muda) | `frontend/` (Next.js, porta 3000) |
| `zytrus-erp.kutomahosting.com/app-static` | Ficheiros estáticos do `frontend/` | `frontend/` (Next.js, porta 3000) |
| `api.zytrus-erp.kutomahosting.com` | API (não muda) | `backend/` |

O domínio é o mesmo, por isso `SESSION_DOMAIN`, `SANCTUM_STATEFUL_DOMAINS` e
`FRONTEND_URLS` não mudam.

## Decisões

- Projecto separado do `frontend/`, na pasta `site/`, com repositório próprio.
- Exportação estática (`output: 'export'`): o build gera HTML e o Apache
  serve-o directamente. Sem segundo processo Node e sem watchdog.
- Blog e guias em ficheiros MDX no repositório. Sem painel de edição por
  agora.
- O login fica em `/app/login`, para clientes e para o backoffice.
- O `frontend/` não usa `basePath` (prefixaria também o backoffice, que
  passaria a `/app/admin`). As rotas do cliente movem-se para dentro de
  `src/app/app/`, o prefixo é aplicado nos pontos de passagem de
  `src/lib/routing/` (os caminhos no código ficam sem prefixo) e usa-se `assetPrefix: '/app-static'` para os ficheiros
  estáticos dos dois projectos não colidirem em `/_next`.
- Interface: direcção C ("Feito para Moçambique"), aprovada a 11/11/2026.
  Desenhos em https://claude.ai/artifact/QUhCMhHmpCnCCRYsMwsVtQ (página
  "Site corporativo").

## Estilo aprovado

- Fonte: Ubuntu (300, 400, 500, 700).
- Fundo escuro `#0c1f2b` (cabeçalho, topo das páginas, rodapé); acento
  `#32f08c` (o verde do favicon); texto sobre escuro `#ffffff`, `#dbe6ec` e
  `#b9cbd6`.
- Secções claras: branco e `#f3f7fa`; títulos `#14303f`; texto `#355164`;
  ligações e botões em fundo claro `#0865a7`; linhas `#cfd8de` e `#dfe6eb`.
- Largura do conteúdo: 1200 px. Botões e alvos de toque com 44 px ou mais.
- Sem dados inventados: o que não existe fica por publicar (ver "Conteúdo
  por fornecer").

## Mapa do site

| Menu | Páginas |
|---|---|
| Produto | Visão geral; Facturação; Cotações; Compras; Produtos e inventário; Contabilidade; Modelos de documentos; Várias moedas; Perfis e permissões; Novidades da versão |
| Integrações | Página única |
| Preços | Página única |
| Recursos | Blog; Guias de utilização; Perguntas frequentes; Novidades da versão; Documentação da API; Comunidade |
| Empresa | Sobre nós; Clientes; Contacto |
| À direita | Entrar (`/app/login`); Falar connosco |
| Rodapé | Tudo o que está acima em cinco colunas, contactos, Termos de utilização, Política de privacidade |

Só entram módulos com código: Facturação, Cotações, Compras, Produtos e
inventário, Contabilidade. Contratos e Recursos Humanos aparecem quando
estiverem em produção.

## Caminhos reservados

O site nunca cria páginas com estes nomes, porque pertencem ao `frontend/`
ou são endereços antigos redireccionados para `/app/...`:

`app`, `admin`, `app-static`, `login`, `register`, `forgot-password`,
`reset-password`, `password`, `convite`, `invites`, `email`, `verify-email`,
`dashboard`, `account`, `billing`, `importacao`, `partners`,
`product-service`, `profile`, `purchasing`, `quotation`, `settings`,
`users`, `lab`.

## Tarefas e ordem

A mudança de endereços vem primeiro, porque o site só pode ocupar a raiz
depois de a aplicação sair de lá.

| Ordem | Tarefa | Repositório |
|---|---|---|
| 1 | `integracao/102` - navegação interna pelos pontos de passagem (feita a 11/11/2026, por commitar) | frontend |
| 2 | `nucleo/069` - links dos emails com o caminho da aplicação | backend |
| 3 | `integracao/103` - aplicação do cliente em `/app` | frontend |
| 4 | `integracao/104` - ficheiros estáticos em `/app-static` | frontend |
| 5 | `site/001` - estrutura do projecto | site |
| 6 | `site/002` - cabeçalho com menus e rodapé | site |
| 7 | `site/003` - página inicial | site |
| 8 | `site/004` - páginas de produto e de módulo | site |
| 9 | `site/005` - preços | site |
| 10 | `site/006` - integrações | site |
| 11 | `site/007` - recursos, blog e guias | site |
| 12 | `site/008` - documentação da API e comunidade | site |
| 13 | `nucleo/070` - pedido de demonstração (rota pública) | backend |
| 14 | `site/009` - empresa, contacto e páginas legais | site |
| 15 | `site/010` - pesquisa, SEO e build de publicação | site |
| 16 | `nucleo/071` - proxy por caminho, endereços antigos e deploy coordenado | backend (deploy) |

As tarefas 1 a 4 podem ir para produção sem o site: a 16 trata do proxy e
dos redireccionamentos, e a raiz pode mostrar uma página provisória.

## Conteúdo por fornecer (Pedro)

- Preços definitivos (os do `PackageSeeder` estão marcados como exemplo:
  1.500 / 3.500 / 7.500 MT por mês; 15.000 / 35.000 / 75.000 MT por ano).
- Nome da empresa, telefone, email, morada, número de WhatsApp.
- Capturas de ecrã reais do sistema.
- Testemunho de cliente, com autorização.
- Canal da comunidade (fórum, WhatsApp ou outro).
- Se a API fica aberta aos clientes com credenciais próprias.
- Resposta sobre migração de dados para as perguntas frequentes.
- Textos de Sobre nós, Termos de utilização e Política de privacidade.

## Desenhos por aprovar

Preços, Sobre nós, Clientes, Contacto, lista e artigo do blog, guia, e a
versão para telemóvel de todas as páginas.
