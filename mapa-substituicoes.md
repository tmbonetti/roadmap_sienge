# Mapa de Substituições — Template Roadmap

## Princípio fundamental

O template HTML é IMUTÁVEL em estrutura. O Gerador copia o
arquivo inteiro e substitui APENAS os pontos listados abaixo.
Nenhuma classe CSS, nenhum ID, nenhuma tag HTML, nenhuma
função JavaScript pode ser alterada, adicionada ou removida.

Se um dado de entrada estiver vazio, o ponto de substituição
recebe string vazia ou array vazio — nunca é removido do HTML.


## Categorias de substituição

Existem 3 tipos de substituição:

  TIPO A — TEXTO INLINE
    Substituir o conteúdo textual dentro de uma tag existente.
    A tag, seus atributos e elementos-irmãos permanecem intactos.

  TIPO B — LISTA DE <li>
    Substituir o conteúdo de um <ul> existente por novos <li>.
    Cada <li> segue um formato fixo com contenteditable e botão ×.

  TIPO C — ARRAY JAVASCRIPT
    Substituir o valor de uma variável JS no bloco <script>.
    Manter a estrutura de objeto com as mesmas chaves.


═══════════════════════════════════════
TIPO A — TEXTOS INLINE
═══════════════════════════════════════

HEADER
──────
Elemento: <span id="team-name">
Dado: contexto.team_name
Exemplo:
  ANTES: <span ... id="team-name" ...>PlugAndPay</span>
  DEPOIS: <span ... id="team-name" ...>Cobranças</span>

TABS
────
Elemento: <span id="tab-q3-label">
Dado: contexto.quarter_futuro
Exemplo:
  ANTES: <span id="tab-q3-label">Q3/2026</span>
  DEPOIS: <span id="tab-q3-label">Q4/2026</span>

Elemento: <span id="tab-q2-label">
Dado: contexto.quarter_passado
Exemplo:
  ANTES: <span id="tab-q2-label">Q2/2026</span>
  DEPOIS: <span id="tab-q2-label">Q3/2026</span>

QUARTER FUTURO (panel-q3)
─────────────────────────
Elemento: <span id="q3-name">
Dado: contexto.team_name

Elemento: <span id="q3-quarter">
Dado: quarter_futuro.quarter

Elemento: <div id="q3-period">
Dado: quarter_futuro.period

Elemento: <div id="q3-focus">
Dado: quarter_futuro.frase_foco

QUARTER PASSADO (panel-q2)
──────────────────────────
Elemento: <span id="q2-name">
Dado: contexto.team_name

Elemento: <span id="q2-quarter">
Dado: quarter_passado.quarter

Elemento: <div id="q2-period">
Dado: quarter_passado.period

Elemento: <div id="q2-focus">
Dado: quarter_passado.frase_foco


═══════════════════════════════════════
TIPO B — LISTAS DE <li>
═══════════════════════════════════════

Formato de cada <li> (FIXO, não alterar estrutura):

  <li><span contenteditable="true" spellcheck="false">{TEXTO}</span><button class="icon-btn del" onclick="removeFocusItem(this)" title="Remover">×</button></li>

QUARTER FUTURO
──────────────
Elemento: <ul id="q3-obj-list">
Dado: quarter_futuro.objetivo[]
Gerar 1 <li> por item do array.

Elemento: <ul id="q3-focus-list">
Dado: quarter_futuro.foco_estrategico[]
Gerar 1 <li> por item do array.

Elemento: <ul id="q3-exp-list">
Dado: quarter_futuro.expectativa[]
Gerar 1 <li> por item do array.

QUARTER PASSADO
───────────────
Elemento: <ul id="q2-obj-list">
Dado: quarter_passado.objetivo[]

Elemento: <ul id="q2-focus-list">
Dado: quarter_passado.foco_estrategico[]

Elemento: <ul id="q2-exp-list">
Dado: quarter_passado.expectativa[]

Se um array estiver vazio, o <ul> fica vazio (sem <li>).
Nunca remover o <ul> nem o botão "+ item" que vem depois.


═══════════════════════════════════════
TIPO C — ARRAYS JAVASCRIPT
═══════════════════════════════════════

BLOCO 1 — defaultData (cards de Delivery e Discovery)
──────────────────────────────────────────────────────
Localização: bloco <script>, variável "const defaultData = {...};"

Estrutura:
  const defaultData = {
    q3: {
      delivery: [
         { title: '...', obj: '...', resumo: '...', jira: '...', scope: '...', size: '...' },
      ],
      discovery: [
        { title: '...', obj: '...', resumo: '...', jira: '...', size: '...' },
      ]
    },
    q2: {
      delivery: [ ... ],
      discovery: [ ... ]
    }
  };

Mapeamento de campos:
  Entrada (epicos_prontos)  →  Saída (defaultData item)
  ─────────────────────────────────────────────────────
  titulo                    →  title
  objetivo                  →  obj
  resumo                    →  resumo
  jira_url                  →  jira
  size                      →  size

Notas:
  - Épicos com tipo "delivery" vão no array delivery[]
  - Épicos com tipo "discovery" vão no array discovery[]
  - Manter a ordem recebida (define numeração dos cards)
  - Strings em JS usam aspas simples '...'
  - Escapar aspas simples dentro do texto: ' → \'
  - Escapar quebras de linha: \n → \\n


BLOCO 2 — defaultEval (soluções em desempenho)
───────────────────────────────────────────────
Localização: bloco <script>, variável "const defaultEval = [...];"

Estrutura:
  const defaultEval = [
    {
      id: 1718640000000,
      title: '...',
      desc: '...',
      status: 'piloto',
      kpi: '',
      archived: false,
      archivedAt: ''
    },
  ];

Mapeamento de campos:
  Entrada (solucoes_desempenho)  →  Saída (defaultEval item)
  ──────────────────────────────────────────────────────────
  id                             →  id (número, sem aspas)
  title                          →  title
  desc                           →  desc
  status                         →  status ('piloto'|'escalando'|'concluida')
  kpi                            →  kpi
  archived                       →  archived (sempre false)
  archivedAt                     →  archivedAt (sempre '')

Notas:
  - Campo "id" é numérico, sem aspas
  - Campo "archived" é booleano, sem aspas
  - Se solucoes_desempenho estiver vazio, usar array vazio: []
  - Campos "jira_key", "confianca", "motivo", "updated" do
    sub-agente 7 NÃO são incluídos (não existem no template)


═══════════════════════════════════════
CARACTERES QUE DEVEM SER ESCAPADOS
═══════════════════════════════════════

EM CONTEÚDO HTML (Tipos A e B):
  &  →  &amp;
  <  →  &lt;
  >  →  &gt;
  "  →  &quot;  (dentro de atributos)

EM STRINGS JAVASCRIPT (Tipo C):
  '  →  \'
  \  →  \\
  Newline → \\n
  Tab → \\t

NUNCA escapar dentro de tags ou atributos HTML que já
existem no template — apenas no conteúdo textual injetado.
