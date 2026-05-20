---
tags: [motifs, topologia, subgrafos, controle-regulatorio, FFL]
---

# Motivos de Rede (Network Motifs)

## Definição
Motivos de rede (*Network Motifs*) são pequenos subgrafos (estruturas de conectividade envolvendo 3 a 5 nós) que ocorrem em uma rede empírica real com uma frequência significativamente maior do que a esperada por acaso (isto é, em modelos nulos de grafos randomizados que conservam a distribuição de grau). 

Eles representam os "blocos de construção" lógicos elementares do design topológico da rede. Algumas medidas de centralidade (como *Motif-based Centralities*) focam na participação de nós específicos nesses circuitos exatos, calculando quantas vezes um nó $v$ ocorre como componente funcional de um motivo específico $M$: $C_{mb}(v)$.

## Contexto Biológico e Implicações na Rede
Na biologia molecular (redes metabólicas, transcricionais e proteicas), motivos comuns incluem o *Feed-Forward Loop (FFL)*, o *Bi-Fan* e cadeias auto-regulatórias. 
- **Feed-Forward Loops (FFLs)**: Funcionam mecanisticamente como filtros dinâmicos de sinais (*sign-sensitive delays*). Evitam que a célula ative genes efetores caros por conta de flutuações e ruídos transientes no ambiente, respondendo apenas a perturbações consistentes.
- **Cadeias Regulatórias**: A centralidade baseada nesses subgrafos é superior a métricas como grau simples para encontrar os verdadeiros reguladores mestres globais da célula.

No Parkinson, investigar em quais motivos genéticos fundamentais os grandes hubs interagem (por exemplo, interações em FFL mediadas por [[LRRK2]] ou [[SNCA]]) ajuda a explicar como a disfunção se propaga em cascata de forma direcionada.

## Fontes
- [[Koschutzki-Schreiber-2008]]
- [[Mason-Verwoerd-2007]]
- [[Centralidade de Intermediação]]