---
tags: [teoria-dos-grafos, centralidade, topologia-de-rede, fluxo-de-informacao]
---
# Centralidade de Intermediação (Betweenness Centrality)

A **Centralidade de Intermediação** é uma medida da centralidade de um vértice em um grafo. Ela quantifica o número de vezes que um nó atua como uma ponte ao longo do caminho mais curto entre outros dois nós. Foi formalmente introduzida por Linton Freeman em 1977.

## Definição Formal

A centralidade de intermediação $C_B(v)$ para um vértice $v$ é a soma da fração de todos os caminhos mais curtos entre pares de nós que passam por $v$:

$$C_B(v) = \sum_{s 
eq v 
eq t} \frac{\sigma_{st}(v)}{\sigma_{st}}$$

Onde:
- $\sigma_{st}$ é o número total de caminhos mais curtos do nó $s$ para o nó $t$.
- $\sigma_{st}(v)$ é o número desses caminhos que passam através de $v$.

## Implicações

- **Controle de Fluxo**: Nós com alta intermediação têm um papel crucial no controle do fluxo de informação (ou de matéria, em redes biológicas) através da rede. Eles podem facilitar, impedir ou distorcer a comunicação.
- **Bottlenecks**: Nós com alta intermediação são frequentemente chamados de *bottlenecks*. A remoção desses nós pode causar a [[Fragmentação de Rede]].
- **Essencialidade**: Em redes regulatórias, a intermediação é um forte preditor da essencialidade de um gene. Um gene *bottleneck* conecta diferentes processos biológicos e sua falha tem consequências drásticas.

## Tipos de Hubs

O estudo de *bottlenecks* levou à distinção entre:
- **Party Hubs**: Nós com alto grau, mas baixa intermediação. Estão no centro de módulos densos e coesos.
- **Date Hubs**: Nós com alta intermediação, que conectam diferentes módulos. Frequentemente, não são co-expressos com seus vizinhos, pois coordenam processos distintos no tempo e espaço.

## Fontes
- [[Freeman-1977]]
- [[Yu-et-al-2007-Bottlenecks]]
- [[Koschutzki-Schreiber-2008]]
