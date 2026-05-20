**Convergência Transcriptômica na Doença de Parkinson: Análise de Redes de Coexpressão**

# Introdução

A Doença de Parkinson (DP) é uma desordem neurológica crônica e progressiva, caracterizada por tremor, rigidez e instabilidade postural (Soman *et al*., 2025). Do ponto de vista patológico, associa-se à perda de neurônios dopaminérgicos na Substantia Nigra pars compacta (SNpc) e ao acúmulo de Corpos de *Lewy* (Soman *et al*., 2025). A DP não constitui uma entidade única, mas um espectro clínico resultante da interação entre fatores genéticos e ambientais (Kalia e Lang, 2015). Um dos principais desafios na sua compreensão é que diferentes gatilhos moleculares levam a um fenótipo degenerativo semelhante, fenômeno descrito como convergência fenotípica, no qual múltiplas vias biológicas culminam em falhas homeostáticas comuns (Beccano-Kelly *et al*., 2023).

Esse cenário pode ser dividido em dois modelos principais, DP idiopática e formas monogênicas. A forma idiopática, responsável pela maioria dos casos, envolve variantes genéticas comuns de baixo efeito que, isoladamente, não causam a doença, mas aumentam a vulnerabilidade a fatores ambientais (Soman *et al.*, 2025). Já as formas monogênicas decorrem de mutações de alta penetrância em genes como SNCA, LRRK2, PINK1 e PRKN, que atuam como gatilhos diretos de disfunção celular (Morris e Lim, 2025). Apesar da diversidade genética, os mecanismos patológicos convergem para vias comuns (Beccano-Kelly *et al.*, 2023).

Entre essas vias, destacam-se a disfunção mitocondrial, que compromete a produção de ATP e a remoção de organelas danificadas (Soman *et al.*, 2025), o estresse oxidativo, decorrente do acúmulo de espécies reativas de oxigênio (Blesa *et al.,* 2015). Soma-se a isso a falha proteostática, resultante do colapso do sistema ubiquitina-proteassoma e à agregação de alfa-sinucleína, levando ao acúmulo de proteínas mal dobradas e à formação de Corpos de Lewy (Branco *et al.,* 2010). Esses processos formam um ciclo vicioso em que a deficiência energética agrava o acúmulo protéico, que por sua vez intensifica a disfunção mitocondrial (Soman et al., 2025).

A degeneração afeta preferencialmente os neurônios dopaminérgicos da SNpc, que apresentam alta demanda energética, dependência de canais de cálcio do tipo L e baixa capacidade de tamponamento de cálcio, tornando-os especialmente vulneráveis ao estresse metabólico e oxidativo (Liss *et al.,* 2016; Surmeier *et al.,* 2012). O estágio final envolve apoptose, frequentemente precedida pelo fenômeno de *dying-back,* em que a degeneração progride dos terminais axonais ao corpo celular (Pissadaki e Bolam, 2013). Em condições normais, o neurónio dopaminérgico atua como um modulador essencial da excitabilidade nos gânglios da base, equilibrando as vias motora direta (que facilita o movimento) e indireta (que o inibe) para garantir movimentos suaves e precisos (Soman *et al.*, 2025). Quando a perda neuronal ultrapassa cerca de 50 a 60%, a depleção de dopamina resulta nos sintomas motores característicos (Soman *et al*., 2025). Esta falta de modulação rompe o equilíbrio sináptico e induz uma hiperatividade da via indireta, levando a uma desinibição de circuitos motores que passam a operar num estado de oscilação rítmica patológica (Pissadaki e Bolam, 2013). Sem o auxílio da dopamina, o sistema perde a capacidade de suprimir descargas neuronais sincronizadas, o que se manifesta clinicamente como o tremor de repouso (Liss *et al*., 2016).

Nesse contexto, a tecnologia de reprogramação celular introduziu uma mudança decisiva na investigação da DP. As iPSCs (células-tronco pluripotentes induzidas, do inglês, *induced pluripotent stem cells*), desenvolvidas por Takahashi e Yamanaka, permitem reverter células somáticas, como fibroblastos, a um estado pluripotente (Shen *et al.,* 2016). Essa abordagem supera a limitação de acesso ao tecido cerebral humano, possibilitando a geração, em laboratório, de neurônios dopaminérgicos derivados diretamente de pacientes (Burbulla *et al.*, 2017).

O principal diferencial das iPSCs é a preservação da arquitetura genética do indivíduo (Beccano-Kelly *et al*., 2023). Isso permite modelar, em um contexto celular humano mais próximo do real, mutações específicas em genes como SNCA, LRRK2, PARK2, PINK1 e PRKN, inclusive em sistemas isogênicos (Rus Jacquet *et al*., 2021). Dessa forma, torna-se possível investigar, de maneira controlada, como diferentes alterações genéticas convergem para os mesmos mecanismos de disfunção celular (Burbulla *et al.,* 2017). Assim, os modelos baseados em iPSCs consolidaram-se como uma plataforma central para estudar as cascatas patogênicas da Doença de Parkinson, conectando diretamente a variabilidade genética inicial aos mecanismos convergentes que levam à degeneração neuronal (Beccano-Kelly *et al*., 2023).

A integração desses modelos *in vitro* com abordagens ômicas amplia significativamente o potencial de investigação em nível de sistemas. Nesse contexto, a incorporação de análises transcriptômicas permite avançar da caracterização estática do genoma para a análise dos estados funcionais da célula (Liu; Song, 2025; Zhao *et al.*, 2022). O transcriptoma corresponde ao conjunto de RNAs expressos em um dado momento, refletindo diretamente a atividade gênica e as vias biológicas em funcionamento. Diferentemente da arquitetura genética, que é relativamente estável, o transcriptoma é dinâmico e sensível a alterações fisiológicas e patológicas. Assim, por meio de técnicas como RNA-seq, torna-se possível capturar essa dinamicidade celular, identificando padrões de expressão gênica e redes regulatórias que estão desreguladas na DP (Gautier *et al.*, 2026). Essa abordagem permite não apenas mapear quais genes estão alterados, mas compreender como programas transcricionais inteiros convergem para estados celulares patológicos, conectando mutações específicas a fenótipos funcionais em nível de sistemas (Clark *et al*., 2022).

