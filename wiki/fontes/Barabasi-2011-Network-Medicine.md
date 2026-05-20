---
title: "Network medicine: a network-based approach to human disease"
authors: Albert-László Barabási, Natali Gulbahce, Joseph Loscalzo
year: 2011
journal: Nature Reviews Genetics
doi: 10.1038/nrg2918
type: Artigo de Revisão (Fundacional)
tags: [network-medicine, barabasi, interactoma, disease-module, doencas-complexas]
---

# Dissecação: Barabási et al. (2011) - Network Medicine

Esta revisão define o campo da **Network Medicine** (Medicina de Redes), estabelecendo que as doenças não são consequências de anormalidades isoladas em um único gene, mas o reflexo de perturbações que se espalham através de um complexo *interactoma* intracelular e intercelular.

## 1. Princípios Estruturais da Medicina de Redes
- **O Interactoma Humano**: Composto por ~25.000 genes, mais de 1.000 metabólitos, e dezenas de milhares de proteínas físicas com mais de 100.000 interações estimadas. É uma rede estritamente heterogênea.
- **Topologia de Falhas**: Assim como as redes de comunicação, o interactoma celular é tolerante a erros (*error tolerance*) graças ao *scale-free topology*, o que explica por que somos robustos a tantas mutações passivas ou ataques ambientais. No entanto, é vulnerável quando a falha atinge os grandes reguladores.
- **A Hipótese do Módulo da Doença (Disease Module)**: As proteínas associadas a uma mesma doença não estão espalhadas aleatoriamente na rede; elas aglomeram-se em uma vizinhança topológica restrita. Este é o fundamento biológico das [[Redes de Co-expressão]] na detecção de caminhos etiológicos.

## 2. Abordagem Metodológica
Aplica-se a rede em diferentes facetas biomédicas:
- **Identificação de Genes de Doença**: Exploração do conceito "Guilt-by-Association" (Culpa por associação) onde interatores locais de um gene patogênico causador conhecido têm probabilidade exponencialmente maior de também causarem o mesmo fenótipo (daí o uso algorítmico do Random Walk em métodos como [[Glaab-et-al-2012-EnrichNet]]).
- **Alvos de Fármacos**: Revela-se que muitas drogas atualmente não atuam sobre a proteína principal causadora da doença, mas em alvos periféricos pertencentes à vizinhança da doença para restabelecer a estabilidade metabólica.

## 3. Comorbidade e Integração
- **Associação Genótipo-Fenótipo**: A comorbidade entre doenças aparentemente não relacionadas é frequentemente explicada por proteínas compartilhadas, como documentado no Mapeamento da "Human Disease Network" (Rede de Doenças Humanas).
- O campo tenta reclassificar síndromes médicas, não pelos sintomas de superfície, mas pela localização subjacente dos módulos afetados dentro do interactoma celular.

## 4. Implicações para o TCC
- **O Fio Condutor**: A "Network Medicine" introduzida por Barabási justifica categoricamente sua abordagem para a **Convergência Fenotípica**. As variantes familiares (e.g. [[LRRK2]], [[SNCA]], [[PRKN]]) induzem disfunções a partir de diferentes pontos do interactoma humano; no entanto, todos os efeitos se propagam através de caminhos proteicos curtos para eventualmente travar ou sobrecarregar as mesmas unidades modulares fisiológicas (como o sistema Lisossômico-Autofágico e a Respiração Mitocondrial).

## Fontes
- [[Modelagem de Redes Biológicas]]
- [[Redes Scale-free]]
- [[Hubs (Nós Centrais)]]
