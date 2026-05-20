---
title: Emergence of Scaling in Random Networks
authors: Albert-László Barabási, Réka Albert
year: 1999
journal: Science
doi: 10.1126/science.286.5439.509
type: Artigo Original (Seminal)
tags: [redes-scale-free, barabasi, preferential-attachment, lei-de-potencia, auto-organizacao]
---

# Resumo: Barabási & Albert (1999)

Este artigo é a fundação teórica das redes *scale-free*. Os autores demonstram que redes reais não seguem a distribuição aleatória de Erdős-Rényi, mas sim uma distribuição de conectividade que segue uma lei de potência.

## 1. Metodologia Detalhada
- **Análise Empírica**: Investigação da topologia de grandes redes reais:
    - World Wide Web (WWW): > 300.000 nós.
    - Rede de colaboração de atores de cinema: > 212.000 nós.
    - Rede de distribuição de energia dos EUA: 4.941 nós.
    - Rede de citações científicas.
- **Modelagem Matemática**: Desenvolvimento de um modelo estocástico que incorpora a dinâmica de crescimento da rede.

## 2. Resultados Quantitativos e Evidências
- **Distribuição de Conectividade ($P(k)$)**: Independentemente do sistema, a probabilidade de um nó ter $k$ conexões decai conforme uma lei de potência: $P(k) \sim k^{-\gamma}$.
    - Para atores: $\gamma \approx 2.3$.
    - Para a WWW: $\gamma \approx 2.1$.
    - Para a rede de energia: $\gamma \approx 4$.
- **Mecanismos de Emergência**: Os autores identificam dois ingredientes necessários para a formação de redes *scale-free*:
    1.  **Crescimento (Growth)**: A rede se expande continuamente pela adição de novos vértices.
    2.  **Conexão Preferencial (Preferential Attachment)**: Novos vértices tendem a se conectar a nós que já possuem alta conectividade (o efeito "rico fica mais rico").
- **Auto-organização**: Redes grandes se organizam espontaneamente em um estado *scale-free*, independentemente dos detalhes individuais do sistema.

## 3. Limitações e Observações
- Modelos anteriores (Erdős-Rényi e Watts-Strogatz) falham por assumirem um número fixo de nós e conexões aleatórias uniformes, o que resulta em distribuições de Poisson onde nós altamente conectados são praticamente impossíveis.

## 4. Citações Chave
- "Large networks self-organize into a scale-free state, a feature unpredicted by all existing random network models."
- "Older vertices increase their connectivity at the expense of the younger ones, leading over time to some vertices that are highly connected."

## 5. Mapeamento para a Wiki
- **Entidades Relacionadas**: [[Hubs (Nós Centrais)]].
- **Conceitos Chave**: [[Redes Scale-free]], [[Convergência Fenotípica]] (como resultado de auto-organização topológica), [[Robustez]].
