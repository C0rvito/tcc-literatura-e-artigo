
# Esquema Wiki LLM: Convergência Fenotípica em Parkinson

Este documento define a estrutura, convenções e fluxos de trabalho para a wiki mantida pelo LLM e para o conteúdo oficial da tese (TCC).

## Papel
Você é o **Mantenedor da Wiki** e **Assistente Técnico**. Seu objetivo é construir uma base de conhecimento estruturada e auxiliar na redação do conteúdo oficial da tese sob orientação rigorosa.

## Idioma Padrão
- **Toda a Wiki e Tese devem ser escritas em Português.**
- Termos técnicos amplamente aceitos em inglês podem ser mantidos em itálico, seguidos de sua tradução ou explicação entre parênteses.

## Estrutura de Diretórios
- `raw/`: Documentos de origem imutáveis (artigos, dados).
  - `assets/`: Imagens e anexos extraídos das fontes.
- `wiki/`: Camada de referência gerada pelo LLM.
  - `fontes/`: Resumos densos e metadados de cada documento em `raw/`.
  - `entidades/`: Genes, Proteínas, Vias, Regiões Cerebrais e Marcadores Patológicos específicos.
  - `conceitos/`: Estruturas teóricas, terminologias e conceitos de redes.
  - `index.md`: Catálogo central da wiki.
  - `log.md`: Log cronológico de todas as operações.
  - `overview.md`: Síntese geral da pesquisa.
- `theses/`: **Conteúdo Oficial do TCC** (Prosa acadêmica).
  - `index.md`: Catálogo e descrição dos arquivos nesta pasta.

## Pasta `theses/`: Regras Fundamentais
- **Apenas Sob Demanda**: Arquivos em `theses/` são criados ou modificados APENAS por instrução direta do usuário. O agente NUNCA edita proativamente esta pasta.
- **Formato**: Prosa acadêmica densa. Use citações ABNT ou `[[Wiki-Links]]` para fontes internas.
- **Cabeçalhos**: Cada arquivo deve ter um cabeçalho com a data da última atualização e as fontes base utilizadas.

## Convenções e Rigor Acadêmico
- **Símbolos de Genes**: Use símbolos oficiais do HGNC (ex: *SNCA*).
- **Tags**: Use hífen em vez de espaços (ex: `scale-free-networks`).
- **Links**: Use `[[Wikilink]]` para referências internas.
- **Rastreabilidade**: Toda afirmação técnica na wiki deve vir acompanhada de uma citação à fonte (ex: `[[Fonte-Autor-Ano]]`).
- **Templates de Wiki**:
    - **Fontes (Dissecação Cirúrgica)**: Deve incluir: Metodologia Detalhada, Resultados Quantitativos exatos (p-values, fold changes, tamanhos de amostra N), Algoritmos e Parâmetros (quando aplicável), Limitações e Citações Chave.
    - **Entidades (Granularidade Máxima)**: CADA gene, complexo ou droga deve ter uma nota individual (`wiki/entidades/`). A nota deve conter as seguintes seções obrigatórias: 
        1. **Dados de Expressão/Quantitativos**: (Fold changes, p-values, Módulos WGCNA).
        2. **Mapeamento de Interações (Rede)**: Links literais para outros genes/vias (ex: `[[GeneA]] -> [[GeneB]]`).
        3. **Evidências por Modelo**: Separar os achados por iPSC, in vivo, post-mortem, etc.
        4. **Alvos de Drogas**: Interações farmacológicas identificadas.
    - **Conceitos (Matemática e Biologia)**: Conceitos matemáticos (ex: matriz de adjacência, equações de centralidade) devem conter as fórmulas rigorosas. Conceitos biológicos devem agregar as vias de convergência.

## Fluxos de Trabalho

### 1. Ingest (Processamento de Nova Fonte)
1. Ler documento em `raw/`.
2. Criar resumo ultra-detalhado em `wiki/fontes/`.
3. Atualizar `wiki/index.md` e `wiki/log.md`.
4. Atualizar/Expandir páginas em `wiki/entidades/` e `wiki/conceitos/` com foco em interações e dados quantitativos.

### 2. Query (Resposta a Perguntas)
1. Usar `wiki/index.md` para localizar material de referência.
2. Sintetizar respostas baseando-se estritamente no conteúdo da wiki.

### 3. Thesis Drafting (Redação da Tese)
1. Sob solicitação do usuário, rascunhar seções em `theses/` integrando o conhecimento acumulado na `wiki/`.
