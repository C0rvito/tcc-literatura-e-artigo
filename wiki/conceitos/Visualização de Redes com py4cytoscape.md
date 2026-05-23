# Visualização de Redes com py4cytoscape

- **Tipo**: Metodologia Computacional / Visualização Científica
- **Contexto**: [[Modelagem de Redes Biológicas]], [[Bibliotecas-Python]]
- **Tags**: #cytoscape #visualizacao #python #reprodutibilidade #biologia-sistemas

---

## Visão Geral
A visualização de redes em biologia de sistemas não é apenas estética, mas uma forma de representar dados multivariados sobre uma topologia complexa. O **py4cytoscape** permite que essa visualização seja definida por código, garantindo que o mapeamento de dados (ex: níveis de proteína, significância estatística) seja preciso e reprodutível.

## 1. Mapeamento de Dados (*Visual Mappings*)
O núcleo da visualização programática é transformar atributos de tabelas (nós/arestas) em propriedades visuais.

### Mapeamento Contínuo (*Continuous Mapping*)
Utilizado para dados numéricos (ex: *p-values*, *fold change*).
- **Exemplo**: Mapear o grau de conectividade ($k$) para o tamanho do nó.
$$Tamanho = f(k)$$

### Mapeamento Discreto (*Discrete Mapping*)
Utilizado para categorias (ex: tipo de gene, compartimento celular).
- **Exemplo**: Diferenciar receptores de fatores de transcrição por formas de nós (elipse vs. retângulo).

### Mapeamento Direto (*Passthrough Mapping*)
Utiliza o valor da coluna diretamente como a propriedade visual (ex: nomes de genes como rótulos).

## 2. Fluxo de Trabalho Bioinformático
O uso do `py4cytoscape` segue geralmente este padrão:

1.  **Criação da Rede**: Importação de um `Pandas.DataFrame` ou `NetworkX.Graph`.
2.  **Aplicação de Layout**: Escolha de algoritmos de força (ex: *Prefuse Force Directed*) ou circulares.
3.  **Estilização**: Definição de cores, tamanhos e formas baseadas em resultados de análise (ex: [[Module Eigengene]] do WGCNA).
4.  **Anotação**: Adição de legendas e imagens para publicação.

## 3. Integração com Apps
O Cytoscape possui um ecossistema de Apps que podem ser chamados via `py4cytoscape`:
- **STRINGApp**: Importação automática de redes de interação proteína-proteína (PPI).
- **MCODE**: Detecção de complexos densamente conectados.
- **Diffusion**: Expansão de redes a partir de nós semente (*seeds*), útil para encontrar novos genes associados à [[Doença de Parkinson]].

## 4. Vantagens na [[Convergência Fenotípica]]
- **Comparação Visual**: Permite gerar redes idênticas para diferentes mutações (ex: [[GBA]] vs [[LRRK2]]) com a mesma escala visual, facilitando a identificação de sobreposições topológicas.
- **Destaque de Hubs**: Automatiza o destaque visual de [[Hubs (Nós Centrais)]] identificados matematicamente.

---

## Fontes
- [[py4cytoscape-Docs]]
- [[Bibliotecas-Python]]
- [[Modelagem de Redes Biológicas]]
- [Cytoscape Automation Guide](https://manual.cytoscape.org/en/stable/Automation.html)
