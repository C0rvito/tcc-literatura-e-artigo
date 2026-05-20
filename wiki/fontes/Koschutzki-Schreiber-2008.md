---
title: Centrality Analysis Methods for Biological Networks and Their Application to Gene Regulatory Networks
authors: Dirk Koschützki, Falk Schreiber
year: 2008
journal: Gene Regulation and Systems Biology
doi: 10.4137/GRSB.S702
type: Artigo Original (Metodológico)
tags: [centralidade, motifs, GRN, regulacao-genica, topologia]
---

# Dissecação: Koschützki & Schreiber (2008)

Este artigo fornece uma visão abrangente sobre como diferentes medidas de centralidade avaliam os nós em uma Rede de Regulação Gênica (GRN), provando que não existe uma "centralidade universal" e introduzindo centralidades baseadas em motivos topológicos (*motifs*).

## 1. Metodologia e Modelagem
- **Rede Analisada**: Rede de Regulação Transcricional de *Escherichia coli* (RegulonDB v5.5).
- **Métricas do Grafo**: Grafo direcionado com $N = 1250$ vértices e $E = 2515$ arestas.
- **Objetivo**: Identificar os "reguladores globais" (genes no topo da hierarquia regulatória) usando 8 medidas de centralidade diferentes.

## 2. Tipos de Centralidade e Fórmulas
O artigo categoriza e testa as seguintes centralidades:

1.  **Grau (Degree)**: Medida puramente local. Em grafos direcionados (GRNs), separa-se em *in-degree* (genes altamente regulados) e *out-degree* (reguladores que controlam muitos alvos).
2.  **Proximidade (Closeness)**: Baseada na soma das distâncias mais curtas.
    $$C_{clo}(u) = \frac{1}{\sum_{v \in V} dist(u,v)}$$
    *Nota: Só pode ser aplicada em redes fortemente conectadas.*
3.  **Radialidade e Integração**: Variações da proximidade que usam uma matriz de distância reversa, permitindo o cálculo em redes desconectadas.
4.  **Intermediação do Caminho Mais Curto (*Shortest Path Betweenness*)**: Mede a capacidade de um nó monitorar a "comunicação". Nós de alto *betweenness* e baixo grau (HBLC) apoiam a modularização da rede (ver também [[Freeman-1977]] e [[Yu-et-al-2007-Bottlenecks]]).
5.  **PageRank / Katz Status Index**: Medidas baseadas no espectro/matriz de adjacência, sensíveis à direcionalidade das arestas (o quão importantes são os nós que apontam para você).

## 3. Centralidades Baseadas em Motivos (*Motif-based Centralities*)
A grande inovação metodológica do artigo. Em vez de focar no grafo inteiro, foca na participação do nó em pequenos subgrafos repetitivos (motivos).
- **Cálculo**: $C_{mb}(v)$ atribui a cada vértice $v$ o número de vezes que $v$ ocorre como correspondência (match) de um motivo específico $M$ (ex: *Feed-Forward Loop* - FFL, cadeias regulatórias).
- **Variantes**: Pode ser refinado por "papel" (ex: o vértice $v$ atua como o "mestre", o "intermediário" ou o "alvo" no FFL?).

## 4. Resultados Quantitativos
- Ao analisar os top 2% dos genes da rede (25 genes), a **centralidade baseada em motivos da classe "Cadeia" (Chains)** foi a mais bem-sucedida, identificando **15 dos 18 reguladores globais conhecidos** (83% de precisão), superando o *out-degree* e o *betweenness* (que identificou apenas 11).
- **Correlação Kendall**: A correlação topológica entre as diferentes métricas foi medida. Curiosamente, a centralidade *betweenness* e a baseada no motivo FFL tiveram as correlações mais baixas (< 0.5) com as demais métricas, provando que medem fenômenos topológicos fundamentalmente diferentes.

## 5. Implicações para o TCC
Para a modelagem matemática das redes de Parkinson:
- O grau simples (*hub-ness*) muitas vezes não é suficiente. 
- A centralidade baseada em motivos pode ser usada para encontrar genes de Parkinson que participam ativamente de cascatas regulatórias específicas (como cadeias), o que justificaria abordagens terapêuticas mais direcionadas.

## Fontes
- [[Redes de Co-expressão]]
- [[Hubs (Nós Centrais)]]
- [[Convergência Fenotípica]]
