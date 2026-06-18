# Guia de Síntese Estratégica

## O que este sub-agente produz

Quatro artefatos por quarter:

  1. FRASE-FOCO — Uma frase curta que captura o tema dominante
     do trimestre. Aparece no banner do quarter.
     Ex: "Foco redução da superfície de erros e expansão de piloto."

  2. OBJETIVO DO TRIMESTRE — 2-4 bullet points que descrevem O QUE
     o time busca alcançar. Aparece no card "Objetivo do Trimestre".

  3. FOCO ESTRATÉGICO — 2-4 bullet points que descrevem OS EIXOS
     transversais de atuação. Aparece no card "Foco Estratégico".

  4. EXPECTATIVA — 2-3 bullet points que descrevem O QUE SE ESPERA
     como resultado. Aparece no card "Expectativa".

Esses quatro artefatos formam a narrativa estratégica do quarter:
juntos, respondem a "Por que estamos fazendo isso?" e
"Como saberemos que deu certo?"


## Diferença entre os três cards

Os três cards são complementares e NÃO devem se sobrepor.

  OBJETIVO = O QUE queremos alcançar (resultados desejados)
    Foco em DESTINO. Verbos no infinitivo.
    "Expandir a cobertura de pagamentos escriturais"
    "Reduzir em 30% os tickets de conciliação"

  FOCO ESTRATÉGICO = COMO vamos atuar (eixos de atuação)
    Foco em ABORDAGEM. Substantivos ou frases nominais.
    "Estabilidade e redução da superfície de erros"
    "Governança e compliance"
    "Adoção e experiência do usuário"

  EXPECTATIVA = O QUE ESPERAMOS que aconteça (tom do quarter)
    Foco em HORIZONTE. Tom prospectivo.
    "Entrega contínua dos épicos de Delivery"
    "Validação das hipóteses de Discovery antes de Q4"
    "Consolidação dos pilotos abertos no quarter anterior"

  TESTE DE SOBREPOSIÇÃO:
    Se um bullet poderia ir em mais de um card sem estranhamento,
    ele provavelmente está genérico demais. Reescreva com mais
    especificidade.

    Errado (genérico, caberia em qualquer card):
      "Melhorar o produto"

    Certo (específico, cabe só no Objetivo):
      "Eliminar as inconsistências de conciliação bancária
       em cobranças via QRCode"


## Matriz de fontes × campos

Para o QUARTER PASSADO (respostas_questionario = null):
  Toda a síntese é derivada exclusivamente dos épicos.

  ┌───────────────────────┬──────────┬──────────┬─────────┬────────┐
  │ FONTE                 │ FRASE-   │ OBJETIVO │ FOCO    │ EXPEC- │
  │                       │ FOCO     │          │ ESTRAT. │ TATIVA │
  ├───────────────────────┼──────────┼──────────┼─────────┼────────┤
  │ Títulos dos épicos    │    ●     │    ●     │    ●    │        │
  │ Objetivos dos épicos  │    ●     │    ●     │    ●    │        │
  │ Resumos dos épicos    │          │          │    ●    │    ●   │
  │ Proporção Deliv/Disc  │          │          │         │    ●   │
  │ T-shirt sizes         │          │          │         │    ●   │
  └───────────────────────┴──────────┴──────────┴─────────┴────────┘

Para o QUARTER FUTURO (respostas_questionario preenchido):
  Cruzar épicos com respostas do PM.

  ┌───────────────────────┬──────────┬──────────┬─────────┬────────┐
  │ FONTE                 │ FRASE-   │ OBJETIVO │ FOCO    │ EXPEC- │
  │                       │ FOCO     │          │ ESTRAT. │ TATIVA │
  ├───────────────────────┼──────────┼──────────┼─────────┼────────┤
  │ Títulos dos épicos    │    ●     │    ●     │    ●    │        │
  │ Objetivos dos épicos  │    ●     │    ●     │    ●    │        │
  │ Resp. continuidade    │          │    ●     │         │        │
  │ Resp. direcionamento  │    ●     │    ●     │    ●    │        │
  │ Resp. problemas/dores │          │    ●     │    ●    │        │
  │ Resp. oportunidades   │          │          │    ●    │        │
  │ Resp. restrições      │          │          │    ●    │    ●   │
  │ Resp. métricas        │          │          │         │    ●   │
  │ Resp. discovery       │          │    ●     │         │        │
  │ Resp. expectativa     │          │          │         │    ●   │
  │ Proporção Deliv/Disc  │          │          │         │    ●   │
  └───────────────────────┴──────────┴──────────┴─────────┴────────┘


## Método de agrupamento temático

