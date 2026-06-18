# Taxonomia Delivery vs Discovery

## Definições

DELIVERY
  Iniciativa com escopo definido, comprometida para entrega no quarter.
  O time sabe O QUE vai construir e COMO. O resultado é código em
  produção, funcionalidade liberada, ou problema técnico resolvido.
  Exemplos: nova feature, correção estrutural, migração, integração,
  refatoração, otimização de performance, expansão de piloto.

DISCOVERY
  Iniciativa exploratória onde o time ainda está aprendendo. O
  resultado é CONHECIMENTO: validação de hipótese, estudo de
  viabilidade, protótipo, pesquisa com usuário, ou definição de
  solução. Pode ou não gerar um épico de Delivery futuro.
  Exemplos: estudo de arquitetura, pesquisa de mercado, teste de
  conceito, validação de problema, design de solução, spike técnico.


## Dicionário de palavras-chave

### Indicadores FORTES de Discovery (peso 3)
  - discovery
  - pesquisa
  - pesquisar
  - hipótese
  - validação (quando não precedido de "teste de")
  - análise exploratória
  - estudo de viabilidade
  - spike
  - poc (proof of concept)
  - prototipar
  - prototipação

### Indicadores MÉDIOS de Discovery (peso 2)
  - estudo
  - explorar
  - exploração
  - investigar
  - investigação
  - entendimento
  - mapear cenários
  - definir solução
  - avaliar alternativas
  - comparativo
  - benchmark

### Indicadores FRACOS de Discovery (peso 1)
  - análise (genérico — pode ser análise de bug)
  - levantamento
  - proposta
  - recomendação
  - fase 0
  - ideação

### Indicadores FORTES de Delivery (peso 3)
  - implementação
  - implementar
  - desenvolvimento
  - desenvolver
  - migração
  - migrar
  - integração (quando acompanhado de parceiro/sistema)
  - liberação
  - liberar
  - correção
  - corrigir
  - deploy
  - rollout
  - escalar

### Indicadores MÉDIOS de Delivery (peso 2)
  - evolução
  - evoluir
  - refatoração
  - refatorar
  - automação
  - automatizar
  - expansão de piloto
  - configuração
  - adequação

### Indicadores FRACOS de Delivery (peso 1)
  - melhoria
  - ajuste
  - suporte
  - manutenção
  - atualização


## Exemplos de referência

"Supply Pagamentos" → DELIVERY
  Motivo: integração com parceiro, escopo definido, expansão de piloto

"Estudo da arquitetura de pagamentos via API" → DISCOVERY
  Motivo: "estudo" + "arquitetura" indica exploração sem compromisso
  de entrega de código

"Evolução da API de geração de parcelas vencidas" → DELIVERY
  Motivo: "evolução" + escopo técnico específico indica entrega

"Fluxo de Caixa – Fase 2: Acompanhamento" → DISCOVERY
  Motivo: "Fase 2" com foco em acompanhamento/estudo, sem menção
  de implementação

"Aprovação Orçamentária – Comparativo de Versões" → DISCOVERY
  Motivo: "comparativo" indica análise exploratória

"Baixa de cobranças com QRCode – RI Itaú" → DELIVERY
  Motivo: correção/implementação técnica específica com parceiro

"Programação de pagamentos multiempresa (EVEN)" → DELIVERY
  Motivo: alteração no fluxo de produção com escopo definido
