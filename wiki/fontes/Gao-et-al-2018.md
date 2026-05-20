---
title: "Study of biological networks using graph theory"
authors: Wei Gao, Hualong Wu, Muhammad Kamran Siddiqui, Abdul Qudair Baig
year: 2018
journal: Saudi Journal of Biological Sciences
doi: 10.1016/j.sjbs.2017.11.022
type: Artigo Original (Matemático)
tags: [matematica-de-grafos, topologia, indices-topologicos, hiper-arvore]
---

# Dissecação: Gao et al. (2018)

Este artigo é extremamente técnico e foca no cálculo exato de índices topológicos baseados em distância (especificamente baseados em excentricidade) para arquiteturas específicas de redes biológicas, como a Árvore Binária (Hypertree) e a X-tree.

## 1. Topologias Analisadas
O estudo foca na topologia e conectividade da reprodução bacteriana e viral modelada por divisão binária.
- **Hypertree k-level ($HT(k)$)**: Uma árvore binária completa onde ligações horizontais são formadas (arestas irmãs) entre os filhos da mesma raiz em níveis idênticos.
- **X-tree k-level ($XT(k)$)**: Similar à hypertree, com caminhos adicionados da esquerda para a direita em todos os vértices de mesmo nível.

## 2. Métricas de Distância e Índices Calculados
Em teoria de grafos aplicada a química e biologia estrutural (Quimioinformática), mapeia-se uma estrutura a um número real positivo $f: G \rightarrow \mathbb{R}^+$ para deduzir sua reatividade. A métrica basal aqui é a **excentricidade $ec(v)$**:
$$ec(v) = \max \{d(v, u) | u \in V(G)\}$$
Onde $d(v, u)$ é a distância geodésica do caminho mais curto. A excentricidade denota a distância máxima entre um nó $v$ e qualquer outro nó na rede.

A partir de $ec(v)$, o artigo calcula exaustivamente matrizes fechadas (equações resolvidas) para:
1.  **Quarto Índice Geométrico-Aritmético ($GA_4$)**
2.  **Quarto e Sexto Índices de Zagreb ($Zg_4, Zg_6$)**
3.  **Versões Multiplicativas de Zagreb ($\Pi_4, \Pi_6$)**
4.  **Polinômios de Zagreb**
5.  **Quinto Índice Multiplicativo de Conectividade Átomo-Ligação ($ABC_5$)**

## 3. Implicações para o TCC
Embora as equações fechadas de matrizes ($GA_4$, Polinômios de Zagreb) sejam muito focadas em química estrutural e reprodução celular binária (o que foge do escopo direto de Parkinson e RNA-seq), o conceito de **Excentricidade** formalizado aqui é vital.
Na doença de Parkinson:
- Nós com baixa excentricidade (raio do grafo pequeno) podem alcançar todos os outros nós rapidamente.
- Nós com alta excentricidade são "isolados", mas em um Grafo Bipartido de Doença-Fármaco, se um hub (como [[LRRK2]]) se tornar altamente excêntrico (falha na rede celular), a intervenção da droga precisa mirar pontes estruturais vizinhas para restabelecer a conectividade.

## Fontes
- [[Modelagem de Redes Biológicas]]