Para gerar os bullets, primeiro agrupe os épicos por tema.

  PASSO 1 — Listar todos os títulos e objetivos dos épicos.

  PASSO 2 — Identificar temas recorrentes. Um tema é um domínio
  de negócio ou eixo de atuação que aparece em 2+ épicos.
    Exemplos de temas:
      "Pagamentos" (3 épicos mencionam pagamentos)
      "Cobranças" (2 épicos mencionam cobrança/piloto)
      "Governança financeira" (2 épicos mencionam orçamento/aprovação)

  PASSO 3 — Se um épico não se encaixa em nenhum tema, ele é
  avulso. Épicos avulsos podem virar um bullet próprio se forem
  relevantes, ou ser absorvidos em um tema mais amplo.

  PASSO 4 — Cada tema gera no máximo 1 bullet por card. Se há
  3 temas, há no máximo 3 bullets.


## Regras de redação

### FRASE-FOCO
  - Exatamente 1 frase
  - Máximo 80 caracteres
  - Começar com "Foco" ou "Foco em"
  - Mencionar no máximo 2 temas dominantes
  - Tom assertivo, não descritivo
  Bom: "Foco redução da superfície de erros e expansão de piloto."
  Ruim: "Neste quarter o time vai trabalhar em diversas iniciativas
         relacionadas a erros e piloto." (descritivo, longo)

### OBJETIVO DO TRIMESTRE
  - 2-4 bullet points
  - Cada bullet: máximo 15 palavras
  - Verbos no infinitivo: "Expandir", "Reduzir", "Consolidar",
    "Garantir", "Viabilizar", "Eliminar", "Fortalecer"
  - Sem artigos no início: "Expandir cobertura" não "A expansão da cobertura"
  - Cada bullet cobre um tema distinto
  - Ordem: do mais abrangente ao mais específico

### FOCO ESTRATÉGICO
  - 2-4 bullet points
  - Cada bullet: máximo 10 palavras
  - Frases nominais ou substantivadas: "Estabilidade e performance",
    "Governança e compliance", "Adoção e experiência do usuário"
  - Representam EIXOS transversais, não épicos específicos
  - Um eixo pode agrupar múltiplos épicos
  - Ordem: do mais prioritário ao complementar

### EXPECTATIVA
  - 2-3 bullet points
  - Cada bullet: máximo 15 palavras
  - Tom prospectivo: "Entrega contínua de...", "Validação de...",
    "Consolidação de..."
  - Deve refletir a ambição do quarter (alta, moderada, conservadora)
  - Para quarter passado: derivar do perfil dos épicos
    (muitos grandes = ambição alta; maioria discovery = exploração)
  - Para quarter futuro: derivar da resposta à pergunta 8 do
    questionário


## Exemplos completos

EXEMPLO — QUARTER PASSADO (sem questionário):

  Épicos:
    Delivery: "Testes Migração DataGrid", "Evolução API parcelas",
      "Liberação Supply Cobranças", "Baixa QRCode Itaú",
      "Pagamentos multiempresa EVEN", "Estudo arquitetura API"
    Discovery: "Fluxo de Caixa Fase 2", "Aprovação Orçamentária"

  Temas identificados:
    - Pagamentos (3 épicos: Supply, multiempresa, arquitetura API)
    - Cobranças (2 épicos: Supply Cobranças, QRCode Itaú)
    - Visão gerencial (2 épicos: Fluxo de Caixa, Aprovação)
    - Infraestrutura (1 épico: DataGrid)

  Saída:
    frase_foco: "Foco em evolução da visão gerencial e
      estabilização de integrações."
    objetivo:
      - "Evoluir a visão executiva e fortalecer a governança"
      - "Ampliar a inteligência sobre o orçamento empresarial"
    foco_estrategico:
      - "Mais dados e visibilidade para decisões"
      - "Governança, compliance e confiabilidade"
      - "Adoção e experiência do usuário"
    expectativa:
      - "Entrega contínua dos épicos de Delivery"
      - "Geração de valor para o negócio"


EXEMPLO — QUARTER FUTURO (com questionário):

  Épicos:
    Delivery: "Supply Pagamentos", "Evolução API parcelas",
      "Supply Cobranças", "Baixa QRCode Itaú",
      "Pagamentos multiempresa", "Estudo arquitetura API"
    Discovery: "Fluxo de Caixa Fase 2", "Aprovação Orçamentária"

  Respostas do questionário:
    continuidade: "Supply e DataGrid continuam."
    direcionamento: "Escalar piloto e reduzir erros."
    problemas_dores: "Inconsistência na conciliação QRCode."
    oportunidades: "Whitelabel na API de pagamentos."
    restricoes: "Time reduzido em agosto."
    metricas: "100% clientes migrados, zero regressão."
    discovery: "Validar arquitetura para Whitelabel."
    expectativa: "Equilibrar entrega e discovery."

  Saída:
    frase_foco: "Foco redução da superfície de erros e
      expansão de piloto."
    objetivo:
      - "Consolidar integrações de pagamento e cobranças"
      - "Eliminar inconsistências na conciliação bancária"
      - "Viabilizar evolução para modelo Whitelabel"
    foco_estrategico:
      - "Estabilidade e redução da superfície de erros"
      - "Expansão controlada de pilotos"
      - "Exploração do modelo Whitelabel"
    expectativa:
      - "Entrega contínua com foco em consolidação"
      - "Validação das hipóteses de Discovery antes de Q4"
