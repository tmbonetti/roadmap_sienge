# Mapeamento de Campos Customizados

Este documento ajuda o Extrator a localizar campos customizados que podem
ter nomes diferentes em cada instância Jira.

## Campos obrigatórios para busca

PLANEJADO PARA
  Nomes possíveis no Jira:
  - "Planejado Para"
  - "Planned For"
  - "Target Quarter"
  - "Quarter"
  - "Sprint Quarter"
  Se nenhum for encontrado: reportar erro ao Orquestrador.

## Campos desejáveis para extração

TIPO DE INICIATIVA
  Nomes possíveis:
  - "Tipo de Iniciativa"
  - "Initiative Type"
  - "Tipo"
  - "Category"
  Se ausente: retornar null (o Classificador inferirá).

T-SHIRT SIZE / ESTIMATIVA
  Nomes possíveis:
  - "T-Shirt Size"
  - "Tamanho"
  - "Size"
  - "Story Points"
  - "Estimation"
  Se ausente: retornar null.

ÁREA DE PRODUTO
  Nomes possíveis:
  - "Área de Produto"
  - "Product Area"
  - "Component" (campo padrão do Jira)
  - "Team"
  Se ausente: retornar null.

ESCOPO DO ITEM (Roadmap / Extra Roadmap)
  Nomes possíveis:
  - "Escopo"
  - "Scope"
  - "Tipo de Escopo"
  - "Roadmap Scope"
  - "Classificação"
  Se ausente: retornar null (o PM preencherá manualmente).
