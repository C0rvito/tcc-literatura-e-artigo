---
title: "Tissue specific LRRK2 interactomes reveal a distinct striatal functional unit"
authors: Yibo Zhao, Nikoleta Vavouraki, Ruth C. Lovering, Valentina Escott-Price, Kirsten Harvey, Patrick A. Lewis, Claudia Manzoni
year: 2023
journal: PLoS Computational Biology
doi: 10.1371/journal.pcbi.1010847
type: Artigo Original (Biologia de Sistemas)
tags: [lrrk2, ppi, transcriptomica, redes-tecido-especificas, striatum, wgcna, rabs]
---

# Dissecação: Zhao et al. (2023)

Este estudo constrói um interatoma geral da proteína LRRK2 (LRRK2$_{int}$) a partir de bases de dados de interação proteína-proteína (PPI) e o filtra utilizando perfis de expressão e co-expressão (RNA-seq) em 15 tecidos saudáveis humanos (11 regiões cerebrais e 4 tecidos periféricos). O objetivo é identificar "unidades funcionais" tecido-específicas de LRRK2, essenciais para entender por que as mutações no LRRK2 causam a Doença de Parkinson (que afeta primariamente o estriado).

## 1. Metodologia Detalhada
- **Construção do Interatoma Geral**: Interações extraídas de 3 bases (PINOT, HIPPIE, MIST). Após filtragem rigorosa (interações replicadas por mais de 1 método ou em mais de 1 publicação), chegou-se a um "core" de **407 interatores LRRK2**.
- **Dados Transcriptômicos**: RNA-Seq de 11 regiões cerebrais (incluindo caudado, putâmen, núcleo accumbens, substância negra) e 4 tecidos periféricos do banco de dados **GTEx** (V8).
- **Métricas Computacionais**:
  - **Expressão Diferencial (DEA)**: Compara a expressão absoluta dos interatores entre pares de tecidos.
  - **Co-expressão**: Correlação de Pearson entre a expressão de LRRK2 e a expressão de cada interator, comparada contra distribuições nulas (1000 conjuntos aleatórios de genes).

## 2. Resultados Quantitativos e Topológicos
- **Dicotomia Cérebro vs. Periferia**: A expressão geral do interatoma de LRRK2 agrupa-se (hierarchical clustering) separando claramente o Sistema Nervoso Central (SNC) dos tecidos periféricos (sangue, fígado, pulmão, rim).
- **Unidade Funcional Estriatal**: As regiões do estriado (putâmen, caudado e núcleo accumbens) agruparam-se juntas com alta similaridade tanto em níveis de expressão quanto em co-expressão com LRRK2.
  - **Surpresa Quantitativa**: Os interatores "core" de LRRK2 apresentaram uma expressão absoluta relativamente **baixa** nessas regiões do estriado (apenas ~4 a 7% do LRRK2$_{int}$ tinha níveis altos). No entanto, o nível de **co-expressão com LRRK2 foi extremamente alto** (coeficientes $\ge 0.7$ para ~35 a 49% do interatoma).
  - Em contrapartida, no cerebelo, os interatores eram altamente expressos (32%), mas fracamente co-expressos com LRRK2 (16.7%).

## 3. Dissecação Fármaco-Rede e Vias Específicas
- **Enriquecimento Estriatal**: A sub-rede do estriado foi funcionalmente enriquecida para "desenvolvimento do mesencéfalo" e "organização do lamelipódio" (via de remodelação do citoesqueleto da actina/microtúbulos).
- **A Família das GTPases RAB**: 13 Rabs foram identificadas. O estudo dissecou a relação tecido-específica:
  - **RAB7A** e **RAB5B**: Expressão basal muito alta em quase todos os tecidos (função constitutiva na via endolisossomal).
  - **RAB29** e **RAB32**: Co-expressão altíssima com LRRK2 *especificamente* na substância negra e na medula espinhal, sugerindo uma regulação seletiva crucial para a patogênese.

## 4. Implicações para o TCC
- **Redes Multicamadas**: Este artigo justifica metodologicamente a sobreposição de dados de **Redes PPI** (físicas e estáticas) com **Redes de Co-expressão (WGCNA)** (dinâmicas e tecido-específicas).
- As entidades [[LRRK2]] e [[RHOT1]] ganham contexto: os interatores mudam seu comportamento (Party vs Date Hubs - ver [[Yu-et-al-2007-Bottlenecks]]) dependendo se a célula é do estriado ou da periferia.

## Fontes
- [[Redes de Co-expressão]]
- [[Hubs (Nós Centrais)]]
