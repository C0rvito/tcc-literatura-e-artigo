---
title: "Graphs in molecular biology"
authors: Wolfgang Huber, Vincent J Carey, Li Long, Seth Falcon, Robert Gentleman
year: 2007
journal: BMC Bioinformatics
doi: 10.1186/1471-2105-8-S6-S8
type: Artigo de Revisão (Software/Teoria)
tags: [bioconductor, grafos-bipartidos, hipergrafos, R, algoritmos]
---

# Dissecação: Huber et al. (2007) - Grafos no Bioconductor

Este artigo foca na representação computacional de grafos aplicados à biologia molecular, especificamente no ecossistema de software R/Bioconductor, o que é altamente relevante para as análises práticas do TCC.

## 1. Tipos de Grafos Complexos
Além das definições básicas (direcionados/não-direcionados), o artigo destaca topologias cruciais para a biologia de sistemas:
- **Grafos Bipartidos (*Bipartite Graphs*)**: Nós divididos em dois conjuntos distintos (U e W), onde arestas só existem entre U e W (nunca dentro de U ou dentro de W). Muito usado para redes Gene-Doença ou Transcrito-Fator de Transcrição. A partir de um grafo bipartido, podem-se gerar projeções (one-mode graphs) que mostram, por exemplo, como duas doenças estão conectadas com base nos genes que compartilham.
- **Hipergrafos (*Hypergraphs*)**: Generalização onde uma aresta (*hyperedge*) pode conectar mais de dois nós simultaneamente. Ideal para modelar complexos proteicos (onde 5 proteínas se unem em um único complexo indivisível) em vez de forçar uma representação de clique (todas conectadas a todas em pares).
- **Grafos Acíclicos Direcionados (DAGs)**: Grafos direcionados sem ciclos. Usados massivamente para representar ontologias hierárquicas (Gene Ontology) e redes bayesianas.

## 2. Lidando com a Incerteza (Falsos Positivos e Negativos)
Um ponto central para a bioinformática: a matriz de adjacência de dados empíricos contém incertezas.
A ausência de uma aresta pode significar:
1.  **Verdadeiro Negativo**: Relação testada e não existe.
2.  **Falso Negativo**: Relação existe, mas a técnica não capturou.
3.  **Não Testado (*Untested*)**: Nenhuma medição foi feita (geralmente ignorado e assumido como falso por algoritmos ingênuos).

## 3. Subgrupos Coesos (Além dos Cliques)
Identificar módulos é relaxar a ideia de *cliques* absolutos:
- **k-plex**: Subgrafo onde cada nó é adjacente a pelo menos $v_s - k$ nós (onde $v_s$ é o tamanho do subgrafo). Permite a identificação de clusters mesmo com falhas de falsos negativos.
- **$\lambda$-sets**: Subconjuntos de nós cujas interconexões internas requerem a remoção de mais arestas para desconectá-los do que arestas que os ligam ao resto do grafo.

## 4. Implementações (Bioconductor)
O ecossistema R provê pacotes fundamentais:
- `graph`: Estrutura de dados base.
- `RBGL`: Algoritmos eficientes (interface para Boost Graph Library em C++).
- `Rgraphviz`: Visualização.

## 5. Implicações para o TCC
- **Visualização Otimizada**: Ao trabalhar com pacotes R no TCC para analisar a DP, a manipulação explícita de matrizes como *Grafos Bipartidos* pode facilitar a projeção de "Drogas x Hubs Mutados".
- A modelagem matemática dos Eigengenes do [[Li-et-al-2018-WGCNA]] no fundo funciona como a identificação de um *k-plex* ou $\lambda$-set denso, relaxando a restrição de cliques perfeitos em redes ruidosas (como RNA-Seq humano).

## Fontes
- [[Modelagem de Redes Biológicas]]
- [[Hubs (Nós Centrais)]]
