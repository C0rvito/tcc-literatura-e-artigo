---
title: A Set of Measures of Centrality Based on Betweenness
authors: Linton C. Freeman
year: 1977
journal: Sociometry
doi: 10.2307/3033543
type: Artigo Original (Teórico)
tags: [centralidade, intermediação, betweenness, teoria-dos-grafos, fluxo-de-informação]
---

# Resumo: Freeman (1977)

Este artigo introduz formalmente o conceito de **Centralidade de Intermediação (*Betweenness Centrality*)**, uma medida fundamental para identificar nós que controlam ou facilitam o fluxo de informações em uma rede.

## 1. Fundamentação Teórica
- **O Problema**: Medidas clássicas de centralidade (como as de Bavelas ou Sabidussi) falham em redes desconectadas ou grandes redes naturais porque dependem da soma das distâncias mínimas, que se tornam infinitas se não houver caminho entre dois nós.
- **A Solução**: Freeman propõe que a centralidade de um nó deve ser medida pelo grau em que ele se coloca entre outros nós em seus caminhos mais curtos (*geodesics*).

## 2. Definições e Fórmulas
- **Intermediação Parcial ($b_{ij}(p_k)$)**: A probabilidade de que o nó $p_k$ esteja no caminho mais curto entre os nós $p_i$ e $p_j$.
    - Se houver apenas um caminho mais curto e $p_k$ estiver nele, $b_{ij}(p_k) = 1$.
    - Se houver $g_{ij}$ caminhos mais curtos e $p_k$ estiver em $g_{ij}(p_k)$ deles, então $b_{ij}(p_k) = \frac{g_{ij}(p_k)}{g_{ij}}$.
- **Centralidade de Intermediação do Ponto ($C_B(p_k)$)**: A soma de todas as intermediações parciais para todos os pares de nós na rede:
  $$C_B(p_k) = \sum_{i < j}^n \sum_{j}^n b_{ij}(p_k)$$
- **Centralidade Relativa ($C'_B(p_k)$)**: Normalização da medida para permitir a comparação entre redes de diferentes tamanhos, variando de 0 a 1.

## 3. Aplicações e Insights
- **Controle de Informação**: Nós com alta intermediação têm o potencial de facilitar, bloquear ou distorcer a comunicação entre outros membros da rede.
- **Robustez da Rede**: A falha de nós com alta intermediação é mais propensa a fragmentar a rede em componentes isolados (conecta-se à teoria de [[Hubs (Nós Centrais)]] e [[Fragmentação de Rede]]).
- **Satisfação e Liderança**: O estudo correlaciona a posição de intermediação com a percepção de liderança e satisfação pessoal em grupos experimentais.

## 4. Citações Chave
- "A point in a communication network is central to the extent that it falls on the shortest path between pairs of other points."
- "The relayer has it in his power to withhold information... or to refuse to pass on requests for information."

## 5. Mapeamento para a Wiki
- **Conceitos Relacionados**: [[Hubs (Nós Centrais)]], [[Modelagem de Redes Biológicas]], [[Robustez]].
- **Implicações para o TCC**: No contexto da DP, genes com alta centralidade de intermediação podem ser "pontes" críticas entre diferentes módulos patológicos (ex: ligando [[Disfunção Mitocondrial]] e [[Via Autofagia-Lisossomo]]).
