---
title: The Importance of Bottlenecks in Protein Networks: Correlation with Gene Essentiality and Expression Dynamics
authors: Haiyuan Yu, Philip M. Kim, Emmett Sprecher, Valery Trifonov, Mark Gerstein
year: 2007
journal: PLoS Computational Biology
doi: 10.1371/journal.pcbi.0030059
type: Artigo Original (Biologia de Sistemas)
tags: [centralidade-intermediação, bottlenecks, hubs, co-expressao, essencialidade-genica, redes-regulatorias, party-hubs, date-hubs]
---

# Dissecação: Yu et al. (2007)

Este artigo investiga o papel dos *bottlenecks* (nós com alta centralidade de intermediação) em redes de interação proteína-proteína (PPI) e redes regulatórias, diferenciando-os dos tradicionais *hubs* (nós com alto grau).

## 1. Metodologia Detalhada
- **Redes Analisadas**: 
    - Rede de Interação (PPI - levedura): Arestas não-direcionadas.
    - Rede Regulatória (TF-alvo - levedura): Arestas direcionadas.
    - Outras: Redes de Fosforilação, Metabólica e Genética.
- **Definições Quantitativas**:
    - **Hubs**: Top 20% das proteínas com maior Grau de Conectividade.
    - **Bottlenecks**: Top 20% das proteínas com maior Centralidade de Intermediação (*Betweenness*).
- **Categorização Cruzada**: As proteínas foram divididas em 4 categorias:
    1.  Nonhub-nonbottlenecks
    2.  Hub-nonbottlenecks
    3.  Nonhub-bottlenecks
    4.  Hub-bottlenecks

## 2. Resultados Quantitativos e Evidências
- **Essencialidade Genética**:
    - Em **redes regulatórias** (direcionadas), a intermediação é o principal preditor de essencialidade. *Bottlenecks* são significativamente mais vitais que *hubs* comuns ($p < 10^{-4}$).
    - Em **redes de interação** (não-direcionadas), o grau (ser hub) ainda é o melhor preditor de essencialidade ($p < 10^{-267}$ para Hub-nonbottleneck vs Nonhub-nonbottleneck).
    - No entanto, se isolarmos apenas interações "permanentes" (complexos proteicos), *bottlenecks* tornam-se altamente essenciais ($p < 10^{-251}$).
- **Dinâmica de Co-expressão**:
    - **Hub-bottlenecks** (pontes inter-módulos) têm **baixa correlação de co-expressão** com seus vizinhos. Eles atuam de forma assíncrona, conectando processos diferentes no tempo e espaço (correlacionam-se com o conceito de *date hubs*).
    - **Hub-nonbottlenecks** (membros centrais de um complexo isolado) têm **alta co-expressão** com seus vizinhos. Atuam simultaneamente (*party hubs*).

## 3. Dinâmica de Interações
- **Interações Permanentes**: Interações físicas estáveis (ex: subunidades do proteassomo). *Bottlenecks* aqui mantêm o complexo estruturalmente íntegro.
- **Interações Transitórias / Transdução de Sinal**: Vias como quinases (ex: MAP quinases). *Bottlenecks* aqui (como o gene *CAK1* citado no artigo) são cruciais para o fluxo de informação entre diferentes vias regulatórias.

## 4. Fórmulas de Algoritmos Utilizados
- O artigo utiliza a fórmula de centralidade baseada em caminhos mais curtos, introduzida por Freeman e otimizada por Newman & Girvan:
  $$b_j = \sum_{k} \frac{p_k}{p_j}$$
  Onde a intermediação de um nó $j$ é a soma dos fluxos que passam por ele para alcançar os nós predecessores $k$.

## 5. Citações Chave
- *"Bottlenecks correspond to the dynamic components of the interaction network—they are significantly less well coexpressed with their neighbors than nonbottlenecks, implying that expression dynamics is wired into the network topology."*
- *"We determined that it is the betweenness that is a stronger determinant of the essentiality of a protein in the regulatory network, not the degree."*

## 6. Mapeamento para a Wiki
- **Conceitos Atualizados**: [[Hubs (Nós Centrais)]] (adição de *date* vs *party* hubs), [[Redes de Co-expressão]] (relação entre intermediação e falta de co-expressão local).
- **Implicações para o TCC**: O artigo fornece a justificativa perfeita para buscar nós de alta intermediação (*bottlenecks*) nas redes de DP: eles são os prováveis causadores de disfunção inter-módulo (ex: falha de um sinal entre a mitocôndria e o lisossomo), mesmo que não tenham o maior número absoluto de conexões.
