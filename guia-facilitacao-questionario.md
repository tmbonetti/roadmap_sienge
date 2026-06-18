# Guia de Facilitação do Questionário Estratégico

## Filosofia

O questionário não é um formulário. É uma conversa estruturada.
O objetivo é extrair do Product Manager o conhecimento tácito que
ele tem sobre o próximo quarter — aquilo que está na cabeça dele
mas não está no Jira.

O Facilitador age como um parceiro de planejamento que faz as
perguntas certas, na ordem certa, e sabe quando aprofundar.


## Estrutura do questionário

O questionário tem 8 perguntas divididas em 3 blocos temáticos.
A ordem importa: começa pelo concreto (o que já existe), avança
para o estratégico (para onde ir) e termina no operacional (como
medir e o que esperar).

BLOCO A — CONTEXTO E CONTINUIDADE (perguntas 1)
  Base: o que veio antes condiciona o que vem depois.

BLOCO B — ESTRATÉGIA E DIRECIONAMENTO (perguntas 2, 3, 4, 5)
  Núcleo: onde o time vai investir energia e por quê.

BLOCO C — MENSURAÇÃO E EXPECTATIVA (perguntas 6, 7, 8)
  Fechamento: como saber se deu certo e qual o nível de ambição.


## Perguntas e intenções

PERGUNTA 1 — CONTINUIDADE
  Texto: "Quais iniciativas do quarter passado terão continuidade
  ou desdobramentos? Há algo que ficou incompleto e precisa ser
  priorizado?"

  Intenção: identificar épicos que transitam entre quarters,
  trabalho inacabado e dívidas técnicas herdadas.

  O que alimenta no Roadmap:
    → Objetivo do Trimestre (continuidade como eixo)
    → Épicos de Delivery (itens que retornam)


PERGUNTA 2 — DIRECIONAMENTO ESTRATÉGICO
  Texto: "Qual o principal tema ou direção estratégica para o
  próximo trimestre?"

  Intenção: capturar a big idea — o fio condutor que amarra
  os épicos em uma narrativa.

  O que alimenta no Roadmap:
    → Frase-foco do quarter
    → Foco Estratégico (eixo dominante)

  Exemplos de boas respostas:
    "Reduzir churn focando em estabilidade e performance"
    "Escalar o piloto de cobranças para 100% da base"
    "Abrir o módulo financeiro para mercado mid-market"

  Exemplos de respostas fracas (precisam de follow-up):
    "Continuar o trabalho" → vago demais
    "Várias coisas" → precisa priorização
    "Não sei ainda" → ok, mas voltar a esta no final


PERGUNTA 3 — PROBLEMAS E DORES
  Texto: "Quais são os maiores problemas ou dores dos clientes
  que o time precisa endereçar neste quarter?"

  Intenção: ancorar o planejamento em problemas reais, não só
  em features desejadas.

  O que alimenta no Roadmap:
    → Objetivo do Trimestre (problemas como motivadores)
    → Foco Estratégico (eixos derivados das dores)


PERGUNTA 4 — OPORTUNIDADES
  Texto: "Existe alguma oportunidade de negócio, tecnologia ou
  mercado que o time quer explorar?"

  Intenção: capturar itens de Discovery e apostas estratégicas
  que não nascem de dores mas de visão de futuro.

  O que alimenta no Roadmap:
    → Épicos de Discovery
    → Foco Estratégico (inovação como eixo)


PERGUNTA 5 — RESTRIÇÕES E DEPENDÊNCIAS
  Texto: "Há restrições técnicas, de time, orçamento ou
  dependências externas que impactam o planejamento?"

  Intenção: calibrar ambição com realidade. Um quarter com
  time reduzido ou migração de infra tem teto diferente.

  O que alimenta no Roadmap:
    → Expectativa (nível de ambição ajustado)
    → Foco Estratégico (restrições como eixo, ex: "estabilização")


PERGUNTA 6 — MÉTRICAS DE SUCESSO
  Texto: "Como você medirá o sucesso deste quarter? Quais
  indicadores são mais importantes?"

  Intenção: forçar pensamento orientado a resultado, não a output.

  O que alimenta no Roadmap:
    → Expectativa (indicadores como referência)

  Exemplos de boas respostas:
    "NPS acima de 45, redução de 30% nos tickets de conciliação"
    "100% dos clientes do piloto migrados, zero regressão"

  Exemplos de respostas fracas:
    "Entregar tudo" → output, não outcome
    "Não temos métricas" → ok, registrar e seguir


PERGUNTA 7 — DISCOVERY E APRENDIZADO
  Texto: "Quais hipóteses ou áreas o time precisa investigar
  antes de comprometer desenvolvimento? Há algo que precisa
  de validação com clientes?"

  Intenção: separar apostas validadas de apostas não validadas.
  Discovery precisa de espaço no quarter.

  O que alimenta no Roadmap:
    → Épicos de Discovery
    → Objetivo do Trimestre (aprendizado como eixo)


PERGUNTA 8 — EXPECTATIVA DE ENTREGA
  Texto: "Qual o nível de ambição para este quarter?"

  Intenção: calibrar o tom da Expectativa no Roadmap.

  Apresentar como opções:
    a) Entregar tudo e escalar — ambição alta, risco alto
    b) Focar em poucos itens com profundidade — consolidação
    c) Equilibrar entrega e discovery — maturidade
    d) Outro (descreva)

  O que alimenta no Roadmap:
    → Expectativa (tom e conteúdo)


## Follow-ups condicionais

O Facilitador pode (e deve) fazer follow-ups quando a resposta
for insuficiente. Seguem as regras:

QUANDO FAZER FOLLOW-UP:
  - Resposta com menos de 10 palavras para perguntas 2, 3 ou 6
  - Resposta que contradiz o contexto dos épicos passados
  - Resposta "não sei" para perguntas 1 ou 2 (as mais críticas)

COMO FAZER FOLLOW-UP:
  - Uma pergunta derivada, curta e específica
  - Referenciar os épicos passados como âncora
  - Nunca mais que 1 follow-up por pergunta

QUANDO NÃO FAZER FOLLOW-UP:
  - Resposta "não sei" ou "pular" para perguntas 4, 5 ou 7
  - Resposta curta mas completa (ex: "NPS e churn" para pergunta 6)
  - Usuário demonstra impaciência ou pressa

EXEMPLOS DE FOLLOW-UP:
  Pergunta 2, resposta "Continuar o trabalho":
  → "Entendi. Dos épicos que vocês tocaram — Supply Pagamentos,
     DataGrid, QRCode Itaú — qual deles melhor representa o tema
     dominante do próximo quarter?"

  Pergunta 3, resposta "Os de sempre":
  → "Especificamente, tem alguma dor que apareceu nos últimos
     meses que não existia antes? Ou as dores são as mesmas
     mas com urgência diferente?"

  Pergunta 6, resposta "Entregar tudo":
  → "Se tivesse que escolher um número para mostrar que o quarter
     foi um sucesso, qual seria?"
