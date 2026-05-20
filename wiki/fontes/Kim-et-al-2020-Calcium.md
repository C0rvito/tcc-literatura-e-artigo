---
title: "Defects in mRNA Translation in LRRK2-Mutant hiPSC-Derived Dopaminergic Neurons Lead to Dysregulated Calcium Homeostasis"
authors: Jungwoo Wren Kim, Xiling Yin, Aanishaa Jhaldiyal, Nicholas T. Ingolia, Ted M. Dawson, Valina L. Dawson, et al.
year: 2020
journal: Cell Stem Cell
doi: 10.1016/j.stem.2020.08.002
type: Artigo Original (Biologia Celular e Molecular)
tags: [lrrk2, calcio, iPSC, ribossomo, traducao-mRNA, vgcca, snc]
---

# Dissecação: Kim et al. (2020)

Este estudo mecanicista liga diretamente a mutação patogênica LRRK2 G2019S à hiperatividade na tradução de mRNAs específicos, resultando na desregulação do cálcio intracelular em neurônios dopaminérgicos humanos. 

## 1. Metodologia Detalhada
- **Modelo Celular**: Neurônios dopaminérgicos (DA) derivados de iPSCs humanas. Comparação entre linhas de pacientes com a mutação G2019S LRRK2 e controles saudáveis (incluindo linhas isogênicas com a mutação corrigida via CRISPR).
- **Ribosome Profiling (Ribo-seq)**: Método para sequenciar fragmentos de mRNA protegidos por ribossomos, quantificando a eficiência de tradução (TE) independentemente dos níveis de transcrição (RNA-seq).
- **Métricas Fisiológicas**: Medição de cálcio intracelular usando imagem radiométrica (Fura-2, Fluo-4) e *patch-clamp* (para medir correntes transmembrana).

## 2. Resultados Quantitativos e Mecanísticos
- **Perfil Traducional Alterado**: A mutação LRRK2 G2019S induz um viés na maquinaria de síntese proteica. Genes cuja tradução (TE - *Translation Efficiency*) subiu significativamente nas células mutantes estão ligados a canais de cálcio dependentes de voltagem (VGCCs) e receptores de glutamato.
- **Sobrecarga de Cálcio**: Neurônios DA mutantes exibem níveis citosólicos de cálcio consideravelmente maiores e correntes aumentadas através dos canais L-VGCC. O tratamento com isradipina (antagonista L-VGCC) resgatou a homeostase de cálcio.
- **A Mecânica Estrutural (O Hub Ribossomal)**: 
  - LRRK2 hiperativo fosforila excessivamente a proteína ribossomal S15 (uS19) no resíduo T136.
  - O estudo descobriu que mRNAs contendo **estruturas secundárias complexas na região 5' UTR** (energia de dobramento < -350 kcal/mol) são traduzidos *muito mais rapidamente* pelos ribossomos com S15 fosforilado.
  - Casualmente, os mRNAs dos canais de cálcio L-VGCC possuem 5' UTRs altamente complexos, explicando por que suas proteínas superabundam e matam a célula de exaustão metabólica.

## 3. Implicações para o TCC e as Redes
- **A via LRRK2 -> Ribossomo -> Cálcio**: Este artigo fornece a "prova viva" em bancada das conexões teóricas detectadas pelo PD-KG e pelo WGCNA (ver [[Zhao-et-al-2024-LRRK2]]). A alteração no "Módulo Azul" (relacionado à função ribossomal e síntese proteica) discutida nas redes transcriptômicas esporádicas e genéticas ganha base mecanicista aqui.
- A mutação cria um **gargalo de intermediação** (*bottleneck*, ver [[Yu-et-al-2007-Bottlenecks]]) no fluxo de informação: o ribossomo alterado atua como um filtro disfuncional, elevando seletivamente a expressão de genes do metabolismo de cálcio.

## Fontes
- [[Convergência Fenotípica]]
- [[Disfunção Mitocondrial]] (indiretamente, pela sobrecarga gerada pelo excesso de cálcio)
