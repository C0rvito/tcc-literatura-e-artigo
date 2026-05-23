# Manipulação de Dados com Polars

- **Tipo**: Metodologia Computacional / Processamento de Dados
- **Contexto**: [[Modelagem de Redes Biológicas]], [[Bibliotecas-Python]]
- **Tags**: #polars #performance #bioinformatica #lazy-evaluation #data-science

---

## Visão Geral
O **Polars** é uma biblioteca de manipulação de DataFrames de alta performance, escrita em Rust e baseada na especificação Apache Arrow. No contexto de bioinformática, ele resolve o gargalo de memória comum ao processar matrizes de expressão gênica de célula única (*single-cell*) ou listas de interações proteicas que excedem a capacidade do Pandas.

## 1. Core Concepts: Lazy API vs Eager API
Diferente do Pandas (que é puramente *eager*), o Polars introduz a separação entre definição e execução.

### Lazy Evaluation (`scan_csv`)
Em vez de ler o arquivo imediatamente, o Polars cria um **Plano de Consulta Lógico** (*Logical Query Plan*).
- **Otimização de Predicados**: Filtros são "empurrados" para o início do plano (ex: filtrar genes antes de carregar a matriz inteira).
- **Projeção de Colunas**: Apenas as colunas necessárias são lidas do disco.

```python
import polars as pl

# Define o plano (não carrega os dados ainda)
q = (
    pl.scan_csv("expression_data.csv")
    .filter(pl.col("p_value") < 0.05)
    .select(["gene_symbol", "log2_fc"])
)

# Executa as otimizações e retorna o resultado
df = q.collect()
```

## 2. Operações de Entrada e Saída (I/O)
O Polars suporta múltiplos formatos, priorizando o **Parquet** para performance e o **CSV** para interoperabilidade.

### Leitura
```python
# Eager (Carrega tudo na RAM)
df = pl.read_csv("data.csv", separator="\t")
df = pl.read_parquet("data.parquet")

# Lazy (Cria plano de execução)
lf = pl.scan_csv("large_data.csv")
lf = pl.scan_parquet("large_data.parquet")
```

### Escrita
```python
# Salvar como CSV
df.write_csv("output.csv", separator=",")

# Salvar como Parquet (Recomendado para grandes volumes/Bioinfo)
df.write_parquet("output.parquet", compression="snappy")

# Salvar como Excel (Requer biblioteca fastexcel ou xlsxwriter)
df.write_excel("output.xlsx")
```

## 3. API de Expressões
O Polars utiliza uma DSL (*Domain Specific Language*) baseada em expressões que permite o paralelismo nativo.

- **Encadeamento**: Operações complexas são descritas em um único bloco, facilitando a legibilidade.
- **Contextos**: `select`, `with_columns`, `filter` e `group_by`.

### Exemplo: Normalização de Contagens
Equação para cálculo de CPM (*Counts Per Million*):
$$CPM = \frac{count}{total\_counts} \times 10^6$$

```python
df.with_columns(
    (pl.col("counts") / pl.col("counts").sum() * 1e6).alias("CPM")
)
```

## 4. Junções e Transformações (Joins & Melts)
Essencial para integrar dados de expressão com anotações de genes ou listas de caminhos (*pathways*).

### Joins
```python
# Mapear IDs de Ensembl para Gene Symbols
annotated_df = expression_df.join(
    annotation_df, 
    on="ensembl_id", 
    how="left"
)
```

### Reshaping (Melt/Pivot)
Útil para converter matrizes de expressão (formato largo) para formato longo para ferramentas como Seaborn ou ggplot2.
```python
long_df = df.melt(
    id_vars="gene_symbol", 
    variable_name="sample", 
    value_name="expression"
)
```

## 5. Aplicação em [[Redes de Co-expressão]]
A manipulação de listas de arestas (*edge lists*) para [[Convergência Fenotípica]] exige filtros rigorosos de topologia.

- **Filtragem de Peso**: Remoção de arestas fracas em redes ponderadas (WGCNA).
- **Cálculo de Conectividade Local**:
```python
# Cálculo rápido do grau (degree) de cada gene
degree_df = edge_list.group_by("source").agg(
    pl.count("target").alias("k_out")
)
```

## 6. Tratamento de Dados Ausentes
Diferente do Pandas que usa `NaN` (float), o Polars usa `null` (específico do tipo), o que é mais robusto para tipos inteiros ou strings.

```python
# Remover linhas com valores nulos em colunas críticas
clean_df = df.drop_nulls(subset=["gene_symbol", "p_value"])

# Preencher nulos (ex: imputação zero para contagens)
filled_df = df.with_columns(
    pl.col("counts").fill_null(0)
)
```

## 7. Eficiência e Memória: A Arquitetura "Polars Sandwich"
A integração com o ecossistema Python tradicional é otimizada através da arquitetura **Polars Sandwich**.

- **Fronteira**: Polars (Processamento Pesado) -> Apache Arrow -> Pandas (Consumo/Visualização).
- **Zero-copy**: O uso do **Apache Arrow** permite que o Polars entregue ponteiros de memória diretamente para o Pandas via `.collect().to_pandas()`, evitando o custo de cópia real de dados.
- **Regra de Ouro**: Todas as operações de redução de dados (filtros, joins, agregações) devem ocorrer no Polars para que o DataFrame entregue ao Pandas seja a menor unidade necessária para a etapa seguinte.

## 8. Vantagens Competitivas
- **Paralelismo Real**: Escrito em Rust, utiliza todos os núcleos da CPU nativamente.
- **Index-free**: Elimina o conceito de `index` do Pandas, que frequentemente causa overhead de memória e complexidade de código.
- **Tipagem**: Exibe tipos de dados (i64, f64, str) diretamente no terminal, facilitando o debug.

---

## Fontes
- [[Nova-conversa-2026-05-22]]
- [[Usando-Polars]]
- [[Bibliotecas-Python]]
- [[Modelagem de Redes Biológicas]]
- [Documentação Oficial Polars](https://docs.pola.rs/)
