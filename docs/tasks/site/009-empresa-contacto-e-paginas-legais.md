# 009 - Empresa, contacto e páginas legais

## Objectivo
O site tem Sobre nós, Clientes, Contacto com pedido de demonstração,
Termos de utilização e Política de privacidade.

Depende de: backend `nucleo/070` (rota pública do pedido de demonstração).
Desenhos por aprovar antes.

## Passo-a-passo
1. Sobre nós e Clientes: textos e nomes fornecidos pelo Pedro; clientes só
   com autorização de cada um.
2. Contacto: telefone, email, morada, WhatsApp e formulário de pedido de
   demonstração (nome, empresa, telefone ou WhatsApp, mensagem opcional).
3. O formulário envia para a rota do `nucleo/070`, mostra os erros de
   validação campo a campo e uma confirmação no fim. Com a API em baixo,
   mostra o telefone e o WhatsApp como alternativa.
4. Termos de utilização e Política de privacidade em MDX, com a data da
   última alteração. A política diz o que o formulário recolhe e para quê.
5. Testes: envio com sucesso, erros de validação e falha da API (MSW).

## Registo do que foi concluído
_(por preencher)_
