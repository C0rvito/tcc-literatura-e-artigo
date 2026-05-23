# py4cytoscape: Automação e Visualização de Redes Biológicas

**Título Original:** py4cytoscape: Programmatic Control of Cytoscape for Network Biology  
**Fonte:** [Documentação Oficial py4cytoscape](https://py4cytoscape.readthedocs.io/)  
**Data de Publicação:** 2024  
**Data de Ingestão:** 22-05-2026  
**Tags:** #ferramentas #python #cytoscape #automacao #visualizacao #biologia-sistemas

---

## 1. Resumo Técnico e Arquitetura
O `py4cytoscape` é o sucessor do `RCy3` (para R), fornecendo um wrapper Python robusto sobre a API **CyREST** do Cytoscape. Sua arquitetura permite que scripts Python controlem quase todos os aspectos do software Cytoscape.

### Infraestrutura de Comunicação
*   **Protocolo:** HTTP/REST via porta 1234 (padrão).
*   **Modos de Operação:**
    *   **Local:** Comunicação direta entre Python e Cytoscape na mesma máquina.
    *   **Remote/Cloud:** Uso do `Jupyter-Bridge` para conectar notebooks remotos (Google Colab) a instâncias locais.
*   **Núcleo:** Baseado no Apache Arrow para eficiência na transferência de tabelas de dados.

---

## 2. Metodologia de Integração
A biblioteca atua como uma ponte entre o ecossistema analítico do Python e a visualização profissional do Cytoscape.

### Fluxo de Dados
1.  **Entrada:** Suporta `Pandas.DataFrame`, `NetworkX.Graph` e `igraph.Graph`.
2.  **Conversão:** `create_network_from_data_frames()` converte tabelas de arestas e nós em redes do Cytoscape.
3.  **Análise Externa:** Integração com bases como **STRING** e **NDEx** via funções dedicadas.

---

## 3. Sintaxe e Funcionalidades Principais
Exemplos aplicados ao contexto de [[Modelagem de Redes Biológicas]].

### Criação de Estilos Visuais
Mapear dados de expressão gênica (ex: log2 Fold Change) para cores de nós:
```python
import py4cytoscape as p4c

# Mapeamento contínuo: Baixa expressão (Azul) -> Alta expressão (Vermelho)
p4c.set_node_color_mapping('log2FC', [-2, 0, 2], ['#0000FF', '#FFFFFF', '#FF0000'])
```

### Automação de Sub-redes
Criar uma sub-rede contendo apenas genes de uma via específica (ex: [[Via Autofagia-Lisossomo]]):
```python
p4c.select_nodes(['GBA', 'LRRK2', 'SNCA'], by_col='name')
p4c.create_subnetwork(subnetwork_name='Via_Interesse')
```

---

## 4. Relevância para a Tese (Convergência Fenotípica)
1.  **Reprodutibilidade:** Garante que a visualização da rede em Parkinson seja idêntica em cada execução do script.
2.  **Escalabilidade Visual:** Permite aplicar estilos complexos a redes de larga escala (ex: interatoma completo) que seriam impossíveis de configurar manualmente.
3.  **Análise de Apps:** Acesso programático a algoritmos de detecção de comunidades (MCODE) e difusão de rede, cruciais para identificar pontos de [[Convergência Fenotípica]].

---

## Citações Chave
> "O py4cytoscape facilita fluxos de trabalho de biologia de redes reproduzíveis, conectando Python ao ambiente de visualização do Cytoscape."

---
**Relacionado:** [[Bibliotecas-Python]], [[Visualização de Redes com py4cytoscape]], [[Modelagem de Redes Biológicas]], [[Grafo de Conhecimento]]
