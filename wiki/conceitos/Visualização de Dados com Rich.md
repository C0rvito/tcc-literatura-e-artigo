---
title: "Visualização de Dados com Rich"
tags: ["rich", "python", "visualização", "terminal"]
---

# Visualização de Dados com Rich

A biblioteca **Rich** permite a criação de interfaces ricas, tabelas formatadas e logs coloridos diretamente no terminal Python. No contexto de bioinformática, é utilizada para monitorar o status de pipelines e inspecionar amostras de DataFrames.

## 1. Integração com Pandas

O Pandas não possui integração nativa com o Rich para renderização de tabelas estruturadas. A conversão exige o mapeamento manual do DataFrame para um objeto `rich.table.Table`.

### Exemplo de Implementação
```python
from rich.table import Table
import pandas as pd

def df_to_rich(df: pd.DataFrame, title: str = "") -> Table:
    table = Table(title=title)
    table.add_column("Index", style="dim")
    for col in df.columns:
        table.add_column(str(col))
    for idx, row in df.iterrows():
        table.add_row(str(idx), *[str(v) for v in row])
    return table
```

## 2. Componentes Principais
- **Table**: Renderização de dados tabulares com cores, bordas e alinhamentos automáticos.
- **Tree**: Representação de estruturas hierárquicas, útil para árvores filogenéticas ou logs de execução (ver [[Rastreamento de Execução]]).
- **Panel**: Envelopamento de conteúdo em caixas estilizadas para destacar estágios de processamento.
- **Progress**: Barras de progresso multi-threaded para longas tarefas (ex: processamento de arquivos FASTQ).

## 3. Vantagens na Modelagem de Redes
- **Inspecção de Hubs**: Visualização clara de tabelas de centralidade com cores destacando os genes de maior interesse.
- **Logs de Pipeline**: Substituição de textos desorganizados por painéis que indicam o estado atual da rede (ex: [[Modularidade Hierárquica]] calculada).

## 4. Referências
- [[Nova-conversa-2026-05-22]]
- [[Bibliotecas-Python]]
