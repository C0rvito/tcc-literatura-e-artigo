# Bibliotecas Python para Ciência de Dados e Bioinformática

**Tipo:** Tecnologia / Ferramenta  
**Contexto:** [[Modelagem de Redes Biológicas]]  
**Tags:** #python #software #biologia-sistemas #performance

---

## Visão Geral
Python consolidou-se como a linguagem líder em bioinformática e ciência de redes devido ao seu ecossistema robusto. No contexto de redes biológicas, a escolha da biblioteca impacta diretamente a escalabilidade e a reprodutibilidade dos resultados.

## 1. Manipulação de DataFrames
Ferramentas para processamento de matrizes de expressão e listas de arestas (edge lists).

### Pandas
*   **Status:** Padrão da indústria.
*   **Características:** Baseado em NumPy, execução single-core, avaliação *eager*.
*   **Limitações:** Alto consumo de memória em datasets genômicos massivos.

### Polars
*   **Status:** Alternativa de alta performance.
*   **Características:** Escrito em Rust, motor multi-threaded, avaliação *lazy* (plano de consulta).
*   **Vantagem:** Redução de até 97% no uso de memória em operações de filtragem e 8x mais rápido na leitura de arquivos CSV (Fonte: [[Usando-Polars]]).

## 2. Análise de Redes e Grafos
*   **NetworkX:** A biblioteca mais versátil para manipulação e análise de topologia de grafos, embora lenta para redes de escala muito grande (>10^6 nós).
*   **Graph-tool:** Implementação em C++ com interface Python, extremamente rápida para grandes redes.
*   **iGraph:** Biblioteca multi-linguagem (C, R, Python) otimizada para cálculos de centralidade e detecção de comunidades.

## 3. Computação Científica
*   **NumPy:** Base para cálculos matriciais.
*   **SciPy:** Algoritmos matemáticos e estatísticos (ex: correlação de Pearson/Spearman para [[Redes de Co-expressão]]).
*   **PyArrow:** Formato de memória colunar que facilita a interoperabilidade entre Polars e Pandas.

---

## Relevância na Convergência Fenotípica
A escolha entre essas bibliotecas permite que a pesquisa lide com a heterogeneidade e o volume de dados provenientes de estudos multimodais (transcriptômica + proteômica), garantindo que a análise de [[Hubs (Nós Centrais)]] e [[Centralidade de Intermediação]] seja executada em tempo hábil.

---
**Relacionado:** [[Redes de Co-expressão]], [[Usando-Polars]], [[Modelagem de Redes Biológicas]]
