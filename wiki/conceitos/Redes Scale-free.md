# Redes Scale-free (*Scale-free Networks*)

- **Tipo**: Topologia de Redes / Conceito Computacional
- **Descrição**: Redes cuja distribuição de conectividade segue uma lei de potência ($P(k) \sim k^{-\gamma}$). Nessas redes, um pequeno número de nós ([[Hubs (Nós Centrais)]]) possui um número excepcionalmente alto de conexões.

## Propriedades Matemáticas
- **Inumogeneidade**: Diferente de redes aleatórias (ER), não existe um "nó típico"; a rede é dominada por hubs [[Albert-et-al-2000]].
- **Crescimento e Conexão Preferencial**: Surgem através de processos de *preferential attachment*, onde novos nós tendem a se conectar a nós já bem conectados. Este modelo foi formalizado por Barabási e Albert em 1999 [[Barabasi-Albert-1999]], [[Barabasi-Linked-2004]].
- **Distribuição Lei de Potência**: A conectividade segue $P(k) \sim k^{-\gamma}$, onde $\gamma$ geralmente varia entre 2.1 e 4 [[Barabasi-Albert-1999]].
- **Estabilidade**: Altamente tolerantes a falhas aleatórias, mas extremamente sensíveis à remoção de hubs [[Albert-et-al-2000]], [[Barabasi-Linked-2004]].

## Relevância na Doença de Parkinson
- **Mapeamento de Doenças**: Redes de co-expressão e redes metabólicas em pacientes com DP tendem a exibir propriedades *scale-free*.
- **Convergência**: A identificação de hubs em redes de iPSC permite entender como diferentes mutações convergem para desestabilizar os mesmos nós centrais, explicando a [[Convergência Fenotípica]] [[Zagare-et-al-2025]].
- **Colapso da Rede**: O acúmulo de [[SNCA]] pode ser visto como um "ataque direcionado" a hubs de sinalização neuronal, levando ao colapso funcional da rede celular.

## Fontes
- [[Albert-et-al-2000]]
- [[Zagare-et-al-2025]]
- [[Barabasi-Linked-2004]]
