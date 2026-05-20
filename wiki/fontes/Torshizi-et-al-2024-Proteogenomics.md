---
title: "Proteogenomic network analysis reveals dysregulated mechanisms and potential mediators in Parkinson’s disease"
authors: Abolfazl Doostparast Torshizi, Dongnhu T. Truong, Liping Hou, Bart Smets, Christopher D. Whelan, Shuwei Li
year: 2024
journal: Nature Communications
doi: 10.1038/s41467-024-50718-x
type: Artigo Original (Proteogenômica / Redes)
tags: [proteogenomica, pQTL, gwas, lrrk2, ppi, interatoma, mediadores-indiretos, lgals3]
---

# Dissecação: Torshizi et al. (2024)

Este estudo utiliza uma abordagem de biologia de sistemas em larga escala para mapear os efeitos de variantes genéticas (identificadas por GWAS) no proteoma humano, visando descobrir mediadores proteicos diretos e indiretos da Doença de Parkinson (DP). A análise é ancorada nos dados do *UK Biobank Pharma Proteomics Project* (UKB-PPP).

## 1. Metodologia Detalhada e Pipeline de Rede
O *framework* proteogenômico foi dividido em três fases sistêmicas:
- **Associação Genética e Mapeamento pQTL**: Uso de estatísticas do GWAS de DP (UK Biobank + FinnGen) cruzadas com o mapeamento de *protein quantitative trait loci* (pQTLs) para 2.923 proteínas através de 54.219 indivíduos (o maior conjunto proteômico populacional atual).
- **Inferência Causal (Mendelian Randomization - MR)**: Identificação de 122 proteínas com vínculo causal direto à DP.
- **Modelagem de Redes (Interactoma)**: As proteínas identificadas no passo anterior foram projetadas em uma rede de Interações Proteína-Proteína (PPI) para identificar módulos densos e *mediadores indiretos* (nós de rede que não possuem um sinal genético primário GWAS, mas são estruturalmente essenciais para a via patológica).

## 2. Resultados Quantitativos
- **Desregulação de Vias Globais**: 577 proteínas associadas a pQTLs de DP enriqueceram significativamente vias de "interação citocina-receptor de citocina" e "função lisossomal" (conectando-se fortemente com a biologia estrutural de [[GBA]] e [[LRRK2]]).
- **Módulos de Rede**: A análise topológica (*hypothesis-free network analysis*) encontrou módulos abrigando 175 proteínas. Delas, a modelagem extraiu 53 proteínas associadas a pQTLs que interagem fisicamente de maneira direta com os *loci* conhecidos do GWAS.
- **Identificação de Alvos Terapêuticos**: A rede convergiu em nove proteínas cruciais com alto potencial como alvos ou biomarcadores: LGALS3, CSNK2A1, SMPD3, STX4, APOA2, PAFAH1B3, LDLR, HSPB1, BRK1.
- O gene **LGALS3** (Galectina-3) apareceu com evidências convergentes causais. Atua controlando a transição de micróglia saudável para micróglia neurodegenerativa tóxica, fazendo deste gene um alvo terapêutico promissor.

## 3. Implicações para o TCC
- **Integração de Camadas**: Reforça a importância de não olhar a genética de forma isolada. Redes PPI servem de andaime estrutural para projetar flutuações de expressão (RNA-seq ou pQTLs) a fim de encontrar gargalos (ver [[Yu-et-al-2007-Bottlenecks]]).
- A identificação de módulos e interações diretas ressalta o uso de centralidade de rede e agregação em *clusters* para expandir os achados de risco genético, alinhando-se com a tese de [[Convergência Fenotípica]].

## Fontes
- [[Modelagem de Redes Biológicas]]
- [[Hubs (Nós Centrais)]]
