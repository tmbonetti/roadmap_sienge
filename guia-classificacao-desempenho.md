# Guia de Classificação de Soluções em Desempenho

## O que é a aba Desempenho

A aba Desempenho do Roadmap lista soluções de produto que já foram
entregues (código em produção) mas que ainda estão em processo de
adoção, validação ou escalamento. São iniciativas que saíram do
"construir" e entraram no "acompanhar".

O ciclo de vida de uma solução entregue:

  DELIVERY → PILOTO → ESCALANDO → CONCLUÍDA (→ ARQUIVADA)

  PILOTO: solução liberada para um grupo restrito de clientes
    ou cenários. Está sendo validada em ambiente real.
    Sinais: poucos clientes, feature flag, beta, rollout parcial.

  ESCALANDO: solução validada no piloto e em processo de expansão
    para toda a base. Pode ter ajustes em andamento.
    Sinais: expansão gradual, rollout, migração de clientes,
    ramp-up, onboarding de novos clientes.

  CONCLUÍDA: solução 100% escalada, disponível para toda a base,
    sem acompanhamento ativo necessário. Pronta para arquivar.
    Sinais: disponível para todos, GA (General Availability),
    sem menções recentes de piloto ou escala.


## Fontes de sinais

Os sinais que indicam o status de uma solução podem vir de
múltiplas fontes. Cada fonte tem um peso diferente:

  PESO 3 — CAMPO CUSTOMIZADO
    Se o Jira tiver um campo como "Fase de Rollout", "Rollout Stage",
    "Fase", "Stage" com valores como "Piloto", "Scaling", "GA":
    usar diretamente.

  PESO 3 — LABEL EXPLÍCITA
    Labels que declaram a fase sem ambiguidade:
      Piloto: "piloto", "pilot", "beta", "early-access"
      Escalando: "scaling", "escalando", "rollout", "ramp-up",
                 "expanding"
      Concluída: "ga", "general-availability", "released",
                 "fully-deployed", "concluida"

  PESO 2 — COMENTÁRIO RECENTE (últimos 90 dias)
    Texto em comentários que mencione a fase atual:
      Piloto: "piloto", "pilot", "testando com clientes",
              "grupo restrito", "beta", "feature flag ativa",
              "clientes selecionados"
      Escalando: "escalando", "expandindo", "liberando para mais",
                 "rollout", "ampliando base", "onboarding",
                 "migrando clientes"
      Concluída: "concluído", "finalizado", "100% liberado",
                 "disponível para todos", "encerrado piloto",
                 "GA"

  PESO 1 — INFERÊNCIA POR STATUS DO ISSUE
    Se o épico tem status "Done"/"Closed" e resolution "Done"
    mas nenhum sinal explícito de piloto ou escala:
    classificar como "concluida" com confiança baixa.


## Regras de prioridade quando sinais conflitam

  1. Sinal mais RECENTE ganha (comentário de ontem > label antiga)
  2. Em sinais de mesma data: peso maior ganha
  3. Empate total: usar o status mais avançado no ciclo
     (concluida > escalando > piloto)


## O que NÃO é uma solução em desempenho

  - Épicos ainda em andamento (status "In Progress", "To Do")
  - Épicos cancelados (resolution "Won't Do", "Duplicate")
  - Épicos puramente técnicos sem impacto visível para o cliente
    (ex: "Refatoração do módulo de logs")
  - Épicos de Discovery (tipo "discovery") — por definição,
    não entregam solução em produção
  - Épicos do quarter atual sendo planejado — esses estão nas
    abas de Delivery/Discovery, não no Desempenho


## Critérios de inclusão

Um épico se torna candidato a solução em desempenho se:
  1. issuetype = Epic
  2. project = {space_key}
  3. status ∈ ("Done", "Closed", "Concluído", "Released", "Resolved")
  4. E pelo menos UMA das condições:
     a) Tem label de piloto/escala/GA
     b) Tem campo customizado de fase de rollout preenchido
     c) Tem comentário nos últimos 90 dias mencionando
        piloto/escala/rollout
     d) Foi finalizado nos últimos 6 meses (para capturar
        soluções recentes que podem não ter labels)
