---
title: Error and attack tolerance of complex networks
authors: Réka Albert, Hawoong Jeong, Albert-László Barabási
year: 2000
journal: Nature
doi: 10.1038/35019019
type: Letter
tags: [redes-scale-free, robustez, tolerancia-a-erros, vulnerabilidade-a-ataques, internet, WWW, redes-biologicas]
---

# Resumo: Albert et al. (2000)

Este artigo seminal explora a estabilidade estrutural de redes complexas, comparando especificamente redes **exponenciais (aleatórias)** e redes **scale-free** (como a Internet, a WWW e redes metabólicas celulares).

## 1. Metodologia Detalhada
- **Modelagem**: Comparação entre o modelo de Erdős–Rényi (ER) para redes exponenciais e o modelo de Barabási-Albert para redes scale-free (baseado em crescimento e conexão preferencial).
- **Simulações**:
    - **Falhas Aleatórias**: Remoção de uma fração *f* de nós selecionados aleatoriamente.
    - **Ataques Direcionados**: Remoção de nós em ordem decrescente de conectividade (grau *k*).
- **Dados Reais**: Análise de mapas topográficos da Internet (6.209 nós) e da World-Wide Web (325.729 nós).

## 2. Resultados Quantitativos e Evidências
- **Classes de Redes**:
    - **Redes Exponenciais**: Conectividade homogênea (distribuição de Poisson). A maioria dos nós tem aproximadamente o mesmo número de conexões.
    - **Redes Scale-free**: Conectividade inumogênea (lei de potência $P(k) \sim k^{-\gamma}$). Poucos nós ("hubs") possuem um número excepcionalmente alto de conexões.
- **Tolerância a Erros (Falhas Aleatórias)**:
    - Redes scale-free são surpreendentemente robustas. A remoção de até **5%** dos nós aleatoriamente quase não afeta o diâmetro da rede.
    - Isso ocorre porque a grande maioria dos nós tem poucas conexões; sua perda não altera a topologia global.
- **Vulnerabilidade a Ataques (Remoção de Hubs)**:
    - Redes scale-free são extremamente sensíveis a ataques direcionados aos hubs. A remoção de apenas **5%** dos nós mais conectados dobra o diâmetro da rede e leva à fragmentação catastrófica.
    - Em contraste, redes exponenciais respondem de forma similar tanto a falhas quanto a ataques devido à sua homogeneidade.

## 3. Aplicações Biológicas
- O artigo destaca que organismos simples persistem e se reproduzem apesar de intervenções drásticas, uma tolerância a erros atribuída à **robustez da rede metabólica subjacente**, que exibe propriedades scale-free.

## 4. Citações Chave
- "Error tolerance is not shared by all redundant systems: it is displayed only by a class of inhomogeneously wired networks, called scale-free networks."
- "The stability of these and other complex systems is often attributed to the redundant wiring of the functional web."

## 5. Mapeamento para a Wiki
- **Entidades Relacionadas**: [[Hubs]], [[Redes Metabólicas]].
- **Conceitos Chave**: [[Redes Scale-free]], [[Robustez]], [[Convergência Fenotípica]] (analogia topológica), [[Fragmentação de Rede]].
