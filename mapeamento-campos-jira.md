# Mapeamento de Campos Customizados

Este documento ajuda o Extrator a localizar campos customizados que podem
ter nomes diferentes em cada instância Jira.

## Campos obrigatórios para busca

PLANEJADO PARA
  No Jira: "Planejado Para"
  Se nenhum for encontrado: reportar erro ao Orquestrador.

## Campos desejáveis para extração

TIPO DE INICIATIVA
  No Jira: "Tipo de Iniciativa"
Se ausente: retornar null (o Classificador inferirá).

T-SHIRT SIZE / ESTIMATIVA
  No Jira: "Tam. Camiseta"
  Se ausente: retornar null.

ÁREA DE PRODUTO
  Nomes possíveis:
  - "Área de Produto"
  - "Product Area"
  - "Component" (campo padrão do Jira)
  - "Team"
  Se ausente: retornar null.

ESCOPO DO ITEM
  No Jira: "Tipo de Roadmap"
  Se ausente: retornar null (o PM preencherá manualmente).
