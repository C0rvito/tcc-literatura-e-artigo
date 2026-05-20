---
tags: [algoritmos, enriquecimento-de-vias, analise-topologica, enrichnet]
---

# Random Walk with Restart (RWR)

## Definição
O *Random Walk with Restart* (RWR), ou Caminhada Aleatória com Reinício, é um algoritmo probabilístico baseado em grafos que modela a topologia global da rede com respeito a pontos de origem selecionados. 

O RWR simula uma "partícula" imaginária que começa em nós sementes (*seed nodes*). Em cada iteração discreta de tempo, a partícula pode:
1. Navegar aleatoriamente para um vizinho adjacente.
2. Com uma probabilidade de reinício $p$ (ex: $p=0.9$), ser "teleportada" de volta ao seu conjunto original de nós sementes.

O estado estacionário (*steady-state probability*) dessa distribuição iterativa fornece uma métrica robusta sobre a proximidade topológica entre os sementes e qualquer outro nó no interactoma.

## Contexto Biológico e Implicações na Rede
Diferente das análises de enriquecimento padrão (como Testes ORA de Fisher que usam apenas interseção binária de genes), o RWR e ferramentas baseadas nele (como o EnrichNet) levam em consideração a arquitetura física da rede. 

No contexto da patologia do Parkinson, a aplicação do RWR partindo de um conjunto restrito de mutações ou variações genéticas causadoras mapeia a propagação do "impacto de doença" pelos vizinhos biológicos. Isso é capaz de associar e descobrir vias que sofrem distúrbios secundários (como vias imunes de Interleucina) que convergem na morte celular e contribuem para o quadro de [[Convergência Fenotípica]], superando as abordagens conservadoras de estatística simples.

## Fontes
- [[Glaab-et-al-2012-EnrichNet]]
- [[Modelagem de Redes Biológicas]]
- [[Grafo de Conhecimento]]