# Park et al. (2026) - GBA1 deficiency differentially affects endolysosomal trafficking in neurons versus astrocytes

- **Fonte**: `raw/GBA.pdf` (bioRxiv preprint)
- **Autores**: Anna J. Park, Sarah L. Fish, Colby L. Samstag, Minsuh Kim, et al. (Laboratório de Marie Y. Davis)
- **Ano**: 2026
- **Tema**: Efeitos específicos de tipo celular da deficiência de GBA1 no tráfego endolisossômico e na alfa-sinucleinopatia em neurônios dopaminérgicos e astrócitos.

## Metodologia Detalhada
- **Modelos In Vitro**: Células iPSC humanas derivadas de fibroblastos de um indivíduo com Doença de Parkinson portador da variante nula heterozigota *GBA1* IVS2+1 G>A (*GBA1* IVS/+).
    - **Edição Genômica (CRISPR/Cas9)**: Geração de controle isogênico (*GBA1* +/+ Rev) e clone homozigoto nulo (*GBA1* IVS/IVS). Utilizou-se o RNP complex com gRNA (GGCATCAGATGAGTGAGTCA).
    - Diferenciação para neurônios dopaminérgicos do mesencéfalo (validados por anti-MAP2 e anti-TH) e astrócitos (validados por anti-S100β e GFAP).
- **Inibição Farmacológica**: Uso de Conduritol B epoxide (CBE) 100mM para inibição irreversível da glicocerebrosidase (GCase) como controle positivo.
- **Ensaios Enzimáticos**: Atividade da GCase medida pela clivagem do substrato sintético fluorescente 4-metilumbeliferil-beta-D-glicopiranosídeo (4-MUG).
- **Microscopia Confocal e Análise Morfológica (Imaris)**: Reconstrução 3D usando Imaris 9.9.0 para quantificar o tamanho e volume de compartimentos endolisossômicos com os marcadores EEA1 (endossomos iniciais), LAMP1 (lisossomos) e Rab11 (endossomos de reciclagem).
- **Imunocitoquímica (ICC) e Western Blot**: Avaliação de níveis e agregação de alfa-sinucleína (monômeros, oligômeros insolúveis em Triton X-100 e pSer129).
- **Sequenciamento de RNA (RNA-Seq)**: Illumina NovaSeq X Plus 2x150bp.

## Algoritmos e Parâmetros
- **Alinhamento e Quantificação**: Trimmomatic v0.36 para trimming, STAR v2.5.2b para alinhamento ao genoma GRCh38, e Subread v1.5.2 para contagem de reads exônicas.
- **Análise de Expressão Diferencial**: Pacote DESeq2 no R. Critérios de corte: adjusted p-value < 0.05 e |log2 fold change| > 0.5.
- **GSEA**: Análise de enriquecimento usando fGSEA v1.34.2 contra o banco de dados MSigDB Reactome, com rankings baseados em Z-scores combinados (Estatística de Fisher).

## Resultados Quantitativos
- **Expressão e Atividade de GBA**: GBA1 IVS/IVS apresentou atividade enzimática quase indetectável; expressão transcriptômica reduzida em 80% nos neurônios e 64% nos astrócitos. O gene [[GBA2]] (GCase citosólica) foi upregulado em 103% em astrócitos GBA1 IVS/IVS.
- **Diferenças Transcriptômicas**:
    - **Neurônios deficientes em GBA1**: Maioria dos DEGs (Differentially Expressed Genes) downregulated (1.398 downregulated, 576 upregulated). Houve regulação positiva nas vias de síntese de colesterol e negativa nas vias de sinalização imune. O transcrito para [[EEA1]] foi reduzido em 62% nos neurônios GBA1 IVS/+.
    - **Astrócitos deficientes em GBA1**: Maioria dos DEGs upregulated (1.007 upregulated, 438 downregulated). Aumento em vias de biogênese de matriz extracelular, vias de efluxo de lipídios ([[APOE]]) e assinatura neurotóxica A1 (ex: CXCL1, CHI3L1).
    - **Sobreposição Celular**: Apenas 255 DEGs foram compartilhados entre ambos os tipos celulares, focados primariamente em metabolismo lipídico, estresse do Retículo Endoplasmático (ER) e interação mitocôndria-lisossomo.
- **Tráfego Endolisossômico**: 
    - **Neurônios**: Aumento volumétrico significativo dos compartimentos endolisossômicos iniciais ([[EEA1]]), tardios/lisossomais ([[LAMP1]]) e de reciclagem ([[RAB11A]]).
    - **Astrócitos**: Não apresentaram aumento compartimental endolisossômico estatisticamente significativo com a mutação genética (apenas com tratamento por CBE).
- **Alfa-Sinucleína ([[SNCA]])**: 
    - Agregados insolúveis de alto peso molecular (~120 kD octâmeros) e aumento de pSer129 encontrados exclusivamente em neurônios deficientes em GBA1, mas **não** nos astrócitos, sugerindo suscetibilidade celular divergente.

## Limitações
- Estudo embasado fortemente em uma mutação nula/truncante drástica (IVS2+1) e no modelo inibidor CBE, o que pode não reproduzir fidedignamente o stress do retículo induzido por mutações missense comuns de ganho de função tóxica ou misfolding na DP (como N370S ou L444P).
- CBE pode inibir não apenas GBA1 mas também GBA2, acentuando respostas em controles positivos.
- A diferenciação em iPSCs pode sofrer viés de edição, forçando o uso de linhagens celulares controle não consanguíneas após variações notadas nos clones isogênicos ("isogenic Rev").

## Citações Chave
- "GBA1 deficiency has cell type-specific effects, with increased neuronal vulnerability to endolysosomal trafficking leading to -synucleinopathy while GBA1 deficiency in astrocytes leads to increased neurotoxic reactivity independent of endolysosomal trafficking and -synucleinopathy."
