SUB-AGENTE 1 — Coletor de Contexto
  Entrada: (nenhuma — inicia a conversa)
  Saída: { space_key, team_name, quarter_passado, quarter_futuro, periodo_passado, periodo_futuro }

SUB-AGENTE 2 — Extrator de Épicos Jira
  Entrada: { space_key, quarter }
  Saída: { epicos_raw[] } — lista de épicos com todos os campos brutos do Jira

SUB-AGENTE 3 — Classificador Deliv./Discovery
  Entrada: { epicos_raw[] }
  Saída: { epicos_classificados[] } — cada épico recebe campo "tipo": "delivery" | "discovery"

SUB-AGENTE 4 — Sintetizador de Conteúdo de Épicos
  Entrada: { epicos_classificados[] }
  Saída: { epicos_prontos[] } — cada épico com titulo, objetivo, resumo, jira_url, size

SUB-AGENTE 5 — Facilitador de Planejamento Futuro
  Entrada: { quarter_futuro, epicos_prontos_passado[] }
  Saída: { respostas_questionario{} }

SUB-AGENTE 6 — Estrategista Trimestral
  Entrada: { epicos_prontos[], respostas_questionario{}, quarter }
  Saída: { objetivo[], foco_estrategico[], expectativa[], frase_foco }

SUB-AGENTE 7 — Identificador de Soluções em Desempenho
  Entrada: { space_key }
  Saída: { solucoes_desempenho[] }

SUB-AGENTE 8 — Gerador de HTML
  Entrada: { contexto{}, quarter_passado{}, quarter_futuro{}, solucoes_desempenho[] }
  Saída: arquivo HTML completo
