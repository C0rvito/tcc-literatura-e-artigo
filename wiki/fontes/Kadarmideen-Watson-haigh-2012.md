---
title: "Building gene co-expression networks using transcriptomics data for systems biology investigations: Comparison of methods using microarray data"
authors: Haja N Kadarmideen, Nathan S Watson-haigh
year: 2012
journal: Bioinformation
doi: 10.6026/97320630008855
type: Artigo Original (Metodológico)
tags: [WGCNA, PCIT, redes-de-co-expressao, hubs, topologia-scale-free]
---

# Dissecação: Kadarmideen & Watson-haigh (2012)

Este estudo compara duas abordagens populares para a construção de Redes de Co-expressão Gênica (GCN): WGCNA (Weighted Gene Co-expression Network Analysis) e PCIT (Partial Correlation and Information Theory), avaliando como cada uma lida com nós altamente conectados (hubs).

## 1. Metodologia Detalhada
- **Dados**: Microarray transcriptômico de pele fetal de ovinos (N=16 matrizes), com 13.511 genes após filtragem de variância e expressão média.
- **WGCNA**: 
  - Utiliza função de adjacência baseada em potência ($a_{ij} = |cor(x_i, x_j)|^\beta$) para forçar uma topologia *scale-free*.
  - $\beta$ variou de 3 a 11 nas diferentes redes para atingir $R^2 \ge 0.85$.
  - Módulos definidos por agrupamento hierárquico da matriz de dissimilaridade baseada na Sobreposição Topológica (1 - TOM).
- **PCIT**:
  - Abordagem *data-driven* que identifica e remove arestas espúrias usando correlação parcial e teoria da informação.
  - Avalia trios de genes (A, B, C) e remove a aresta AB se a correlação for totalmente explicada pelas fortes correlações AC e BC.

## 2. Resultados Quantitativos e Evidências
- **Nós Altamente Classificados Diferencialmente (HDR)**: Identificaram 1.017 genes cujos ranks de conectividade divergiam significativamente entre WGCNA e PCIT.
- **Impacto nos Hubs**: O algoritmo **PCIT removeu muitas arestas dos nós mais altamente interconectados (hubs)**. Isso ocorre porque o PCIT deleta conexões fortes entre genes rigidamente co-regulados, considerando-as dependentes de terceiros nós.
- **Vantagem do WGCNA**: Os autores concluem que o WGCNA é mais favorável porque "retém os genes hub biologicamente relevantes e suas conexões dentro das sub-redes intactas", o que é provado por análises de enriquecimento gênico.

## 3. Fórmulas Chave
- **Correlação Parcial (PCIT)**:
  $$r_{AB.C} = \frac{r_{AB} - r_{AC}r_{BC}}{\sqrt{(1-r_{AC}^2)(1-r_{BC}^2)}}$$
  Indica a força da relação linear entre A e B independente de C.

## 4. Implicações para o TCC
- Justifica metodologicamente a escolha do **WGCNA** em vez de métodos de correlação parcial estrita para o TCC do usuário, pois o WGCNA preserva a estrutura de *hubs* em módulos co-regulados, o que é essencial para identificar os reguladores mestres da convergência fenotípica na DP.

## Fontes
- [[Redes de Co-expressão]]
- [[Hubs (Nós Centrais)]]
