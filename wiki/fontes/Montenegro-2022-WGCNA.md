---
title: "Gene Co-expression Network Analysis"
authors: Juan D. Montenegro
year: 2022
journal: Methods in Molecular Biology (Plant Bioinformatics)
doi: 10.1007/978-1-0716-2067-0_19
type: Capítulo de Livro / Tutorial Metodológico
tags: [WGCNA, RNA-Seq, pipeline-bioinformática, TPM, eigengenes, redes-de-co-expressao]
---

# Dissecação: Montenegro (2022) - WGCNA Pipeline

Este capítulo de livro fornece um guia passo a passo, incluindo scripts em R, sobre como processar dados brutos de RNA-Seq (fastq) até a geração de módulos de co-expressão gênica (Eigengenes) via WGCNA.

## 1. Condições Prévias e Limitações
- **Design Experimental**: A análise de co-expressão não requer réplicas biológicas para estimar variações estatísticas da mesma forma que a expressão diferencial, mas é **extremamente sensível ao viés de composição da amostra**. Ter um número desproporcional de bibliotecas para um tratamento em relação a outro distorce os padrões de co-expressão.
- **Tamanho da Amostra (N)**: O mínimo recomendado é de 30 amostras. Menos de 20 amostras é considerado fraco para o poder estatístico de WGCNA.

## 2. Pipeline Computacional Extraído
1. **Alinhamento e Contagem**: 
   - Ferramentas recomendadas: `STAR` para mapeamento (GAP-aware) no modo twopass.
   - Contagem de fragmentos: `featureCounts` (cuidando para que *paired-end reads* sejam contados como 1).
2. **Filtragem**:
   - É comum descartar genes de baixa expressão. Recomenda-se um corte brando de TPM >= 1 (ou log2(CPM) correspondente) em pelo menos $X$ amostras (ex: 3) para aliviar a carga computacional das operações de matriz ($N^2/2$).
3. **Normalização**:
   - A normalização FPKM é desaconselhada. TPM (Transcripts Per Kilobase Million) ou métodos baseados em razão (TMM do edgeR ou VST do DESeq2) são mandatórios para permitir comparação cruzada robusta entre as amostras.

## 3. Dinâmica dos "Eigengenes"
- **Definição**: O primeiro componente principal obtido a partir dos valores de expressão de todos os genes pertencentes a um módulo. Funciona como um vetor resumo do comportamento do módulo ao longo de todas as amostras.
- **Merge de Módulos (Corte Dinâmico da Árvore)**: Muitas vezes o agrupamento hierárquico baseado em TOM particiona a rede em demasiados sub-módulos redundantes. A correlação de *Eigengenes* é usada para decidir se módulos vizinhos na árvore dendrograma têm perfis tão parecidos que devem ser unificados (*merged*) (Ex: cutHeight de 0.20 equivale a uma correlação de 80% entre Eigengenes).

## 4. Implicações para o TCC
- **Preparo de Dados**: Fornece o protocolo exato (TPM/TMM) de como você deve limpar e transformar sua própria matriz de contagens antes de jogar os dados no WGCNA.
- **Análise Final**: Explica como o *Module Eigengene* pode ser usado para relacionar módulos com fenótipos de Parkinson ou fazer o cruzamento inter-espécies/tecidos de forma compacta (ao invés de correlacionar cada gene).

## Fontes
- [[Redes de Co-expressão]]
- [[Modelagem de Redes Biológicas]]
