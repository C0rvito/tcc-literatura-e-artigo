---
title: Application of Weighted Gene Co-expression Network Analysis for Data from Paired Design
authors: Jianqiang Li, Doudou Zhou, Weiliang Qiu, et al.
year: 2018
journal: Scientific Reports
doi: 10.1038/s41598-017-18705-z
type: Artigo Original (Metodológico)
tags: [WGCNA, redes-de-co-expressão, design-pareado, genes-hub, biologia-de-sistemas]
---

# Resumo: Li et al. (2018) - WGCNA em Design Pareado

Embora o artigo foque em uma modificação do WGCNA para desenhos experimentais pareados (como amostras tumorais vs. normais do mesmo paciente), ele fornece uma excelente base técnica sobre como o WGCNA funciona e como identificar genes centrais (*hubs*) em redes de co-expressão.

## 1. Metodologia Detalhada (WGCNA Pipeline)
O fluxo de trabalho padrão do WGCNA descrito no artigo inclui:
1.  **Construção da Rede**: Cálculo de uma matriz de adjacência baseada na similaridade de co-expressão (correlação de Pearson).
2.  **Limiar Suave (*Soft Thresholding*)**: Uso de uma potência $\beta$ para transformar a correlação em adjacência, garantindo que a rede obedeça a uma topologia *scale-free*.
3.  **Identificação de Módulos**: Agrupamento hierárquico baseado na Medida de Sobreposição Topológica (TOM), que captura a similaridade de "vizinhança" entre os genes.
4.  **Eigengene do Módulo (ME)**: Definição do primeiro componente principal do módulo, servindo como um perfil representativo de sua expressão.
5.  **Conectividade e Hubs**: Identificação de *hub genes* dentro de módulos correlacionados com fenótipos.

## 2. Resultados Quantitativos e Evidências
- **Validação da Correlação**: O estudo confirma que a correlação de Pearson é válida para medir a co-expressão mesmo em dados pareados.
- **Associação Módulo-Fenótipo**: Uso de Modelos Lineares de Efeitos Mistos (LMM) para associar módulos de microRNA ao status de câncer.
- **Significância do Gene (GS)**: Definida como a correlação entre o gene e o traço fenotípico. No módulo principal (*turquoise*), a GS foi altamente correlacionada com a pertinência ao módulo (*Module Membership - MM*).

## 3. Conceitos Técnicos Relevantes
- **Module Membership (MM)**: $MM(i) = cor(x_i, ME)$, mede a importância de um gene dentro do seu módulo.
- **Genes Hub**: Definidos como os nós com o maior número de arestas (grau) dentro de um módulo funcional. Falhas nesses genes afetam todos os genes conectados.
- **Escalabilidade**: O método permite reduzir milhares de genes a poucos módulos biologicamente significativos, mitigando problemas de múltiplos testes.

## 4. Citações Chave
- "Each gene is estimated on average to interact with four to eight other genes and to be involved in 10 biological functions."
- "The nodes having the largest number of edges are most important because the malfunction of this gene would affect all connected genes."

## 5. Mapeamento para a Wiki
- **Conceitos Relacionados**: [[Redes de Co-expressão]], [[Hubs (Nós Centrais)]], [[Redes Scale-free]], [[Modelagem de Redes Biológicas]].
- **Implicações para o TCC**: Fornece a base matemática para identificar os genes "maestros" em redes de Parkinson, permitindo isolar módulos de co-expressão que convergem para o fenótipo da doença.
