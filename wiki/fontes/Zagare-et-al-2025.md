---
title: Deciphering shared molecular dysregulation across Parkinson’s disease variants using a multi-modal network-based data integration and analysis
authors: Alise Zagare, Irina Balaur, Adrien Rougny, et al.
year: 2025
journal: npj Parkinson's Disease
doi: 10.1038/s41531-025-00914-3
type: Artigo Original
tags: [Grafo-de-Conhecimento, PD-KG, organoides-de-mesencefalo, iPSC, DP-idiopatica, sinalizacao-ROBO, multi-modal, convergencia-fenotipica, scRNA-seq]
---

# Dissecação: Zagare et al. (2025)

Este artigo constrói um Grafo de Conhecimento centrado na Doença de Parkinson (PD-KG) para integrar dados experimentais multi-ômicos (imagem e transcriptômica) de organoides de mesencéfalo específicos de pacientes. O estudo é o mapa base para a identificação da sinalização ROBO como via de convergência.

## 1. Metodologia Detalhada
- **Plataforma do Grafo**: Neo4j, integrando bancos de dados públicos: Reactome, IntAct, DisGeNet, DGIdb, UniProtKB.
- **Amostragem em DPI (scRNA-seq)**: Organoides de mesencéfalo de 6 pacientes com DP Idiopática (DPI) (3 homens, 3 mulheres) e 6 controles saudáveis. Sequenciamento no dia 50 de cultura.
- **Dados Monogênicos (Bulk RNA-seq)**: Integração com dados previamente publicados para *LRRK2-G2019S* (dia 35), *3xSNCA* (dia 30), *GBA-N370S* (dia 30) e *MIRO1-R272Q* (dia 30).
- **Redução de Dimensionalidade e Integração**: Utilizou-se o algoritmo *Similarity Network Fusion* (SNF) para agrupar linhagens de DPI misturando transcriptômica e imagem de alto conteúdo.

## 2. Resultados Quantitativos e Topologia do PD-KG
- **Métricas do PD-KG**: O grafo abriga **3610 nós** (genes, drogas, vias, doenças) e **8512 arestas** (interações).
- **Assinaturas Gênicas Compartilhadas**:
    - **Nenhum gene (DEGs)** foi compartilhado por todos os 4 conjuntos de dados monogênicos simultaneamente.
    - **25 genes** foram diferencialmente expressos em *pelo menos dois* dos quatro conjuntos monogênicos.
    - **15 genes** foram compartilhados exclusivamente entre as linhas *LRRK2-PD* e *MIRO1-PD*, indicando alta similaridade mecanicista.
- **Hubs de Citoesqueleto**: Seis genes (MORF4L2, EPHA5, ACTB, ACTG1, TUBA1A, TUBB2B) tiveram o maior envolvimento em vias dentro do PD-KG, associando-se a 69 vias.
- **Estratificação da DPI**:
    - No clustering não supervisionado de scRNA-seq, casos de DPI (como IPD e LRRK2-PD) frequentemente clusterizam perto do eixo zero da PCA, sugerindo mecanismos mais similares.
    - A desregulação transcriptômica em DPI reflete os defeitos monogênicos particularmente nas populações de **células gliais** (glia radial, astrócitos e oligodendrócitos).

## 3. Descoberta de Redes Convergentes
- **Sinalização ROBO e Axonogênese**: Identificada através da Análise de Sobreposição (ORA). As mutações convergem na desregulação de receptores ROBO (ex: *ROBO2* estava presente nos datasets de MIRO1 e LRRK2). Esta via afeta o crescimento axonal e a resposta do citoesqueleto.
- **Translocação de GLUT4**: Módulo de regulação metabólica também compartilhado, apontando para a ligação entre falha mitocondrial e glicólise.

## 4. Análise Fármaco-Rede (Drogas Alvo)
Através do banco DGIdb no PD-KG, 14 drogas existentes foram mapeadas para os genes desregulados, representando candidatas a *drug repurposing*:
- **Antineoplásicos**: Thalidomide, Plerixafor, Midostaurin, Docetaxel Anhydrous, Cisplatin, Carfilzomib, Bortezomib, Bevacizumab-AwwB.
- **Outros**: Ácido 4-fenilbutírico (distúrbios metabólicos), Hidroclorotiazida (diurético), Resveratrol, Quercetina, Ataluren.

## 5. Limitações Críticas
- **Heterogeneidade Temporal**: Dados de transcriptômica monogênica foram adquiridos apenas em um "time point" inicial (dia 30-35), enquanto os dados de imagem variavam até o dia 180, limitando a correlação de causa e efeito ao longo do envelhecimento in vitro.
- **Assinatura Limitada**: Apenas proteínas centrais limitadas (ex: tirosina hidroxilase - TH) foram sobrepostas completamente na análise de imagem em todos os quatro experimentos monogênicos.

## 6. Citações Chave
- *"Interestingly, 15 of these 25 genes were shared between LRRK2-PD and MIRO1-PD datasets, suggesting a higher similarity of transcriptomic dysregulation."*
- *"We identified significant DEGs associated with the SLIT-ROBO pathway also in other monogenic PD datasets and in the IPD dataset, suggesting that SLIT/ROBO might play an important role in PD independently of disease aetiology."*

## 7. Mapeamento de Entidades
- **Genes**: [[SNCA]], [[LRRK2]], [[GBA]], [[RHOT1]], [[ROBO2]], [[ACTB]], [[TUBA1A]], [[MORF4L2]].
- **Vias/Conceitos**: [[Grafo de Conhecimento]], [[Organoides de Mesencéfalo]], [[Sinalização ROBO]], [[Convergência Fenotípica]].
