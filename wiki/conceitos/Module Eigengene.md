---
tags: [WGCNA, reducao-de-dimensionalidade, PCA, agrupamento, RNA-Seq]
---

# Module Eigengene (ME)

## Definição
O *Module Eigengene* (Eigengene do Módulo, ou ME) é a métrica fundamental da redução de dimensionalidade utilizada em Redes Ponderadas de Co-Expressão Gênica (WGCNA). 

Matematicamente, o ME é o **primeiro componente principal (First Principal Component)** da matriz contendo a quantificação da expressão padronizada em todos os dados pareados para os genes associados exclusivamente àquele módulo específico. 

## Contexto Biológico e Implicações na Rede
O Eigengene de um módulo age como o "perfil de gene perfeitamente representativo" (o vetor médio de comportamento transversal). Num módulo biológico construído contendo, por exemplo, mil transcritos de RNA diferentes, o vetor ME condensa o sinal macroscópico ao longo do grupo de dados pareados.

- **Merge de Módulos (Unificação Hierárquica)**: Árvores de topologia genômica podem se super-particionar excessivamente de maneira ruidosa. Ao correlacionar diferentes Eigengenes, os autores de redes avaliam se "Módulo Verde" e "Módulo Azul" possuem padrões ME funcionalmente em $> 80\% $ de sintonia; em caso positivo, o dendrograma as funde num macro-módulo único.
- **Relacionamento Fenótipo-Módulo (Module Membership)**: Calcular a correlação estatística entre o ME dos Módulos Isolados e o *status* clínico patológico (Amostra Controle Saudável *vs.* Portador de Parkinson LRRK2 mutado) propicia determinar quais ilhas inteiras de funções transcricionais (como Cascatas Endossômicas ou de Dopamina) induzem criticamente ou coexistem com a patologia. 

## Fontes
- [[Montenegro-2022-WGCNA]]
- [[Li-et-al-2018-WGCNA]]
- [[Zhang-Horvath-2005-WGCNA-Framework]]