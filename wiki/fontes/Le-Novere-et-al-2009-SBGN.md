---
title: "The Systems Biology Graphical Notation"
authors: Nicolas Le Novere, Michael Hucka, Huaiyu Mi, Stuart Moodie, Falk Schreiber, et al.
year: 2009
journal: Nature Biotechnology
doi: 10.1038/nbt1558
type: Artigo Original (Normatização / Framework Visual)
tags: [sbgn, diagramas-de-rede, visualizacao-biologica, semantica-de-grafos, biologia-de-sistemas]
---

# Dissecação: Le Novère et al. (2009) - SBGN

Este artigo estabelece a **Systems Biology Graphical Notation (SBGN)**, uma linguagem visual padronizada para representar de forma inequívoca processos bioquímicos e redes biológicas, a fim de evitar as ambiguidades comuns em diagramas desenhados à mão (bolhas e setas ad-hoc).

## 1. O Problema da Ambiguidade
Antes do SBGN, os diagramas em biologia molecular usavam símbolos idiossincráticos. Uma simples seta (->) poderia significar conversão química, catálise ou aumento de transcrição genética, o que impossibilita a leitura e simulação automatizada por máquinas (parsers).

## 2. As Três Linguagens Ortogonais do SBGN
O SBGN resolve a complexidade separando a biologia em três tipos de diagramas mutuamente exclusivos e complementares:

### 2.1 Process Diagram (PD - Diagrama de Processos)
- **Foco**: Eventos sequenciais, transições de estado, metabolismo.
- **Mecânica**: Representa *como* as entidades físicas se transformam. Mostra a temporalidade e as reações mecanicistas. Se uma proteína (ex: ERK) pode ser não-fosforilada ou duplamente fosforilada, cada estado *deve ser desenhado separadamente* na tela.
- **Desvantagem**: Altamente suscetível à explosão combinatória de estados.

### 2.2 Entity Relationship Diagram (ER - Diagrama de Relacionamento de Entidades)
- **Foco**: Interações e regras sem sequencialidade.
- **Mecânica**: Cada entidade (ex: ERK) é desenhada *apenas uma vez*. As interações e os estados (ex: fosforilação) "penduram" na entidade principal. Excelente para visualizar todas as influências (inibição, ativação) simultâneas em um único alvo.
- **Vantagem**: Contorna a explosão combinatória do Process Diagram.

### 2.3 Activity Flow Diagram (AF - Diagrama de Fluxo de Atividades)
- **Foco**: A influência das atividades biológicas umas sobre as outras.
- **Mecânica**: O diagrama foca puramente no impacto positivo ou negativo. A atividade da quinase A estimula a atividade de B. Sem detalhes de complexos, locais subcelulares ou estequiometria.
- **Aplicação Real**: A esmagadora maioria das redes inferidas via **WGCNA**, microarray, genômica funcional e cascatas de sinalização (que o TCC irá mapear) utiliza intrinsecamente a semântica de *Activity Flow*.

## 3. Implicações para o TCC
- Ao integrar as redes de Parkinson extraídas de organoides do mesencéfalo e o PD-KG (Zagare et al.), a topologia descoberta via *Similarity Network Fusion* é primariamente um **Activity Flow** em nível de rede global, mas quando damos "zoom" na interação entre [[LRRK2]] e [[RHOT1]], a explicação mecanicista converte-se conceitualmente em um **Entity Relationship**.
- A normatização SBGN é fundamental para guiar o design visual que você gerará com pacotes R como o *Rgraphviz* ou *Cytoscape*, pois força a eliminação de setas ambíguas.

## Fontes
- [[Modelagem de Redes Biológicas]]
- [[Grafo de Conhecimento]]
