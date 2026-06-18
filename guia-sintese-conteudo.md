# Guia de Síntese de Conteúdo para Roadmap

## Princípios de redação

1. FACTUAL. Cada frase deve ser rastreável a algo escrito no Jira.
   Se a informação não existe na description nem nos comments,
   ela não existe no Roadmap.

2. CONCRETO. Nomes de sistemas, parceiros, APIs, clientes e números
   são mais úteis que generalizações. Preservá-los sempre.
   Ruim: "Melhorar a integração bancária"
   Bom:  "Expandir integração escritural com parceiro Supply via API"

3. CONCISO. Cada campo tem um limite. Respeitar sem cortar informação
   essencial. Se algo não cabe, priorizar o quê sobre o como.

4. AUTOCONTIDO. Quem ler o Objetivo deve entender a meta sem precisar
   ler o Resumo. Quem ler o Resumo deve entender o escopo sem precisar
   abrir o Jira.

5. SEM JARGÃO DE STATUS. Não usar "Em andamento", "Concluído", "Done"
   nos textos. O Roadmap mostra o quê, não o estado do card.


## Regras por campo

### TÍTULO
  - Fonte: campo "summary" do épico
  - Transformações permitidas:
    · Remover prefixos mecânicos: "[EPIC]", "Epic -", "E -", "EPIC:"
    · Remover sufixos redundantes: "- Epic", "(Epic)"
    · Remover espaços duplos
  - Transformações proibidas:
    · Não reescrever o título
    · Não traduzir (se estiver em inglês, manter)
    · Não adicionar informação
  - Limite: sem limite (preservar integralmente após limpeza)

### OBJETIVO (máximo 2 frases, máximo 200 caracteres)
  - Fonte primária: description do épico
  - Fonte secundária: summary (se description não tiver objetivo claro)
  - Lógica de extração:
    1. Procurar por marcadores explícitos na description:
       · Linha que comece com "Objetivo:", "Meta:", "Goal:", "Finalidade:"
       · Parágrafo após heading "Objetivo" ou "## Objetivo"
       · Primeira frase após "O objetivo é...", "A meta é...",
         "Visa...", "Busca..."
    2. Se encontrou marcador: extrair o trecho e condensar em ≤ 2 frases
    3. Se não encontrou: sintetizar a partir do primeiro parágrafo da
       description. Usar o padrão:
       "Verbo no infinitivo + complemento que descreva o resultado."
    4. Se description for vazia: tentar derivar do summary.
       Ex: summary "Migração do DataGrid"
       → objetivo "Possibilitar exportação e análises de forma mais completa."
       Só se for possível sem inventar. Caso contrário: string vazia.
  - Tom: verbos no infinitivo ("Expandir...", "Garantir...", "Entregar...")
  - Evitar: iniciar com "O objetivo é..." (redundante — o label do campo
    já diz que é objetivo)

### RESUMO (máximo 3 frases, máximo 400 caracteres)
  - Fonte primária: description do épico (excluindo o trecho de objetivo)
  - Fonte secundária: comments recentes (últimos 30 dias)
  - Lógica de síntese:
    1. Identificar as informações mais relevantes da description:
       · O QUE será feito (escopo)
       · COMO será feito (abordagem técnica, se mencionada)
       · PARA QUEM (clientes, segmento, se mencionado)
       · COM QUEM (parceiros, integrações, se mencionado)
    2. Condensar em 2-3 frases priorizando:
       Escopo > Abordagem > Impacto
    3. Se houver comments recentes (≤ 30 dias) que agreguem contexto
       sobre resultado, andamento concreto ou decisão tomada:
       incorporar ao resumo. Não usar comments apenas para
       repetir o que a description já diz.
    4. Se description for vazia e não houver comments relevantes:
       string vazia.
  - Tom: factual, terceira pessoa ("Realizado...", "Adição de...",
    "Atuação direcionada na...")
  - Evitar:
    · Não copiar a description inteira
    · Não incluir status ("em andamento", "concluído")
    · Não incluir datas de sprint ou milestone
    · Não incluir menções a pessoas (@fulano)

### URL JIRA
  - Construir a partir do campo "key":
    https://{DOMÍNIO}.atlassian.net/browse/{key}
  - Derivar o DOMÍNIO automaticamente:
    · Se o campo "self" estiver disponível nos dados do épico,
      extrair o domínio da URL
      Ex: "self": "https://sienge.atlassian.net/rest/api/..."
      → domínio = "sienge"
    · Se "self" não estiver disponível, usar o space_key em
      lowercase como fallback: {space_key_lower}.atlassian.net
  - Se o key for inválido ou ausente: string vazia ""