**Teoria de Redes e *framework* computacional**  
Tratando a interação gênica como um sistema complexo, é necessário compreender como os componentes dessa rede interagem entre si (Barabási, 2016). Para modelar essa interação, os Grafos são utilizados para capturar matematicamente as relações entre os componentes e suas interações dentro de um sistema de redes.

Em uma rede, os componentes são chamados de nós e as interações entre nós são arestas. O número de nós ([![][image1]](https://www.codecogs.com/eqnedit.php?latex=N#0)) representa o tamanho do sistema e são indexados com [![][image2]](https://www.codecogs.com/eqnedit.php?latex=i%20%5C%20\(i%20%3D%201%2C%202%2C%20%5Cdots%2C%20N\)#0), enquanto o número de links ([![][image3]](https://www.codecogs.com/eqnedit.php?latex=L#0)) representa o número de interações entre os nós (Barabási, 2016). Matematicamente o grafo ([![][image4]](https://www.codecogs.com/eqnedit.php?latex=G#0)) que representa a rede se daria pelo conjunto [![][image5]](https://www.codecogs.com/eqnedit.php?latex=V#0)composto pelos nós ([![][image6]](https://www.codecogs.com/eqnedit.php?latex=V%20%3D%20%5C%7Bi_1%2C%20i_2%2C%20%5Cdots%2C%20i_N%5C%7D#0)) e o conjunto [![][image7]](https://www.codecogs.com/eqnedit.php?latex=E#0) composto pelas arestas, ou seja, qual nó conecta com qual ([![][image8]](https://www.codecogs.com/eqnedit.php?latex=E%20%3D%20%5C%7B%5C%7Bi_3%2C%20i_N%5C%7D%2C%20%5C%7Bi_1%2C%20i_2%5C%7D%5C%7D#0)). Além disso, um sistema de rede contém uma série de propriedades, entre elas grau e distância (Koutrouli et al., 2020). 

A relação entre nós define o tipo de grafo. Dado um grafo [![][image9]](https://www.codecogs.com/eqnedit.php?latex=G%20%3D%20\(V%2C%20E\)#0) onde

[![][image10]](https://www.codecogs.com/eqnedit.php?latex=E%20%3D%20%5C%7B\(i%2C%20j\)%20%5Cmid%20i%2C%20j%20%5Cin%20V%5C%7D#0), se a interação é recíproca, o grafo é não-direcional, enquanto o grafo direcional ([![][image11]](https://www.codecogs.com/eqnedit.php?latex=G%20%3D%20\(V%2C%20E%2C%20f\)#0))  apresenta a função [![][image12]](https://www.codecogs.com/eqnedit.php?latex=f#0) mapeando a orientação da aresta entre um nó e outro (Huber et al., 2007). Em sistemas biológicos as relações direcionais podem representar a melhora, inibição ou regulação entre nós (Le Novère et al., 2009). Se há um peso que determina a relevância da interação entre dois nós, o grafo é ponderado. Caso haja um caminho entre qualquer ponto do grafo para outro ponto qualquer, o grafo é denotado conectado, e quando todo par de nós é conectado por uma única aresta o grafo é completo (Koutrouli et al., 2020).

Redes podem ser descritas como matrizes de tamanho [![][image13]](https://www.codecogs.com/eqnedit.php?latex=N%20%5Ctimes%20N#0) representando o grafo. A representação em matriz permite o rastreio das interações entre cada nó. Dada uma matriz [![][image14]](https://www.codecogs.com/eqnedit.php?latex=A#0), as linhas serão preenchidas pelo mapeamento das conexões entre os nós: se [![][image15]](https://www.codecogs.com/eqnedit.php?latex=A_%7Bij%7D%20%3D%201#0), uma presença de interação é identificada; se [![][image16]](https://www.codecogs.com/eqnedit.php?latex=A_%7Bij%7D%20%3D%200#0), a ausência de uma conexão é identificada. Se a rede for ponderada, a conexão será dada por [![][image17]](https://www.codecogs.com/eqnedit.php?latex=A_%7Bij%7D%20%3D%20w_%7Bij%7D#0), onde [![][image18]](https://www.codecogs.com/eqnedit.php?latex=w_%7Bij%7D#0) é um valor real que representa a relevância da interação entre os nós [![][image19]](https://www.codecogs.com/eqnedit.php?latex=i#0) e [![][image20]](https://www.codecogs.com/eqnedit.php?latex=j#0) (Barabási, 2016, Koutrouli et al., 2020).

---

Quanto às propriedades das redes, o grau ([![][image21]](https://www.codecogs.com/eqnedit.php?latex=k_1#0)) representa o número de ligações que o nó i possui com outros componentes. Em grafos não direcionados, o número total de ligações (L) é igual à metade da soma dos graus de todos os nós, dado que cada aresta é contada duas vezes (uma para cada nó que ela conecta). Matematicamente, essa relação é expressa por [![][image22]](https://www.codecogs.com/eqnedit.php?latex=L%20%3D%20%5Cfrac%7B1%7D%7B2%7D%20%5Csum_%7Bi%3D1%7D%5E%7BN%7D%20k_i#0) . A partir disso, para um grafo não direcionado o grau médio ([![][image23]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20k%20%5Crangle#0)) com [![][image24]](https://www.codecogs.com/eqnedit.php?latex=N#0) nós é calculado como [![][image25]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20k%20%5Crangle%20%3D%20%5Cfrac%7B1%7D%7BN%7D%20%5Csum_%7Bi%3D1%7D%5E%7BN%7D%20k_i%20%3D%20%5Cfrac%7B2L%7D%7BN%7D#0), enquanto que em grafos direcionados, cada nó apresenta dois graus, o grau de entrada ([![][image26]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20k%20%5Crangle_%7Bin%7D#0)) representando o número de arestas incidentes naquele nó e o grau de saída ([![][image27]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20k%20%5Crangle_%7Bin%7D#0)), que representa os número de arestas que saem daquele nó. Logo o grau total de um nó é a soma [![][image28]](https://www.codecogs.com/eqnedit.php?latex=k_i%20%3D%20k_i%5E%7Bin%7D%20%2B%20k_i%5E%7Bout%7D#0) e, portanto, seu número total de ligações será a soma dos graus de entrada ou de saída, sem o fator de correção das redes não direcionadas [![][image29]](https://www.codecogs.com/eqnedit.php?latex=L%20%3D%20%5Csum_%7Bi%3D1%7D%5E%7BN%7D%20k_i%5E%7Bin%7D%20%3D%20%5Csum_%7Bi%3D1%7D%5E%7BN%7D%20k_i%5E%7Bout%7D#0) e seu grau médio por [![][image30]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20k%5E%7Bin%7D%20%5Crangle%20%3D%20%5Clangle%20k%5E%7Bout%7D%20%5Crangle%20%3D%20%5Cfrac%7BL%7D%7BN%7D#0) (Pavlopoulos et al., 2011 , Barabási, 2016).

Tratando de outra propriedade, a distância em uma rede é definida pelo tamanho do caminho entre dois nós. Em uma rede de N nós, o caminho entre os nós [![][image31]](https://www.codecogs.com/eqnedit.php?latex=i_0#0) e [![][image32]](https://www.codecogs.com/eqnedit.php?latex=i_n#0) é dado pelo conjunto [![][image33]](https://www.codecogs.com/eqnedit.php?latex=P#0) de [![][image34]](https://www.codecogs.com/eqnedit.php?latex=n#0) ligações que os conectam. Matematicamente, o conjunto é expresso como [![][image35]](https://www.codecogs.com/eqnedit.php?latex=P%20%3D%20%5C%7B%20\(i_0%2C%20i_1\)%2C%20\(i_1%2C%20i_2\)%2C%20%5Cdots%2C%20\(i_%7Bn-1%7D%2C%20i_n\)%20%5C%7D#0). O menor caminho ([![][image36]](https://www.codecogs.com/eqnedit.php?latex=d_%7Bij%7D#0)) entre dois nós [![][image37]](https://www.codecogs.com/eqnedit.php?latex=i#0) e [![][image38]](https://www.codecogs.com/eqnedit.php?latex=j#0) é o caminho que contém o menor número de arestas entre todos os conjuntos [![][image39]](https://www.codecogs.com/eqnedit.php?latex=P#0) possíveis. A partir disso , o diâmetro ([![][image40]](https://www.codecogs.com/eqnedit.php?latex=d_%7Bmax%7D#0)) representa a maior distância mais curta entre qualquer par de nós na rede: [![][image41]](https://www.codecogs.com/eqnedit.php?latex=d_%7Bmax%7D%20%3D%20%5Cmax_%7Bi%2Cj%7D%20d_%7Bij%7D#0). O tamanho médio ([![][image42]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20d%20%5Crangle#0)) é a média aritmética das distâncias mais curtas entre todos os pares de nós: [![][image43]](https://www.codecogs.com/eqnedit.php?latex=%5Clangle%20d%20%5Crangle%20%3D%20%5Cfrac%7B1%7D%7BN\(N-1\)%7D%20%5Csum_%7Bi%2Cj%3B%20i%20%5Cneq%20j%7D%20d_%7Bij%7D#0) (Barabási, 2016). 

A aplicação matemática dessa abordagem para analisar interações biológicas constitui a teoria dos grafos biológicos e é fundamental na compreensão de sistemas biológicos complexos (Pavlopoulos *et al.*, 2011, Gao *et al.*, 2018). Nessas redes de interação os nós representam entidades biológicas, como genes, transcritos ou proteínas, enquanto as arestas denotam as interações ou relações funcionais entre eles (Pavlopoulos et al., 2011). Na genômica, as conexões entre os nós podem refletir tanto as relações regulatórias causais entre genes quanto suas coexpressões (Manson, Verwood, 2006, Montenegro 2022).

Em redes de regulação transcricional (TRNs) utilizam-se representações de grafos direcionais para modelar as etapas da expressão gênica e identificar como moléculas e fatores de transcrição inibem ou estimulam genes alvo (Pavlopoulos et al., 2011). Em complemento, as redes de coexpressão gênica (GCNs) não exigem uma direcionalidade causal, mas agrupam genes que exibem padrões de transcrição semelhantes através de condições experimentais. Essa abordagem se baseia na premissa biológica de que genes transcritos simultaneamente tendem a compartilhar mecanismos de regulação, participar das mesmas vias moleculares e ditar fenótipos específicos (Montenegro, 2022).

Independentemente de serem regulatórias ou de coexpressão, estudos revelam que as interações biológicas não se conectam de forma aleatória e uniforme, mas adotam a arquitetura de redes biológicas livres de escala (Pavlopoulos et al., 2011; Barabási, 2016). Nesses sistemas, a distribuição de conectividade segue uma função de lei de potência, resultando em uma topologia na qual a vasta maioria dos nós possui poucas conexões, enquanto um número reduzido de nós apresenta uma alta centralidade de grau, concentrando as ligações do sistema (Barabási & Albert, 1999; Mason, Verwoerd, 2007). Esses nós altamente conectados, chamados de hubs, atuam como pontos centrais da rede e delimitam comunidades de genes funcionalmente relacionados (Pavlopoulos et al., 2011; Koutrouli et al., 2020). Essa organização confere aos sistemas biológicos uma excepcional robustez e tolerância a falhas aleatórias; entretanto, a deleção de nós com alta centralidade está correlacionada com a instabilidade e colapso da rede (Albert et al., 2000; Barabási, 2016).

No que tange à construção de redes de coexpressão gênica, uma das técnicas mais robustas é a Weighted Gene Co-expression Network Analysis (WGCNA) (Langfelder, Horvath, 2008). A WGCNA agrupa transcritos em módulos funcionais e utiliza a centralidade de grau para identificar os hubs intramodulares. Em vez de definir limites de corte rígidos (hard-thresholding) que dicotomizam as relações biológicas e geram perda de informação, a WGCNA emprega uma função de adjacência baseada em potência para ponderar a matriz de similaridade contínua (Zhang, Horvath, 2005). Matematicamente, a adjacência ([![][image44]](https://www.codecogs.com/eqnedit.php?latex=a_%7Bij%7D#0)) entre dois genes é obtida pela elevação do coeficiente de correlação a um expoente de *soft-thresholding* [![][image45]](https://www.codecogs.com/eqnedit.php?latex=\(%5Cbeta\)%3A%20a_%7Bij%7D%20%3D%20%7Ccor\(x_i%2C%20x_j\)%7C%5E%5Cbeta#0). Essa transformação enfatiza conexões fortes e penaliza correlações fracas (Kadarmideen, Watson-Haigh, 2012), aproximando a rede de uma topologia livre de escala. Contudo, a adjacência simples captura apenas a força da interação direta. Para que a estrutura modular da rede seja biologicamente coesa, é necessário considerar o contexto topológico no qual esses genes estão inseridos (Montenegro, 2022).

Para a identificação precisa desses módulos, a WGCNA utiliza o cálculo da Medida de Sobreposição Topológica (TOM) (Ravasz et al., 2002; Zhang, Horvath, 2005). A TOM altera a métrica de conectividade ao considerar não apenas a força da ligação entre dois nós, mas o nível de interconectividade com seus vizinhos compartilhados. Um valor de [![][image46]](https://www.codecogs.com/eqnedit.php?latex=%5Ctext%7BTOM%7D%20%3D%201#0) indica que dois genes compartilham exatamente a mesma vizinhança, enquanto [![][image47]](https://www.codecogs.com/eqnedit.php?latex=%5Ctext%7BTOM%7D%20%3D%200#0) aponta para a ausência de conexões comuns. Por fim, a [![][image48]](https://www.codecogs.com/eqnedit.php?latex=%5Ctext%7BTOM%7D#0) é convertida em uma matriz de dissimilaridade ([![][image49]](https://www.codecogs.com/eqnedit.php?latex=d_%7Bij%7D%5E%5Comega%20%3D%201%20-%20%5Ctext%7BTOM%7D_%7Bij%7D#0)), utilizada como input para algoritmos de agrupamento hierarquico. Com os módulos estabelecidos a partir dos valores de TOM, é possível inferir as funções biológicas de transcritos fundamentando-se no princípio de "culpa por associação" com os genes de seu respectivo módulo, garantindo uma maior robustez da rede (Langfelder & Horvath, 2008; Li et al., 2018).

Em complemento, a análise de rede pode ser refinada pela aplicação da centralidade de intermediação (Freeman, 1977; Koschützki, Schreiber, 2008; Pavlopoulos et al., 2011). Enquanto a centralidade de grau foca na vizinhança local, a intermediação avalia a rede de forma global, quantificando a proporção de caminhos mais curtos que atravessam obrigatoriamente um nó específico. Essa abordagem destaca genes estruturalmente essenciais que atuam como pontes ou gargalos na dinâmica da rede (Yu et al., 2007; Pavlopoulos et al., 2011).

A presença contínua dessas pontes moleculares revela que os sistemas celulares não operam como compartimentos perfeitamente isolados, mas formam comunidades de rede sobrepostas, permitindo que conjuntos de genes atuem de forma simultânea em múltiplas vias funcionais (Pavlopoulos et al., 2011). Esse grau de compartilhamento topológico é uma manifestação direta da pleiotropia gênica, propriedade biológica na qual um único gene, no contexto da rede um nó de alta intermediação, é capaz de influenciar múltiplos traços fenotípicos ou patológicos (Koschützki & Schreiber, 2008; Pavlopoulos et al., 2011).

A fim de explorar a complexidade dessas sobreposições e mitigar variações limitadas a um único grupo amostral, a biologia de sistemas se utiliza da construção de redes transcriptômicas de consenso. Essa estratégia busca módulos de coexpressão que se mantêm topologicamente robustos e consistentes através de múltiplas condições biológicas ou diferentes conjuntos de dados (Langfelder, Horvath, 2007; Montenegro, 2022). No contexto de doenças de origem genética altamente heterogênea, como a Doença de Parkinson, a formulação dessas redes globais permite realizar o mapeamento de interseção de mutações cruzadas. Ao sobrepor dados de coexpressão de pacientes ou modelos que possuem diferentes bases genéticas, torna-se possível identificar os módulos genéticos de consenso que são invariavelmente afetados no sistema de rede (Glaab et al., 2012).

Figura 1\. Parte superior: top 5 genes de parkinson e suas frequências em parkison. Parte inferior mostrar o que é sobreposição de comunidades em redes (5 redes que compartilham alguns nós).

A identificação desses padrões estruturais compartilhados evidencia os mecanismos biológicos universais subjacentes à patologia. Em suma, o mapeamento destas redes indica que, independentemente do gene específico que sofreu a mutação primária, o dano se propaga através dos nós de ponte, afetando as mesmas vias modulares centrais do organismo. Essa dinâmica caracteriza uma cascata patogênica convergente, demonstrando como perturbações inicialmente distintas na rede biológica convergem estruturalmente para ditar o mesmo desenvolvimento e progressão fenotípica da doença clínica.

Novo outline para seguir a norma: Deve ser apresentada em uma abordagem (1) do contexto geral para o específico; (2) conter o estado da arte do assunto (informações recentes sobre o assunto); (3) apresentar a lacuna do conhecimento; (4) a justificativa(relevância) do estudo.

Paragrafo 1: visão geral de PD (incidência, diagnóstico e manifestação clínica). Complexidade da doenca.

Paragrafo 2: muitos trabalhos sobre os mecanismos de cada gene. Descrever mecanismos de cada gene (Focar nos escolhidos).

Paragrafo 3: lacuna que vamos explorar (O que existem em comum entre as alterações genéticas. Consequências especificas em células neuronais (Aplicação em parkison) e consequências em outros tipos de células (aplicação em câncer).

Paragrafo 4: justifica. Pouco explorada a análise de redes e convergência evolutiva. Desenvolvimento de terapias que possam atingir mais pacientes, pois tratam processos biologicos em comum e aplicação em câncer.

Objetivos ((5) objetivo do artigo. O objetivo deve ser claro e sucinto. Sugere-se redigir a introdução entre quatro a sete parágrafos e utilizar somente referências pertinentes ao assunto.)

Geral: caracterizar convergência de fenótipos biologicos de diferentes alterações genéticas de PD.

Desenvolver um pipeline para análise de convergência de redes em PD.

Analisar GSEA das overlapping communities in PD.

Encontrar convergência de fenótopos de alteracnoes geneticas associadas a parkison

# Metodologia

**Aquisição de Dados e Montagem da Coorte**

Conjuntos de dados de RNA-seq derivados de células-tronco pluripotentes induzidas humanas (iPSCs) serão obtidos do banco de dados Gene Expression Omnibus (GEO). As coortes selecionadas incluirão linhagens de iPSCs portadoras de mutações associadas à Doença de Parkinson, especificamente nos loci LRRK2, GBA e SNCA. Cada coorte mutante será rigorosamente pareada com dados transcriptômicos correspondentes de linhagens controle saudáveis, *wild-type* ou isogênicas corrigidas por CRISPR, garantindo uma análise comparativa robusta.

Figura 2\. Criar uma figura que mostra as comparações (nada de código) apenas a coisas biológicas.

**Controle de Qualidade e Pré-processamento**

Os dados brutos de sequenciamento (arquivos FASTQ) serão submetidos a uma avaliação abrangente de controle de qualidade (QC) utilizando o FastQC, a fim de analisar a qualidade das leituras, o conteúdo de GC e a presença de contaminação por adaptadores. Com base nas métricas de QC, as leituras serão processadas por *trimming* para remoção de sequências de adaptadores e bases de baixa qualidade (por exemplo, *Phred score* \< 30), utilizando ferramentas como Trimmomatic ou Cutadapt. Após essa etapa, será realizado um novo QC para garantir a integridade dos dados antes do alinhamento.

**Alinhamento e Quantificação do Transcriptoma**

As leituras filtradas e de alta qualidade serão alinhadas ao genoma de referência humano mais atualizado (GRCh38) utilizando o algoritmo STAR (*Spliced Transcripts Alignment to a Reference*). Para maximizar a precisão do mapeamento em regiões de junção de splicing, o alinhamento será guiado por anotações transcriptômicas de referência. A quantificação em nível gênico será realizada com ferramentas como featureCounts ou pelo pipeline interno do STAR, gerando matrizes de contagem bruta para análises estatísticas subsequentes.

**Análise de Expressão Gênica Diferencial**

As contagens brutas serão importadas para o ambiente estatístico R, onde a análise de expressão diferencial será conduzida utilizando o pacote DESeq2. Fatores de normalização (*size factors*) serão estimados para corrigir diferenças na profundidade de sequenciamento entre as amostras. Genes diferencialmente expressos (DEGs) entre as iPSCs mutantes (LRRK2, GBA, SNCA) e seus respectivos controles serão identificados por meio de modelos lineares generalizados baseados na distribuição binomial negativa. A significância estatística será definida por correção para múltiplos testes utilizando taxa de descoberta falsa (FDR), com limiar, por exemplo, de *p ajustado* \< 0,05, associado a um ponto de corte de *log2 fold-change* previamente definido.

A decodificação das redes de coexpressão obtidas a partir de modelos baseados em iPSCs requer ferramentas analíticas avançadas, como a Gene Set Enrichment Analysis (GSEA) e o Gene Ontology (GO) mapping, que traduzem alterações transcricionais sutis e coordenadas em vias biológicas funcionais, elucidando a raiz do colapso celular descrito anteriormente (Manuel & Tayo, 2023; Eteleeb *et al.,* 2024). Para expandir essa compreensão estrutural, os dados transcricionais são frequentemente integrados à Interactomics (Protein-Protein Interaction networks), uma abordagem que mapeia as interações físicas entre as proteínas para identificar genes "hubs" que orquestram a falha homeostática em nível sistêmico (Manuel & Tayo, 2023; García-Criado *et al*., 2025). A preservação sistemática destas redes de interação em pacientes com diferentes perfis genéticos possibilita a descoberta de universal transcriptomic biomarkers, que consistem em assinaturas moleculares robustas capazes de sinalizar a disfunção e o estágio da patologia independentemente da origem etiológica (Manuel & Tayo, 2023; Liu & Song, 2025).

Ao mapear com precisão esses nós críticos de convergência fenotípica, a pesquisa translacional passa a explorar sistematicamente o druggable genome, cruzando as assinaturas genéticas desreguladas com grandes bancos de dados farmacológicos para o rápido reposicionamento (*drug repurposing*) de compostos e a identificação de novos alvos terapêuticos (Manuel & Tayo, 2023). Em última análise, a consolidação deste modelo de biologia de redes visa o desenvolvimento de estratégias de mutation-agnostic neuroprotection, construindo o caminho para terapias modificadoras que protegem os neurônios dopaminérgicos ao intervirem nas vias de falência sistêmica compartilhadas, como o estresse mitocondrial e lisossomal, beneficiando de forma abrangente tanto os pacientes com formas monogênicas raras quanto a esmagadora maioria afetada pela Doença de Parkinson idiopática (Burbulla *et al.,* 2017; Padmanabhan *et al.*, 2019\)

**Análise Independente e Integrativa de Redes**

Para avançar da análise de genes individuais para uma compreensão em nível de sistemas, será empregada análise de redes de coexpressão gênica.

1. **Análise de Redes Separadas**

Inicialmente, redes topológicas independentes serão construídas para cada contexto mutacional (LRRK2, GBA, SNCA), utilizando metodologias como WGCNA (*Weighted Gene Co-expression Network Analysis*). Essa abordagem permitirá identificar módulos gênicos e arquiteturas transcriptômicas específicas perturbadas por cada mutação.

2. **Integração de Redes**

Em seguida, será implementado um pipeline rigoroso de integração entre redes. As redes independentes serão comparadas sistematicamente para identificar sub-redes conservadas e genes centrais (*hub genes*) compartilhados entre todas as coortes mutantes. Essa estratégia integrativa e multicamada visa identificar um fenótipo molecular convergente que contribua de forma robusta para a patogênese da Doença de Parkinson, independentemente dos diferentes gatilhos genéticos iniciais.

Figura 3\. Parte inferior mostrar o que é sobreposição de comunidades em redes (5 redes que compartilham alguns nós).

3. **GSEA de comunidade overlapping** 

**Resultados**

**5-7 figuras;**

**Discussão**

**Discutir com artigos base**

Coukos, R., Krainc, D. Key genes and convergent pathogenic mechanisms in Parkinson disease. Nat. Rev. Neurosci. 25, 393–413 (2024). [https://doi.org/10.1038/s41583-024-00812-2](https://doi.org/10.1038/s41583-024-00812-2)

Tran, J., Anastacio, H. & Bardy, C. Genetic predispositions of Parkinson’s disease revealed in patient-derived brain cells. *npj Parkinsons Dis.* **6**, 8 (2020). [https://doi.org/10.1038/s41531-020-0110-8](https://doi.org/10.1038/s41531-020-0110-8)

Zagare, A., Balaur, I., Rougny, A. *et al.* Deciphering shared molecular dysregulation across Parkinson’s disease variants using a multi-modal network-based data integration and analysis. *npj Parkinsons Dis.* **11**, 63 (2025). https://doi.org/10.1038/s41531-025-00914-3

# Referências

ALBERT, R.; JEONG, H.; BARABÁSI, A.-L. Error and attack tolerance of complex networks. **Nature**, v. 406, n. 6794, p. 378–382, jul. 2000\.

ALBERT-LÁSZLÓ BARABÁSI. **Network science**. Cambridge: Cambridge University Press, 2016\.

BARABÁSI, A.-L.; ALBERT, R. Emergence of Scaling in Random Networks. **Science**, v. 286, n. 5439, p. 509–512, 15 out. 1999\.

FREEMAN, L. C. A Set of Measures of Centrality Based on Betweenness. **Sociometry**, v. 40, n. 1, p. 35, mar. 1977\.

GAO, W. et al. Study of biological networks using graph theory. **Saudi Journal of Biological Sciences**, v. 25, n. 6, p. 1212–1219, set. 2018\.

GLAAB, E. et al. EnrichNet: network-based gene set enrichment analysis. **Bioinformatics**, v. 28, n. 18, p. i451–i457, 3 set. 2012\.

HUBER, W. et al. Graphs in molecular biology. **BMC Bioinformatics**, v. 8, n. S6, set. 2007\.

KADARMIDEEN, H. N.; WATSON-HAIGH, N. S. Building gene co-expression networks using transcriptomics data for systems biology investigations: Comparison of methods using microarray data. **Bioinformation**, v. 8, n. 18, p. 855–861, 21 set. 2012\.

KOSCHÜTZKI, D.; SCHREIBER, F. Centrality Analysis Methods for Biological Networks and Their Application to Gene Regulatory Networks. **Gene Regulation and Systems Biology**, v. 2, p. GRSB.S702, jan. 2008\.

KOUTROULI, M. et al. A Guide to Conquer the Biological Network Era Using Graph Theory. **Frontiers in Bioengineering and Biotechnology**, v. 8, 31 jan. 2020\.

LANGFELDER, P.; HORVATH, S. WGCNA: an R package for weighted correlation network analysis. **BMC Bioinformatics**, v. 9, n. 1, dez. 2008\.

LI, J. et al. Application of Weighted Gene Co-expression Network Analysis for Data from Paired Design. **Scientific Reports**, v. 8, n. 1, 12 jan. 2018\.

MASON, O.; VERWOERD, M. Graph theory and networks in Biology. **IET Systems Biology**, v. 1, n. 2, p. 89–119, 1 mar. 2007\.

MONTENEGRO, J. D. Gene Co-expression Network Analysis. **Methods in Molecular Biology (Clifton, N.J.)**, v. 2443, p. 387–404, 2022\.

NOVÈRE, N. L. et al. The Systems Biology Graphical Notation. **Nature Biotechnology**, v. 27, n. 8, p. 735–741, 1 ago. 2009\.

PAVLOPOULOS, G. A. et al. Using graph theory to analyze biological networks. **BioData Mining**, v. 4, n. 1, 28 abr. 2011\.

RAVASZ, E. Hierarchical Organization of Modularity in Metabolic Networks. **Science**, v. 297, n. 5586, p. 1551–1555, 30 ago. 2002\.

YU, H. et al. The Importance of Bottlenecks in Protein Networks: Correlation with Gene Essentiality and Expression Dynamics. **PLoS Computational Biology**, v. 3, n. 4, p. e59, 20 abr. 2007\.

ZHANG, B.; HORVATH, S. A General Framework for Weighted Gene Co-Expression Network Analysis. **Statistical Applications in Genetics and Molecular Biology**, v. 4, n. 1, 12 jan. 2005\. 

[image1]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAJBAMAAAD0ltBnAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme+rEM3du4lEZjJ2IlT/AWrmAAAAEUlEQVR4XmP8zwACTGCSdAoAQDgBEaehpFcAAAAASUVORK5CYII=>

[image2]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHEAAAAPBAMAAAAheD1SAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIpndq2ZU7xB2u4kyzURERAO4AAAAHUlEQVR4XmP8z0Ae+MiELkI0GNVJCIzqJASGlk4AlbICDoXhkSYAAAAASUVORK5CYII=>

[image3]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAJBAMAAAD9fXAdAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme/dzburIkSJZnYyEFQ2tUYyAAAAEUlEQVR4XmP8z8DAwMRAHAEALZYBEce9Dw0AAAAASUVORK5CYII=>

[image4]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAALBAMAAABbgmoVAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIlSJq7vN3e+ZdjIQZkTyK+OvAAAAFElEQVR4XmP8zwAEH5lAJAMDhRQAkicCBm41e8MAAAAASUVORK5CYII=>

[image5]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAALBAMAAABbgmoVAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAie/dzburmWZEIlQydhDLkUXkAAAAFElEQVR4XmP8zwAEH5lAJAMDhRQAkicCBm41e8MAAAAASUVORK5CYII=>

[image6]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHwAAAAPBAMAAADUhrbiAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAie/dzburmWZEIlQydhDLkUXkAAAAHElEQVR4XmP8z0AJYEIXIA2MaicbjGonGwxp7QDnjQEddR7hkQAAAABJRU5ErkJggg==>

[image7]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAAJBAMAAAAWSsseAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAMnaJmRDdq83vu1QiRGZ/VowGAAAAFElEQVR4XmP8zwAEH5lAJAMDyRQAdeECAjR5M6QAAAAASUVORK5CYII=>

[image8]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJMAAAAPBAMAAAASb+AeAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAMnaJmRDdq83vu1QiRGZ/VowGAAAAIklEQVR4XmP8z0Al8JEJXYR8MGoU8WDUKOLBqFHEAyoaBQCDzwIOw5mlOAAAAABJRU5ErkJggg==>

[image9]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAEUAAAAPBAMAAABAYB8QAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIlSJq7vN3e+ZdjIQZkTyK+OvAAAAGUlEQVR4XmP8z0AIfGRCF8ECRtXgB0NRDQAWSgIOvJLaywAAAABJRU5ErkJggg==>

[image10]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIkAAAAPBAMAAAAi4/E/AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAMnaJmRDdq83vu1QiRGZ/VowGAAAAIUlEQVR4XmP8z0A5+MiELkIWGDUFOxg1BTsYNQU7oI4pAPJ1Ag7U9ONQAAAAAElFTkSuQmCC>

[image11]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFQAAAAPBAMAAACIDPXGAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIlSJq7vN3e+ZdjIQZkTyK+OvAAAAGElEQVR4XmP8z0AsYEIXwA1GlY4qJUEpAKnqAR14HHoYAAAAAElFTkSuQmCC>

[image12]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAcAAAANBAMAAACX52mGAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEHar3e9mRLsyIpnNVIkRoUKfAAAAEklEQVR4XmP8z8DwkYkBCMgkAHy7AgpX6bqBAAAAAElFTkSuQmCC>

[image13]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACwAAAAJBAMAAAC7y9O3AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme+rEM3du4lEZjJ2IlT/AWrmAAAAFElEQVR4XmP8z4ANMKELQMCgFwYA1UgBEVvdsVkAAAAASUVORK5CYII=>

[image14]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAALBAMAAABfd7ooAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARJm7EFQi3e+JMmards2GRuarAAAAE0lEQVR4XmP8z8DA8JGJAQTIIwF9RAIG3tgAgQAAAABJRU5ErkJggg==>

[image15]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAC8AAAAPBAMAAACGpYupAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARJm7EFQi3e+JMmards2GRuarAAAAGElEQVR4XmP8z4AVfGRCF4GBUQkMQLoEANaHAg79gbJ2AAAAAElFTkSuQmCC>

[image16]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADAAAAAPBAMAAABQAFHMAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARJm7EFQi3e+JMmards2GRuarAAAAF0lEQVR4XmP8z4AdMKELwMCoBAYgXQIAjAkBHbM7AzUAAAAASUVORK5CYII=>

[image17]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAADwAAAAPBAMAAABKPLFCAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMARJm7EFQi3e+JMmards2GRuarAAAAF0lEQVR4XmP8z4APMKELoIJRaaxgIKUB608BHUpdYs0AAAAASUVORK5CYII=>

[image18]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABMAAAALBAMAAABv+6sJAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIna73WYQRO8ymYnNq1RFekfLAAAAFElEQVR4XmP8zwAFH5lgLAYGOjAB5bMCBh+Ux20AAAAASUVORK5CYII=>

[image19]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAQAAAAJBAMAAADnQZCTAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIpndq2ZU7xB2u4kyzURERAO4AAAAD0lEQVR4XmP8z8DEgB0BABr0AREmfPr9AAAAAElFTkSuQmCC>

[image20]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAMBAMAAABYTmoeAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZs3vu1QiqzIQ3XaJRJlUPrLcAAAAEklEQVR4XmP8z/CRiYGBgVgMAFueAggn/g/KAAAAAElFTkSuQmCC>

[image21]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAMBAMAAACkW0HUAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAECJEVHaJmbvN3e8yq2bW66NZAAAAEUlEQVR4XmP8zwACTGCSShQAVvEBF2ROGQoAAAAASUVORK5CYII=>

[image22]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAFkAAAATBAMAAAAJ5ryWAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme/dzburIkSJZnYyEFQ2tUYyAAAAHUlEQVR4XmP8z0A8+MiELoIXjKrGBKOqMcHIUA0AtqYCFl/HFbAAAAAASUVORK5CYII=>

[image23]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAPBAMAAAAfXVIcAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAEUlEQVR4XmP8zwABTFB6YBgAjeoBHZ5UvLMAAAAASUVORK5CYII=>

[image24]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAwAAAAJBAMAAAD0ltBnAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme+rEM3du4lEZjJ2IlT/AWrmAAAAEUlEQVR4XmP8zwACTGCSdAoAQDgBEaehpFcAAAAASUVORK5CYII=>

[image25]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAIwAAAATBAMAAACw3vibAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAJElEQVR4XmP8z0ANwIQuQB4YNQY3GDUGNxg1BjcYNQY3oJIxAKhrASWaGdvIAAAAAElFTkSuQmCC>

[image26]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAPBAMAAAAFYbKSAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAEklEQVR4XmP8z4AMmFB4w4ELAO0wAR1vbR+7AAAAAElFTkSuQmCC>

[image27]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABwAAAAPBAMAAAAFYbKSAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAEklEQVR4XmP8z4AMmFB4w4ELAO0wAR1vbR+7AAAAAElFTkSuQmCC>

[image28]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAF0AAAAQBAMAAACGmW5CAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAECJEVHaJmbvN3e8yq2bW66NZAAAAHUlEQVR4XmP8z0AK+MiELkIAjKrHD0bV4we0Vg8A1g0CEBcjxz4AAAAASUVORK5CYII=>

[image29]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAKkAAAATBAMAAAAZqjAPAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAme/dzburIkSJZnYyEFQ2tUYyAAAAIUlEQVR4XmP8z0B98JEJXYQqYNTUUVNHTR01ddTUoWQqAI04AhbYdY8gAAAAAElFTkSuQmCC>

[image30]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAHcAAAARBAMAAAAVui7+AAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAH0lEQVR4XmP8z0A2+MiELkIKGNVMIhjVTCIY1UwiAADpCAIS8LtJ7QAAAABJRU5ErkJggg==>

[image31]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAkAAAAMBAMAAABCcoqQAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIpndq2ZU7xB2u4kyzURERAO4AAAAE0lEQVR4XmP8z8DA8JGJAQQoIQGJdAIIWmdO+gAAAABJRU5ErkJggg==>

[image32]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAAMBAMAAABGh1qtAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIpndq2ZU7xB2u4kyzURERAO4AAAAFElEQVR4XmP8zwAEH5lAJAMDdSgAoF8CCJ6LogkAAAAASUVORK5CYII=>

[image33]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAAJBAMAAAAWSsseAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZt3vzburmXYyIolEEFRxbS86AAAAFElEQVR4XmP8zwAEH5lAJAMDyRQAdeECAjR5M6QAAAAASUVORK5CYII=>

[image34]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAHBAMAAADHdxFtAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAMpnN74lEq927ImYQVHaOqnWsAAAAEUlEQVR4XmP8z8DAwMSAjwAAIvYBDazScAcAAAAASUVORK5CYII=>

[image35]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAOMAAAAPBAMAAADkJmWGAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZt3vzburmXYyIolEEFRxbS86AAAAJ0lEQVR4XmP8z0Bn8JEJXYT2YNRKGoFRK2kERq2kERi1kkZgAKwEAA5yAg72Z3CxAAAAAElFTkSuQmCC>

[image36]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAPBAMAAAAfXVIcAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEDJEZnaZq7vd74nNVCLjteybAAAAEUlEQVR4XmP8zwABTFB6YBgAjeoBHZ5UvLMAAAAASUVORK5CYII=>

[image37]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAQAAAAJBAMAAADnQZCTAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIpndq2ZU7xB2u4kyzURERAO4AAAAD0lEQVR4XmP8z8DEgB0BABr0AREmfPr9AAAAAElFTkSuQmCC>

[image38]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUAAAAMBAMAAABYTmoeAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZs3vu1QiqzIQ3XaJRJlUPrLcAAAAEklEQVR4XmP8z/CRiYGBgVgMAFueAggn/g/KAAAAAElFTkSuQmCC>

[image39]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAAJBAMAAAAWSsseAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZt3vzburmXYyIolEEFRxbS86AAAAFElEQVR4XmP8zwAEH5lAJAMDyRQAdeECAjR5M6QAAAAASUVORK5CYII=>

[image40]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAB0AAAAMBAMAAABsN6sCAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEDJEZnaZq7vd74nNVCLjteybAAAAFUlEQVR4XmP8z4AMPjKhcBkYBjsfAG6xAggUORl2AAAAAElFTkSuQmCC>

[image41]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAG8AAAAPBAMAAAAYH4wJAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEDJEZnaZq7vd74nNVCLjteybAAAAHUlEQVR4XmP8z0AW+MiELkIsGNWIB4xqxAOGkEYAeKMCDp68mmEAAAAASUVORK5CYII=>

[image42]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAPBAMAAAAfXVIcAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAq80y7xAiVJlEZt2JdruNvp7tAAAAEUlEQVR4XmP8zwABTFB6YBgAjeoBHZ5UvLMAAAAASUVORK5CYII=>

[image43]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJ0AAAAUCAMAAACgR8/0AAADAFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAALI7fhAAAAEnRSTlMAq80y7xAiVJlEZt2JdrvXp6FVMTmWAAABjUlEQVR4Xs1V207DMAwNowW6Qh/8/9/YBySEgAlRx3bsOFXaqJ3E0db4bsfz3BCOALzgZFy84F8hr+7MXsATEyPAgbjJFZqrq9obZdWuQGbdydlb6S5Us3ZG2zRA6ncJ443J6WcjXSNuJtqvkTfgEp7jCSF2bs6UW1hGoXadObx50Sb6ETot4oEOmOlLDzyTRVvBOSTabqQ6hJfHi7KnYWoNh/bqM+m4XhN1Ht69YA3mBu4y7E4l28JBMLEARctjQh6JIVqa2zHUPrhsKTQdsiGYjeMvFcRdGRUsofmujXGf5SIHK7pSwUaUO+xBj05YDTKD19biJTc26gZ/G+dN2yACwquh8fPIxhIsqVXqL7sBDBr0xyscSZDqyCc51ZqXxXQey0yZURT5HIx+SQb+5UJqMVLjYggQVHtprCxgR816+VCywIjK4TOxX2GG2jL0/fhefGWdLV+Y/W6zEP1uaJ9T1lEIhm9PBpksMaL9usYcQ7WI6t8e+2mvxJF8m++IeiLfbsI93gSrqBfXiD9+OCwE/p7PjQAAAABJRU5ErkJggg==>

[image44]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAALBAMAAACEzBAKAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAIlSZzd3vEHZmMolEu6tBDbM6AAAAEUlEQVR4XmP8zwABTFCa+gwAZkIBFRa1sv4AAAAASUVORK5CYII=>

[image45]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAJgAAAARBAMAAADTU3gCAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAZt2rELsiiUTvmVQyzXajcYypAAAAIUlEQVR4XmP8z0A9wIQuQAkYNYx0MGoY6WDUMNLBCDEMAHM5ASEFIsSfAAAAAElFTkSuQmCC>

[image46]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAD0AAAALBAMAAAA+b5hqAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAECKZ3avvu3ZURDLNZolJY/pfAAAAFklEQVR4XmP8z4APfGRCF0EDo/L4AQCccAIGW4QzGwAAAABJRU5ErkJggg==>

[image47]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAD8AAAALBAMAAAA6mkhXAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAECKZ3avvu3ZURDLNZolJY/pfAAAAGElEQVR4XmP8z4AXfGRCF0EHowoggKACALFTAgZ57g6eAAAAAElFTkSuQmCC>

[image48]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAACMAAAALBAMAAAAHCCkxAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAECKZ3avvu3ZURDLNZolJY/pfAAAAFUlEQVR4XmP8z4AGPjKhizAwDCEhAIzaAgbg57UJAAAAAElFTkSuQmCC>

[image49]: <data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAGwAAAAQBAMAAAABqIdEAAAAMFBMVEX///8AAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAv3aB7AAAAD3RSTlMAEDJEZnaZq7vd74nNVCLjteybAAAAHElEQVR4XmP8z0AOYEIXIA6MasMAo9owwHDWBgCmLgEfJ0bgGQAAAABJRU5ErkJggg==>