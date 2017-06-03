
scRNA-Seq Forum
========================================================
date: 07.2017
author: Jens Kleinjung
autosize: true
transition: rotate
transition-speed: slow
incremental: true

[https://github.com/jkleinj/scRNA-Seq_forum](https://github.com/jkleinj/scRNA-Seq_forum)

[https://www.keystonesymposia.org/17e3](https://www.keystonesymposia.org/17e3)


Overview
========================================================
1. Reena Lasrado: single cells from tissue
2. Andreas Sagner: single cells from culture
3. ? : processing of single cells in the NGS facility
4. Julien Delile : pseudo-temporal and large-scale analysis of single cell trajectories
5. Jens Kleinjung : alignment, normalisation and (semi-)supervised analysis of single cell data


scRNA-Seq Alignment
========================================================
- zero, one or two cells
- Alignment of RNA-Seq (fastq) transcripts against reference -ome
- -ome: fasta sequence + annotation
- Tophat2 (genome), Salmon (transcriptome), ...
- Human (ENSEMBL:) and Mouse (ENSEMBL:)
- alignment against spike-ins (important for normalisation)
- create 'spikeIn-ome'
- Transcript counts created by aligner or second program (featureCounts)
- gene names from org.db?

Quality Control and Normalisation
========================================================
- Check the distribution of read counts
- Remove all cells with 'total transcript counts < cut-off'
  (~50000, but other methods might have lower counts)
- Remove all genes with less than 5 counts in 2 samples
- Normalise via design matrix to remove batch effects
- Upper quartile or quantile normalisation (RUVSeq -> DESeq2)
- In difficult cases, more sophisticated normalisation might be required


(Semi-)Supervised Analysis
========================================================
- Currently there is no fully automated analysis of biological processes!
  We can map GO terms, pathways, gene modules and more,
  but the understanding comes from the Biology <=> Bioinformatics exchange.
  Make a Bioinformatician your friend (chocolate helps, a beer as well).
  
1. Differential gene expression
  (contrast between pairs of design groups)
  - two-dimensional clustering
  - gene lists through correlation or regression models
2. Analysis of the covariance matrix
  - PCA, tSNE, SVD
  - Latent factor analysis (scLVM, scran)
  - Pseudo-time as latent factor (Monocle, Wanderlust, DeLorean)
  - Branching trajectories: software emerging this year


Reviews
========================================================
- Alignment Methods
- Normalisation
- Other


Software
========================================================
- Aligners
- Normalisation
- Latent factor decomposition
- Pseudo-time modelling

