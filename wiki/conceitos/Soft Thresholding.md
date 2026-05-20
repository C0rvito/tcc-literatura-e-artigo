---
tags: [WGCNA, thresholding, topologia-scale-free, matriz-de-adjacencia, matriz-continua]
---

# Soft Thresholding

## Definição
*Soft Thresholding* (Limiar Suave) é o método matemático principal utilizado na metodologia WGCNA para converter uma matriz de correlação cruzada em uma matriz de adjacência de grafos ponderados, substituindo a velha necessidade de binarizar os dados em 1 (conectado) ou 0 (desconectado).

Invés da função *Signum* limitante (*hard thresholding*, ex: $a_{ij} = 1 \text{ se } s_{ij} > 0.8$), o *soft thresholding* usa uma elevação de potência para penalizar correlações fracas enquanto mantem a natureza contínua dos dados:

$$a_{ij} = |s_{ij}|^\beta$$

onde $s_{ij}$ é a correlação absoluta entre a expressão dos nós e $\beta$ é a potência escolhida pelo usuário.

## Contexto Biológico e Implicações na Rede
A escolha do hiperparâmetro ótimo de potência $\beta$ não é arbitrária. A função é ajustada rigorosamente de modo a garantir que a rede genômica artificial recém-construída obedeça à biologia natural do coeficiente de determinação linear, a topologia de lei de potência de [[Redes Scale-free]] ($R^2 \ge 0.80$).

Binarizar redes moleculares (usando cortes radicais) destrói uma quantidade massiva de informação da regulação transcricional fraca. O limiar suave mantém a sensibilidade total, evita a distorção artificial na relação topológica entre conectividade ($k$) e coeficiente de agrupamento, e sustenta a extração orgânica de módulos genômicos cruciais no cérebro com Doença de Parkinson sem isolamento prematuro de arestas.

## Fontes
- [[Zhang-Horvath-2005-WGCNA-Framework]]
- [[Li-et-al-2018-WGCNA]]
- [[Redes Scale-free]]
- [[Redes de Co-expressão]]