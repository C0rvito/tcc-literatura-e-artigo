---
tags: [WGCNA, topologia, redes-ponderadas, clustering, vizinhanca]
---

# Medida de Sobreposição Topológica (TOM)

## Definição
A Medida de Sobreposição Topológica (*Topological Overlap Measure* - TOM) é uma métrica avançada de similaridade usada predominantemente em redes ponderadas. Em vez de avaliar apenas se dois nós $i$ e $j$ estão diretamente conectados (adjacência), o TOM avalia o quão interconectados estão os **vizinhos comuns** de ambos os nós.

A fórmula para redes ponderadas, onde as arestas têm forças $a_{ij} \in [0,1]$ é dada por:

$$\omega_{ij} = \frac{l_{ij} + a_{ij}}{\min\{k_i, k_j\} + 1 - a_{ij}}$$

onde:
- $l_{ij} = \sum_u a_{iu}a_{uj}$ representa o produto das forças das arestas ligando os nós $i$ e $j$ aos mesmos vizinhos compartilhados $u$.
- $k_i = \sum_{u} a_{iu}$ é o grau ponderado (conectividade) do nó $i$.

## Contexto Biológico e Implicações na Rede
No WGCNA, o TOM atua como a fundação do agrupamento hierárquico para formar módulos de co-expressão. Ele minimiza o ruído biológico: dois genes podem ter baixa correlação direta entre si por questões de ruído de RNA-Seq, mas se ambos se comunicam intensamente com o mesmo grupo de 50 genes (vizinhança compartilhada alta), o TOM os agrupará firmemente.
Para doenças complexas como o Parkinson, usar o TOM permite encontrar "Módulos de Doença" robustos, isolando agrupamentos funcionais de vias como a Autofagia-Lisossomo, mesmo quando conexões diretas individuais são fracas.

## Fontes
- [[Zhang-Horvath-2005-WGCNA-Framework]]
- [[Modelagem de Redes Biológicas]]
- [[Redes de Co-expressão]]