---
title: "A network-based systems genetics framework identifies pathobiology and drug repurposing in Parkinson’s disease"
authors: Lijun Dou, Zhenxing Xu, Jielin Xu, Chengxi Zang, Chang Su, Andrew A. Pieper, et al.
year: 2025
journal: npj Parkinson's Disease
doi: 10.1038/s41531-025-00870-y
type: Artigo Original (Farmacologia de Redes / Deep Learning)
tags: [sistemas-genéticos, deep-learning, drug-repurposing, xQTL, simvastatina, ppi, network-medicine]
---

# Dissecação: Dou et al. (2025)

Este artigo introduz um modelo de *Deep Learning* fundamentado em topologia de redes (NETTAG expandido) para integrar dados multômicos, prever novos genes de risco para a Doença de Parkinson e redirecionar fármacos (*drug repurposing*).

## 1. Metodologia: Framework de Rede e Deep Learning
- **Rede Interatômica Base**: Construção de um vasto interactoma PPI com 351.444 interações físicas entre 17.706 proteínas humanas, extraídas de múltiplas bases estruturais, binárias e complexos proteicos (BioPlex, Instruct, Y2H).
- **Atributos dos Nós (xQTLs)**: Associações genéticas não codificantes do GWAS foram vinculadas a genes através de 5 níveis de regulação: expressão (eQTL), proteína (pQTL), *splicing* (sQTL), metilação (meQTL) e acetilação de histonas (haQTL).
- **Algoritmo de Aprendizado Profundo**: Utilizou *Graph Neural Networks* (GNN). Especificamente, a topologia da PPI forneceu a arquitetura. O estado de um nó (proteína) considerou os vizinhos diretos (1ª ordem) e também de 2ª ordem para aprimorar a capacidade de extrair agrupamentos de mesma função sem saturar a rede.

## 2. Resultados Quantitativos e Evidências Farmacológicas
- **Genes de Risco Inferidos**: A rede priorizou 175 genes como *pdRGs* (Parkinson's Disease likely Risk Genes). Entre eles encontram-se clássicos como [[SNCA]], [[LRRK2]], mas também genes metabólicos/imunes como CTSB, DGKQ e CD44.
- **Validação Transcriptômica (scRNA-seq)**: A validação em núcleo único (*single-nuclei RNA-seq*) da substância negra mostrou que o conjunto de 175 genes é fortemente diferencial entre neurônios dopaminérgicos, micróglia e astrócitos em cérebros de pacientes.
- **Redirecionamento de Fármacos (*Network Proximity*)**:
  - Distâncias topológicas (caminhos mais curtos - *shortest paths*) entre alvos de medicamentos aprovados (FDA) e o módulo de 175 genes de DP foram calculadas.
  - De 2.938 candidatos, o *screening* de proximidade filtrou 70 medicamentos.
  - **Simvastatina**: Identificada como um alvo primário. A validação em vida real com Registros Eletrônicos de Saúde (EHR de 15 milhões de pacientes) provou que seu uso está associado a uma redução no risco de progressão severa (HR = 0.91 para quedas, HR = 0.88 para demência) após ajuste pareado por *Propensity Score Matching* (267 covariáveis).

## 3. Implicações para o TCC
- **Identificação e Uso de "Distância de Rede"**: As fórmulas e o conceito de usar "Network Proximity" ($d(S,T)$) entre um módulo biológico e alvos de fármacos são fundamentais para o objetivo translacional do seu trabalho de TCC.
- **Célula Específica**: Corrobora a hipótese extraída no estudo [[Zhao-et-al-2023-LRRK2-Tissue]], evidenciando que as redes e os genes não agem no vácuo global, mas sim de maneira tipo-celular e tecido-dependente.

## Fontes
- [[Modelagem de Redes Biológicas]]
- [[Convergência Fenotípica]]
- [[Redes Scale-free]]
