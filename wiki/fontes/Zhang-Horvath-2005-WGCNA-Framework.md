---
title: "A General Framework for Weighted Gene Co-Expression Network Analysis"
authors: Bin Zhang, Steve Horvath
year: 2005
journal: Statistical Applications in Genetics and Molecular Biology
doi: 10.2202/1544-6115.1128
type: Artigo Original (Teórico/Metodológico)
tags: [WGCNA, redes-ponderadas, TOM, topologia-scale-free, matematica-de-grafos, coeficiente-de-agrupamento]
---

# Dissecação: Zhang & Horvath (2005) - WGCNA

Este é o documento fundacional da Metodologia WGCNA. Ele estabelece matematicamente as vantagens de usar limiares suaves (redes ponderadas - *soft thresholding*) em oposição a limiares rígidos (redes não-ponderadas - *hard thresholding*) na análise de co-expressão gênica.

## 1. Funções de Adjacência (Hard vs Soft Thresholding)
A matriz de adjacência determina o quão forte é a conexão entre dois genes ($i$ e $j$), partindo da correlação inicial de expressão $s_{ij} = |cor(i,j)|$.

- **Unweighted (Hard)**: Usa a função Signum. Os valores são binarizados (0 ou 1) com base num corte $\tau$. Resulta em extrema perda de informação biológica e alta sensibilidade ao limite escolhido.
    $$a_{ij} = signum(s_{ij}, \tau) \equiv \begin{cases} 1 & \text{if } s_{ij} \ge \tau \\ 0 & \text{if } s_{ij} < \tau \end{cases}$$

- **Weighted (Soft)**: Usa a função Power. Preserva a natureza contínua da correlação. Valores fortes são mantidos e os fracos são rapidamente diluídos, não havendo descarte sumário.
    $$a_{ij} = power(s_{ij}, \beta) \equiv |s_{ij}|^\beta$$

## 2. O Critério da Topologia Scale-Free
Como determinar o $\beta$ (ou o $\tau$) adequado? Os autores defendem que a rede resultante **deve obedecer à topologia biológica natural**. 
O coeficiente de ajuste da regressão linear ($R^2$) entre $log_{10}(p(k))$ e $log_{10}(k)$ é usado. Os autores recomendam escolher um $\beta$ onde o $R^2 \ge 0.80$ e a curva de saturação se nivele, provando que os graus da rede seguem uma distribuição em lei de potência.

## 3. Generalização de Medidas Topológicas para Valores Contínuos
O artigo translada conceitos clássicos de teoria de grafos para redes ponderadas:

### 3.1 Conectividade Ponderada ($k_i$)
Invés de simplesmente contar arestas (1s), soma-se as forças das conexões entre 0 e 1.
$$k_i = \sum_{j=1}^n a_{ij}$$

### 3.2 Matriz de Sobreposição Topológica (TOM - $\omega_{ij}$)
A medida de TOM avalia quão interconectados estão os vizinhos comuns de dois nós. É o motor por trás do agrupamento em módulos de co-expressão.
$$\omega_{ij} = \frac{l_{ij} + a_{ij}}{\min\{k_i, k_j\} + 1 - a_{ij}}$$
onde $l_{ij} = \sum_u a_{iu}a_{uj}$ representa o produto das forças adjacentes aos nós compartilhados. No modelo não ponderado, $l_{ij}$ é apenas o número de vizinhos em comum.

### 3.3 Coeficiente de Agrupamento (*Clustering Coefficient* - $C_i$)
Enquanto em redes não-ponderadas o Coeficiente de Agrupamento ($C_i$) e a Conectividade ($k_i$) são fortemente correlacionados inversamente (nós muito conectados perdem o agrupamento local), os autores provam que, ao adotar limiares suaves (*soft*), **essa restrição artificial desaparece**. $C_i$ e $k_i$ tornam-se constantes independentes em hubs dentro do mesmo módulo.
$$C_i = \frac{n_i}{\pi_i}$$
(A dedução para $\pi_i$ e $n_i$ ponderados contorna anomalias matemáticas geradas pelo corte binário).

## 4. Implicações para o TCC
- Justifica cientificamente o porquê de redes de co-expressão simples (acima de $0.7$, liga; abaixo, não liga) falharem miseravelmente em análises de DP: elas quebram as premissas matemáticas do agrupamento topológico e criam artefatos analíticos inversos.
- Fornece as definições matemáticas sólidas para a criação de [[Redes de Co-expressão]] e a detecção dos sub-módulos biológicos de patologia.

## Fontes
- [[Redes de Co-expressão]]
- [[Redes Scale-free]]
- [[Modelagem de Redes Biológicas]]
