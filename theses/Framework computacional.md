**Última atualização:** 2026-05-26  
**Fontes base:** [[Barabasi-Albert-1999]], [[Zhang-Horvath-2005-WGCNA-Framework]], [[Langfelder-Horvath-2008-WGCNA]], [[Montenegro-2022-WGCNA]].

***

Tratando a interação gênica como um sistema complexo, é necessário compreender como os componentes dessa rede interagem entre si (Barabási, 2016). Para modelar essas dinâmicas, a teoria dos grafos biológicos é utilizada para capturar matematicamente as relações entre entidades, como genes ou proteínas, e suas interações funcionais (Pavlopoulos et al., 2011; Gao et al., 2018) **[Figura 1]**. 

> **[Figura 1: Representação Fundamental de um Grafo]**
> *(Representação matemática do conjunto de vértices V e arestas E).*

A natureza dessas conexões define a topologia do sistema. Na genômica, a representação estrutural varia de acordo com a interação biológica analisada, podendo os grafos apresentarem propriedades de direcionalidade, peso e variação de conectividade (Mason, Verwoerd, 2007; Montenegro, 2022) **[Figura 2]**. 

> **[Figura 2: Tipologias de Grafos]**
> *(Comparativo entre grafos direcionais, ponderados, conectados e completos).*

Em redes de regulação transcricional (TRNs), utilizam-se grafos direcionais para modelar detalhadamente como fatores de transcrição inibem, estimulam ou regulam genes alvo (Pavlopoulos et al., 2011) **[Figura 3]**. Em contrapartida, as redes de coexpressão gênica (GCNs) não exigem causalidade direta, mas agrupam genes com padrões de transcrição semelhantes. Essa abordagem baseia-se na premissa de que genes transcritos simultaneamente tendem a compartilhar mecanismos regulatórios e participar das mesmas vias moleculares (Montenegro, 2022).

> **[Figura 3: Representação de Regulação Biológica]**
> *(Diagrama de interações regulatórias: melhora, inibe e regula).*

Estudos revelam que essas interações adotam a arquitetura de redes biológicas livres de escala (*Scale-Free*) (Pavlopoulos et al., 2011; Barabási, 2016). Nessa topologia, a distribuição de conectividade segue uma função de lei de potência, resultando em um sistema onde a vasta maioria dos nós possui poucas conexões, enquanto um número reduzido de "hubs" concentra as ligações e delimita comunidades funcionais (Barabási & Albert, 1999; Mason, Verwoerd, 2007; Pavlopoulos et al., 2011; Koutrouli et al., 2020). Essa organização confere robustez contra falhas aleatórias, mas torna a rede vulnerável à deleção desses hubs centrais (Albert et al., 2000; Barabási, 2016).

A análise pode ser refinada pela centralidade de intermediação (*betweenness*), que identifica genes estruturalmente essenciais atuando como "pontes" ou gargalos entre os módulos (Freeman, 1977; Yu et al., 2007; Koschützki & Schreiber, 2008; Pavlopoulos et al., 2011). A presença dessas pontes revela que sistemas celulares formam comunidades sobrepostas, permitindo que genes exerçam pleiotropia ao influenciar múltiplos traços patológicos em diferentes vias simultâneas (Koschützki & Schreiber, 2008; Pavlopoulos et al., 2011) **[Figura 4]**.

> **[Sugestão de Figura 4: Propriedades Scale-Free e Centralidade]**
> *(Esquema visual demonstrando a Lei de Potência, nós Hubs e o conceito de Intermediação/Ponte).*

Para identificar com precisão esses módulos funcionais, a técnica *Weighted Gene Co-expression Network Analysis* (WGCNA) destaca-se ao utilizar ponderações contínuas e o cálculo da Medida de Sobreposição Topológica (TOM), em vez de cortes rígidos (*hard-thresholding*) que geram perda de informação biológica (Zhang, Horvath, 2005; Langfelder & Horvath, 2008) **[Figura 5]**. 

> **[Sugestão de Figura 5: Fluxograma Metodológico WGCNA]**
> *(Passos: Matriz de Expressão → Soft-thresholding → Matriz TOM → Dendrograma de Módulos).*

A fim de mitigar variações amostrais e explorar a heterogeneidade clínica, a biologia de sistemas utiliza a construção de redes transcriptômicas de consenso, buscando módulos topologicamente robustos através de múltiplas condições (Langfelder & Horvath, 2007; Montenegro, 2022). No contexto da Doença de Parkinson, isso permite realizar o mapeamento de interseção de mutações cruzadas, identificando como danos em genes inicialmente distintos (ex: *SNCA*, *LRRK2*, *GBA*) se propagam e convergem estruturalmente para afetar as mesmas vias modulares centrais do organismo (Glaab et al., 2012) **[Figura 6]**. 

> **[Sugestão de Figura 6: Modelo de Convergência Fenotípica]**
> *(Diagrama mostrando diferentes gatilhos genéticos convergindo estruturalmente para um módulo central comum da patologia).*

Essa cascata patogênica convergente demonstra como perturbações genéticas independentes convergem para ditar o mesmo desenvolvimento e progressão fenotípica da doença clínica.