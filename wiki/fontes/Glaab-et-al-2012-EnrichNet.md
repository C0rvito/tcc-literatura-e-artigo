---
title: "EnrichNet: network-based gene set enrichment analysis"
authors: Enrico Glaab, Anaïs Baudot, Natalio Krasnogor, Reinhard Schneider, Alfonso Valencia
year: 2012
journal: Bioinformatics
doi: 10.1093/bioinformatics/bts389
type: Artigo Original (Metodológico/Ferramenta)
tags: [enriquecimento-de-vias, random-walk, RWR, grafos, biologia-de-sistemas]
---

# Dissecação: Glaab et al. (2012) - EnrichNet

Este artigo introduz o **EnrichNet**, uma ferramenta que integra estatísticas baseadas em grafos e redes moleculares para realizar análises de enriquecimento de conjuntos de genes, superando as limitações da Análise de Super-representação clássica (Over-Representation Analysis - ORA).

## 1. O Problema das Abordagens Clássicas (ORA)
As abordagens clássicas, como o Teste Exato de Fisher, baseiam-se na contagem de interseções entre um conjunto de genes alvo (ex: genes mutados no Parkinson) e um conjunto de genes de referência (ex: via KEGG). 
- **Limitações**: Elas não conseguem detectar associações quando a interseção é vazia ou muito pequena. Ignoram a estrutura física da rede (genes vizinhos que interagem fortemente mas que não têm a mesma anotação direta) e têm baixo poder discriminativo.

## 2. Metodologia Detalhada (O Algoritmo EnrichNet)
O EnrichNet supera as limitações mapeando os genes alvo em um interactoma humano (como o STRING) e avaliando a proximidade da rede.
- **Algoritmo Central**: *Random Walk with Restart* (RWR) - Caminhada Aleatória com Reinício.
- **Mecanismo**: Uma partícula imaginária itera a partir de nós semente (seed nodes - o conjunto de genes alvo). Em cada passo, ela pode se mover para um vizinho aleatório ou reiniciar nos nós semente com probabilidade $p$ (EnrichNet usa $p=0.9$ para focar na vizinhança local). A probabilidade de estado estacionário (steady-state) reflete a proximidade estrutural entre os alvos e os conjuntos de referência.
- **Métrica de Distância (Xd-distance)**: Mede o desvio da distribuição de scores (obtidos pelo RWR) de uma via específica em relação à distribuição média (o "background model" do restante da rede).
  $$Xd = \sum_{i=1}^n \frac{P_{ic} - P_{ia}}{i \cdot n}$$

## 3. Resultados Quantitativos e Evidências
- **Descoberta de Associações Ocultas**: A abordagem identificou conexões biológicas não capturadas pelo teste de Fisher clássico ($Q-value > 0.05$).
- **Aplicação ao Parkinson (PD)**: Os autores testaram o EnrichNet em um conjunto de genes conhecidos implicados na Doença de Parkinson. O algoritmo revelou uma forte conexão com a via de *regulação do processo biossintético da interleucina-6* (GO:0045408) com um XD-score de 0.77 (significativo), mesmo havendo apenas um gene na interseção exata (IL1B). Isso corrobora evidências clínicas de inflamação no líquor de pacientes com DP.

## 4. Implicações para o TCC
O TCC do usuário utiliza redes de co-expressão para gerar módulos. Como interpretar biologicamente o que um módulo de 100 genes faz?
- **O Papel do RWR**: Utilizar metodologias inspiradas pelo EnrichNet, onde os *hub genes* de Parkinson são os "seed nodes" num RWR, pode revelar como a *Disfunção Mitocondrial* afeta vias distantes (como a do Lisossomo) mapeando as cascatas de sinalização, consolidando a teoria da [[Convergência Fenotípica]].

## Fontes
- [[Redes de Co-expressão]]
- [[Modelagem de Redes Biológicas]]