### SIZE (T-Shirt)
  - Fonte: custom_fields.tshirt_size
  - Mapeamento de texto:
      "Extra Small", "XS", "PP"       → "XS"
      "Small", "S", "P"               → "S"
      "Medium", "M"                    → "M"
      "Large", "L", "G"               → "L"
      "Extra Large", "XL", "GG"       → "XL"
      "Extra Extra Large", "XXL", "XGG" → "XXL"
  - Mapeamento numérico (story points):
      1-2     → "XS"
      3-5     → "S"
      8       → "M"
      13      → "L"
      21      → "XL"
      34+     → "XXL"
  - Se o campo não existir ou for null: string vazia ""
  - Nunca inventar estimativa
    
### SCOPE (apenas delivery)
  - Fonte: custom_fields.escopo
  - Mapeamento:
      contém "extra" (case-insensitive)  → "extra"
      contém "roadmap" E NÃO "extra"     → "roadmap"
      null ou vazio                       → "" (PM preencherá)
  - Apenas para épicos tipo "delivery". Discovery não recebe scope.

## Exemplos de antes/depois

ANTES (dados brutos do Jira):
  summary: "[EPIC] Supply Pagamentos"
  description: "Objetivo: Expandir pagamentos escritural via API com
  parceiro de integração Supply\r\nResumo: Adicionar clientes
  aderentes ao piloto ecutar testes na nova versão do DataGrid
  de forma controlada e garantir que a liberação para os clientes
  continuam preservando as jornadas de negócio e o comportamento
  atual em produção."
  tshirt_size: "Medium"

DEPOIS (sintetizado):
  titulo: "Supply Pagamentos"
  objetivo: "Expandir pagamentos escritural via API com parceiro
  de integração Supply."
  resumo: "Adicionar clientes aderentes ao piloto, executar testes
  na nova versão do DataGrid de forma controlada e garantir que a
  liberação para os clientes preserve as jornadas de negócio e o
  comportamento atual em produção."
  size: "M"

Notas:
  - Prefixo "[EPIC]" removido do título
  - Objetivo extraído do marcador "Objetivo:"
  - Resumo extraído do marcador "Resumo:"
  - Erro de digitação "ecutar" mantido (fidelidade ao Jira)
  - Única alteração textual: "\r\n" convertido para espaço


ANTES (description sem marcadores):
  summary: "Programação de pagamentos multiempresa (EVEN)"
  description: "Entregar eficiencia operacional para empresas com
  grandes demandas de pagamento escritural, eliminando gargalo
  operacional na jornada de geração de pagamentos. Realizado grande
  alteração no fluxo de programação e geração de arquivos de
  pagamento escritural, integrado com VAN de transmissão (NEXXERA)
  garantindo geração de pagamentos em massa e multi empresa."
  tshirt_size: null

DEPOIS (sintetizado):
  titulo: "Programação de pagamentos multiempresa (EVEN)"
  objetivo: "Entregar eficiência operacional para empresas com
  grandes demandas de pagamento escritural, eliminando gargalo
  operacional na jornada de geração de pagamentos."
  resumo: "Alteração no fluxo de programação e geração de arquivos
  de pagamento escritural, integrado com VAN de transmissão (NEXXERA),
  garantindo geração de pagamentos em massa e multiempresa."
  size: ""

Notas:
  - Sem marcadores → primeiro período virou Objetivo, restante virou Resumo
  - size vazio porque o campo era null


ANTES (description vazia):
  summary: "Hotfix conciliação bancária"
  description: ""
  comments: [
    { date: "2026-05-20", body: "Corrigido o cálculo de hash do
      webhook Itaú. Deploy realizado em staging." }
  ]
  tshirt_size: "3"

DEPOIS (sintetizado):
  titulo: "Hotfix conciliação bancária"
  objetivo: ""
  resumo: "Correção no cálculo de hash do webhook Itaú."
  size: "S"

Notas:
  - Description vazia → objetivo vazio
  - Resumo derivado do comment mais recente (≤ 30 dias)
  - Removida menção a deploy/staging (status operacional)
  - Story points 3 → size "S"
