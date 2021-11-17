
# Comparison report, differential expression of RNAseq data
Created by the compcodeR package, version 1.30.0

Date: Wed Nov 17 18:40:38 2021

Data set:

```
syn_data
```
Number of samples per condition:

```
5
```
Included replicates (for repeated simulated data sets):

```
1
```
Differential expression methods included in the comparison:

```
voom.3.50.0.limma.TMM
edgeR.3.36.0.exact.TMM.movingave.tagwise
ttest.1.76.0.TMM
```
Parameter values:

```
                   value
fdr.threshold       0.05
tpr.threshold       0.05
typeI.threshold     0.05
mcc.threshold       0.05
ma.threshold        0.05
fdc.maxvar          1500
overlap.threshold   0.05
fracsign.threshold  0.05
nbrtpfp.threshold   0.05
signal.measure      mean
```
---

<a name='contents'></a>
## Contents
- [False discovery rate](#fdr)

- [True positive rate](#tpr)

- [Spearman correlation between scores, single replicate](#correlation)

---

---
<a name='fdr'></a>
## FDR [(Contents)](#contents)
The false discovery rate (FDR) indicates the fraction of truly non-differentially expressed genes that we expect to find among the genes that we consider to be differentially expressed. For high-dimensional problems, where many statistical tests are performed simultaneously (such as gene expression studies) it is more relevant to attempt to control the FDR than to control the gene-wise type I error rate, since it is almost certain that at least one gene will show a low nominal p-value even if the null hypothesis is true. To control the FDR, typically, the nominal p-values are adjusted for the large number of tests that are performed. The figures below indicate the observed rate of false discoveries (i.e., the fraction of truly non-differentially expressed genes among the genes that are considered significant) at an adjusted p-value threshold of 0.05. Only methods returning corrected p-values or FDR estimates are included. Each boxplot summarizes the values obtained across all data set replicates that are included in the comparison. For a good method, the observed FDR should not be too high above the imposed adjusted p-value threshold (indicated by a dashed vertical line). If the observed FDR is much larger than the imposed adjusted p-value threshold, the fraction of false discoveries is not controlled at the claimed level. 

<img src="C:/Users/domin/Desktop/R/GenomeW3/compcodeR_figurefdr-1.png" width="1344" style="display: block; margin: auto auto auto 0;" />
---
<a name='tpr'></a>
## TPR [(Contents)](#contents)
The true positive rate (TPR) indicates the fraction of truly non-differentially expressed genes that are indeed considered significant by a method at a given significance threshold. A good method gives a high true positive rate, while at the same time keeping the false discovery rate under control. The figures below show the observed rate of true positives at an adjusted p-value threshold of 0.05. Only methods returning corrected p-values or FDR estimates are included. Each boxplot summarizes the values obtained across all data set replicates included in the comparison.

<img src="C:/Users/domin/Desktop/R/GenomeW3/compcodeR_figuretpr-1.png" width="1344" style="display: block; margin: auto auto auto 0;" />
---
<a name='correlation'></a>
## Spearman correlation between scores [(Contents)](#contents)
The table below shows, for each pair of compared differential expression methods, the Spearman correlation between the scores that they assign to the genes. The value of the correlation is always between -1 and 1, and a high positive value of the Spearman correlation indicates that the compared methods rank the genes in a similar fashion. The results are also shown in a 'heatmap', where the color indicates the Spearman correlation. Finally, the methods are clustered using hierarchical clustering, with a dissimilarity measure defined as 1 - Spearman correlation. This visualizes the relationships among the compared differential expression methods, and groups together methods that rank the genes similarly.

#### 5  samples/condition [(Contents)](#contents)

```
                                         voom.3.50.0.limma.TMM
voom.3.50.0.limma.TMM                                1.0000000
edgeR.3.36.0.exact.TMM.movingave.tagwise             0.8807225
ttest.1.76.0.TMM                                     0.9061983
                                         edgeR.3.36.0.exact.TMM.movingave.tagwise
voom.3.50.0.limma.TMM                                                   0.8807225
edgeR.3.36.0.exact.TMM.movingave.tagwise                                1.0000000
ttest.1.76.0.TMM                                                        0.9267768
                                         ttest.1.76.0.TMM
voom.3.50.0.limma.TMM                           0.9061983
edgeR.3.36.0.exact.TMM.movingave.tagwise        0.9267768
ttest.1.76.0.TMM                                1.0000000
```

<img src="C:/Users/domin/Desktop/R/GenomeW3/compcodeR_figurecorrelation-1-1.png" width="576" style="display: block; margin: auto auto auto 0;" /><img src="C:/Users/domin/Desktop/R/GenomeW3/compcodeR_figurecorrelation-1-2.png" width="576" style="display: block; margin: auto auto auto 0;" />
---
