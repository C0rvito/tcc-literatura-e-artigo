---
tags: [redes-scale-free, barabasi, preferential-attachment, crescimento, auto-organizacao]
---

# Conexão Preferencial (Preferential Attachment)

## Definição
A Conexão Preferencial é um mecanismo dinâmico de crescimento de redes onde novos vértices (nós) adicionados ao sistema tendem a se conectar a vértices preexistentes de forma proporcional à conectividade (grau) que estes já possuem. Informalmente, é o fenômeno do "rico fica mais rico".

Em um modelo de evolução de rede, a probabilidade $\Pi(k_i)$ de um novo nó se conectar a um nó $i$ existente depende do grau $k_i$ do nó $i$:

$$\Pi(k_i) = \frac{k_i}{\sum_j k_j}$$

## Contexto Biológico e Implicações na Rede
Quando combinado com o crescimento contínuo da rede, este mecanismo é responsável pela auto-organização espontânea de redes complexas na chamada topologia *scale-free* (livre de escala), cuja distribuição de conectividade segue uma lei de potência ($P(k) \sim k^{-\gamma}$).

Em biologia de sistemas e redes genéticas, a conexão preferencial explica a emergência de [[Hubs (Nós Centrais)]]. Genes que adquiriram funções importantes cedo na evolução acumularam mais conexões (interações proteicas, controle regulatório) ao longo do tempo. Na Doença de Parkinson, mutações em hubs ancestrais (como *SNCA* ou *LRRK2*) causam falhas generalizadas, pois milhares de cascatas de sinalização acoplaram-se a eles devido a essa força topológica seletiva evolutiva.

## Fontes
- [[Barabasi-Albert-1999]]
- [[Redes Scale-free]]
- [[Hubs (Nós Centrais)]]