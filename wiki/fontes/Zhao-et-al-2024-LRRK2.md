---
title: "Transcriptomics and weighted protein network analyses of the LRRK2 protein interactome reveal distinct molecular signatures for sporadic and LRRK2 Parkinson’s Disease"
authors: Yibo Zhao, Matthew Bracher-Smith, Yuelin Li, Kirsten Harvey, Valentina Escott-Price, Patrick A. Lewis, Claudia Manzoni
year: 2024
journal: npj Parkinson’s Disease
doi: 10.1038/s41531-024-00761-8
type: Artigo Original (Pesquisa / Redes Biológicas)
tags: [lrrk2, ppi, transcriptomica, wgcna, sPD, LRRK2-PD, convergencia-fenotipica, sangue-total]
---

# Dissecação: Zhao et al. (2024)

Este estudo utiliza dados transcriptômicos do sangue total e análise de redes (WGCNA e análise topológica) para comparar o interatoma da proteína LRRK2 em pacientes com Doença de Parkinson Esporádica (sPD) versus pacientes com a forma familiar ligada a mutações no LRRK2 (LRRK2-PD).

## 1. Metodologia Detalhada
- **Amostragem**: Dados de transcriptômica do sangue total (RNA-Seq) obtidos da coorte PPMI (Parkinson’s Progression Marker Initiative).
  - Casos sPD: N = 371
  - Casos LRRK2-PD: N = 116 (Focando na mutação LRRK2-G2019S, N = 100, excluindo carreadores de R1441C/G)
  - Controles Saudáveis (HC): N = 170
- **Construção da Rede (LRRK2$_{net}$)**: 
  - Interações Proteína-Proteína (PPIs) "de 2ª camada" (interatores interagindo entre si) extraídas da base HIPPIE (v2.3) com alto score de confiança ($\ge 0.72$).
  - A rede resultante continha **338 interatores** (nós) e **1345 arestas** (PPIs).
- **Análises Aplicadas**:
  - Expressão Diferencial (DEA) usando `DESeq2`.
  - Classificação via Machine Learning: Regressão Logística com algoritmo LASSO (Least Absolute Shrinkage and Selection Operator) usando o pacote `glmnet` em R. Parâmetro de sintonia $\lambda = 0.006$.
  - WGCNA (*Weighted Gene Co-expression Network Analysis*) usando *soft power* $\beta = 12$.
  - Algoritmo de agrupamento topológico *Fast Greedy* baseado na intermediação de arestas (*edge betweenness*) aplicado via Cytoscape (plugin clusterMaker2).

## 2. Resultados Quantitativos e Evidências
- **Desregulação Compartilhada e Específica**:
  - Em LRRK2-PD: 67 interatores (17.7%) alterados (39 *down*, 28 *up*).
  - Em sPD: 55 interatores (14.6%) alterados (28 *down*, 27 *up*).
  - **Apenas 13 interatores** exibiram a mesma alteração em ambas as condições (9 *down*, 4 *up*), ligados principalmente ao **metabolismo ribossomal e biossíntese de proteínas**.
- **Desempenho do Modelo LASSO**:
  - Um painel de 9 interatores (CDK2, RAB5B, ACTA2, TUBB6, LRRK2, HSPA1A, LMNB1, SNCA, SLC25A6) diferenciou sPD de LRRK2-PD com precisão de 80.3% no conjunto de treino e AUC de 0.735 no conjunto de teste.
- **Topologia do LRRK2$_{net}$**:
  - A rede seguiu uma distribuição *Scale-free* (Lei de Potência, $R^2 = 0.8606$).
  - Identificados "sub-seeds" (hubs) com os maiores graus, incluindo TP53 (grau=68), CDK2 (48), HSPA8 (46), e PRKN (28).

## 3. Descoberta de Redes Convergentes (Módulos e Clusters)
- **WGCNA**: 
  - Identificou 3 módulos principais de co-expressão: MTurquoise, MBlue e MBrown. 
  - O **Módulo Azul (MBlue)**, enriquecido para modificação de proteínas, metabolismo e função ribossomal (31 proteínas ribossomais), foi significativamente *down-regulado* em **ambos** os casos (sPD e LRRK2-PD) vs. controles.
- **Clustering Topológico**:
  - O algoritmo *Fast Greedy* identificou 11 clusters.
  - O **Cluster A**, que concentra grande parte das proteínas ribossomais, apresentou conectividade significativamente reduzida em sPD e LRRK2-PD.

## 4. Limitações Críticas
- **Tamanho da Amostra**: Especialmente na coorte LRRK2-PD, um $N$ maior aumentaria o poder estatístico.
- **Dinâmica Temporal vs. Estática**: As interações de proteínas da base HIPPIE são consideradas estáticas, enquanto a expressão in vivo é dinâmica. Os dados transcriptômicos refletem o momento do diagnóstico (baseline), podendo não capturar alterações que ocorrem na progressão da doença.

## 5. Citações Chave
- *"Interestingly, the 13 protein whose expression profile was altered in both LRRK2-PD and sPD were similarly related to ribosomal activity and protein biosynthesis, suggesting that there are commonalities at the molecular level between LRRK2-PD and sPD."*
- *"This conclusion cautions against considering LRRK2-PD and sPD as identical conditions, highlights the need to for specific experimental models to be generated to differentially study sporadic and LRRK2 PD, and confirms the requirement for patient stratification in clinical trials."*

## 6. Mapeamento de Entidades e Implicações para o TCC
- **Entidades Relacionadas**: [[LRRK2]], [[SNCA]], [[PRKN]], [[PINK1]], [[GBA]], [[ACTA2]], [[CDK2]], Proteínas Ribossomais.
- **Conceitos Chave**: [[Redes Scale-free]], [[Hubs (Nós Centrais)]], [[Redes de Co-expressão]], [[Convergência Fenotípica]].
- **Implicações para o TCC**: Este estudo fundamenta que o **WGCNA é eficaz na identificação de vias convergentes em subtipos de DP** (como a via ribossômica no Módulo Azul), apesar de as origens da doença (familial vs. esporádica) gerarem assinaturas globais distintas. A integração entre a topologia estática de PPI e a dinâmica transcriptômica (co-expressão) é o *core* metodológico que pode ser replicado ou discutido no seu TCC.