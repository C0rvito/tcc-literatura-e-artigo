---
title: "py4cytoscape: Programmatic Control of Cytoscape for Network Biology"
source: "https://py4cytoscape.readthedocs.io/"
author: "Cytoscape Consortium"
published: 2024
created: 2026-05-22
description: "Documentation and features of py4cytoscape, a Python package for automating Cytoscape workflows via CyREST."
tags:
  - "raw"
  - "python"
  - "cytoscape"
  - "automation"
  - "network-biology"
---

# py4cytoscape

O `py4cytoscape` é um pacote Python que permite o controle programático do Cytoscape através de sua API REST (CyREST). Ele foi projetado para facilitar fluxos de trabalho de biologia de redes reproduzíveis, conectando o ecossistema de análise de dados do Python (Pandas, NetworkX, igraph) com as capacidades de visualização e análise do Cytoscape.

## Arquitetura
- **CyREST:** Interface baseada em HTTP que serve como núcleo para a automação.
- **Conectividade:** Suporta execução local, via Docker e ponte para Jupyter (Google Colab).

## Integração
- **Pandas:** Criação de redes a partir de DataFrames.
- **NetworkX / igraph:** Conversão bidirecional de grafos.
- **STRING/NDEx:** Importação direta de redes de repositórios públicos.

## Funcionalidades Principais
- **Estilização Visual:** Mapeamentos contínuos, discretos e passthrough.
- **Automação de Apps:** Acesso a funções de Apps como MCODE, Diffusion e StringApp.
- **Exportação:** Geração de imagens e arquivos de rede para publicações.

## Relevância
Essencial para a integração de dados ômicos e análise topológica automatizada no contexto de doenças complexas como Parkinson.
