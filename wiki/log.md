# Wiki Log

## [2026-05-27] - Ingestão de Nova Fonte
- **Fonte**: [[Coukos-Krainc-2024]] (Review em *Nature Reviews Neuroscience*).
- **Operação**: Extração de mecanismos de convergência (mitocôndria, lisossomo, sinapse) e contatos inter-organelas. Atualização de múltiplas entidades e conceitos.

## [2026-05-22] Expansão: Documentação Prática do Polars
- **Ação**: Atualização profunda do conceito [[Manipulação de Dados com Polars]].
- **Conteúdo Adicionado**: Seções de I/O (leitura/escrita de CSV, Parquet, Excel), Junções (joins), Reshaping (Melt/Pivot) e Tratamento de Dados Ausentes (nulls).
- **Impacto**: Fornece um guia de referência completo para manipulação de grandes conjuntos de dados transcriptômicos, cobrindo desde a carga de dados até a exportação de resultados filtrados.

## [2026-05-22] Ingestão: Metodologias de Pipeline e Visualização (Rich/Polars)
- **Ação**: Processamento do diálogo técnico contido em `raw/Nova conversa.md`.
- **Fontes Criadas**: [[Nova-conversa-2026-05-22]]
- **Conceitos Criados**: [[Visualização de Dados com Rich]], [[Rastreamento de Execução]]
- **Conceitos Atualizados**: [[Manipulação de Dados com Polars]] (adição da arquitetura Polars Sandwich).
- **Impacto**: Formaliza a metodologia de pipelines híbridos (Polars/Pandas) e estabelece padrões de monitoramento e visualização de runtime para o projeto da tese.

## [2026-05-22] Ingestão: Automação com py4cytoscape
- **Ação**: Pesquisa e processamento da biblioteca `py4cytoscape` conforme novo protocolo de ferramentas.
- **Arquivo Raw**: `raw/py4cytoscape-docs.md`.
- **Fontes Criadas**: [[py4cytoscape-Docs]]
- **Conceitos Criados**: [[Visualização de Redes com py4cytoscape]]
- **Impacto**: Estabelece a metodologia para visualização reprodutível de redes biológicas e integração com o ecossistema Python (Pandas/NetworkX).

## [2026-05-22] Ingestão: Comparativo Pandas vs. Polars
- **Ação**: Processamento da fonte `raw/Pandas vs. Polars...md` (via web fetch para detalhamento).
- **Fontes Criadas**: [[Usando-Polars]]
- **Conceitos Criados**: [[Bibliotecas-Python]], [[Manipulação de Dados com Polars]]
- **Impacto**: Fornece base técnica para escolha de ferramentas de alta performance no processamento de grandes redes de co-expressão, com foco em eficiência de memória (redução de 97%) e velocidade (8x mais rápido).

## [2026-05-20] Criação de Novos Conceitos Metodológicos e Teóricos
- **Ação**: Agente Generalist dissecou `wiki/fontes/` para extrair e fundamentar matematicamente novos conceitos da teoria de grafos e WGCNA.
- **Conceitos Criados**: 
  - [[Conexão Preferencial]] (Barabási & Albert)
  - [[Medida de Sobreposição Topológica]] (TOM)
  - [[Module Eigengene]]
  - [[Motivos de Rede]]
  - [[Random Walk with Restart]] (RWR)
  - [[Redes Small-World]]
  - [[Soft Thresholding]]
- **Atualização**: O arquivo `wiki/index.md` foi atualizado para incluir os novos conceitos na listagem oficial em ordem alfabética.

## [2026-05-20] Extração de Novos Conceitos de Rede
- **Conceitos Criados**: Foram extraídos e definidos 4 novos conceitos fundamentais da teoria de grafos a partir das fontes existentes.
  - [[Tolerância a Erros]]: Definido a partir de `Albert-et-al-2000`.
  - [[Fragmentação de Rede]]: Definido a partir de `Albert-et-al-2000` e `Freeman-1977`.
  - [[Centralidade de Intermediação]]: Definido a partir de `Freeman-1977`, `Yu-et-al-2007-Bottlenecks`, e `Koschutzki-Schreiber-2008`.
  - [[Modularidade Hierárquica]]: Definido a partir de `Ravasz-et-al-2002-Hierarchical` e `Mason-Verwoerd-2007`.
- **Índice e Log**: Atualizados para refletir as novas adições à base de conhecimento.

## [2026-05-20] Refatoração para Rigor Acadêmico e Idioma Português
- **GEMINI.md**: Atualizado com novas diretrizes de rigor científico e obrigatoriedade do Português.
- **Fontes**: Refatoradas `Tran-et-al-2020`, `Zagare-et-al-2025` e `Albert-et-al-2000` com metodologias detalhadas e dados quantitativos.
- **Entidades**: Traduzidas e expandidas para incluir mapeamento de rede e evidências por modelo (SNCA, LRRK2, PRKN, PINK1, GBA, RHOT1).
- **Conceitos**: Todos os arquivos renomeados para o português e conteúdo aprofundado com foco em teoria de redes e mecanismos moleculares convergentes.
- **Estrutura**: Consolidação completa do diretório `wiki/conceitos/`.

## [2026-05-20] Conclusão da Dissecação Cirúrgica de Redes
- Finalizada a ingestão profunda em lote dos 8 artigos metodológicos (Yu 2007, Kadarmideen 2012, Koschützki 2008, Glaab 2012, Zhang 2005, Montenegro 2022, Mason 2007, Huber 2007, Koutrouli 2020).
- Todos os resumos foram escritos com rigor matemático (ex: matrizes TOM, limiares WGCNA, equações de centralidade).
- Otimização do catálogo de entidades biológicas (criadas notas detalhadas para genes da via do citoesqueleto/ROBO: ROBO2, ACTB, TUBA1A, MORF4L2).
- Índices perfeitamente sincronizados. Prontidão declarada para análise do Rascunho do TCC.

## [2026-05-20] Ingestão: Estudo LRRK2 (Zhao et al., 2024)
- Ingestão de `s41531-024-00761-8.pdf`.
- Extração de resultados de transcriptômica (sangue total, coorte PPMI) cruzados com topologia de PPI usando WGCNA, validando o uso da ferramenta para estratificação e detecção de convergência fenotípica na DP.
