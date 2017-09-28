
scRNA-Seq Forum
========================================================
date: 29.07.2017
author: Jens Kleinjung, jens.kleinjung@crick.ac.uk
width: 1920
height: 1080
font-family: 'Helvetica'
navigation: slide
transition: none
transition: rotate
transition-speed: slow
#incremental: true

[https://github.com/jkleinj/scRNA-Seq_forum](https://github.com/jkleinj/scRNA-Seq_forum)


Programme
========================================================

```
15:00 Introduction
```

- 15:05 Sample preparation from tissue. *Reena Lasrado*
- 15:20 Sample preparation from culture. *Andreas Sagner*
- 15:35 Sequencing of single-cell samples. *Marta Costa*

```
15:50 Break
```

- 16:00 10X Genomics. *Scott Brouilette*
- 16:15 Post-processing of single-cell RNA-Seq data. *Jens Kleinjung*
- 16:30 Pseudo-time analysis and lineage reconstruction. *Julien Delile*

```
- 16:45 Discussion
- 17:00 Refreshments, kindly sponsored by 10X Genomics
```


Introduction
========================================================
## Single-cell RNA-Seq Publications

![plot of chunk unnamed-chunk-1](scRNAseq_forum-figure/unnamed-chunk-1-1.png)

<small>
[Keystone Symposia: Single Cell Omics (E3)](https://www.keystonesymposia.org/17e3)
```
Design and computational analysis of single-cell RNA-sequencing experiments.
Rhonda Bacher and Christina Kendziorski, Genome Biology 17 (2016) 63.
DOI 10.1186
```
</small>

***

## Spatio-temporal and Lineage-specific Mapping
<img src="fig/Z_A_PCA.png" title="ENS cells" width="800px" />


scRNA-Seq Post-processing: Alignment
========================================================
- Output of scRNA-Seq run: short (50-100 n) transcript reads in fastq files
- Reference (human, mouse, ) genome or transcriptome: fasta sequence + annotation (UCSC, ENSEMBL, )
- Alignment of transcript reads with reference genome or transcriptome
- Hisat2 (genome), STAR (genome), Kallisto (transcriptome), ...
- Alignment with spike-ins (important for normalisation): create 'spikeIn-ome'
- Transcript counts created by aligner or second program (featureCounts from the subread package)
- Gene names in R from org.Hs.eg.db or org.Mm.eg.db library


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

