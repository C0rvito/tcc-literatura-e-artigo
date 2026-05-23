# Redes de Co-expressão (*Co-expression Networks*)

- **Tipo**: Método Analítico / Redes Biológicas
- **Descrição**: Redes onde as arestas representam a correlação estatística entre os níveis de expressão de genes através de diferentes condições ou amostras.

## Método WGCNA (*Weighted Gene Co-expression Network Analysis*)
O WGCNA é a técnica padrão-ouro para construir estas redes de forma ponderada.
- **Limiar Suave (*Soft Thresholding*)**: Diferente de redes não ponderadas, o WGCNA utiliza uma potência $\beta$ para enfatizar correlações fortes e penalizar as fracas, resultando em uma rede que segue uma topologia [[Redes Scale-free]] [[Li-et-al-2018-WGCNA]].
- **Módulos**: Genes são agrupados em módulos baseados na Medida de Sobreposição Topológica (TOM), refletindo funções biológicas coordenadas [[Li-et-al-2018-WGCNA]].
- **Eigengene do Módulo (ME)**: Representa o perfil de expressão global de um módulo (primeiro componente principal) [[Li-et-al-2018-WGCNA]].

## Na Doença de Parkinson
- **Identificação de Módulos**: Agrupamentos de genes que funcionam de maneira coordenada (ex: módulo de [[Disfunção Mitocondrial]]).
- **Convergência**: Genes mutados em diferentes variantes de DP (ex: [[SNCA]] e [[PRKN]]) frequentemente participam dos mesmos módulos de co-expressão em linhagens iPSC [[Zagare-et-al-2025]].
- **Hubs Gênicos**: Genes com alta conectividade dentro de um módulo são considerados alvos terapêuticos primários [[Li-et-al-2018-WGCNA]].

## Implementação e Performance
A construção de redes de co-expressão a partir de dados de RNA-Seq de larga escala exige alta eficiência computacional.
- **Ferramentas**: Embora o R seja o padrão para WGCNA, o ecossistema [[Bibliotecas-Python]] (especialmente o **Polars**) oferece vantagens críticas de memória e velocidade para o processamento de grandes matrizes de correlação e listas de arestas [[Usando-Polars]].

## Fontes
- [[Zagare-et-al-2025]]
- [[Tran-et-al-2020]]
- [[Li-et-al-2018-WGCNA]]
- [[Usando-Polars]]
