---
tags: 🏛 🔬 ✍️ 🔖 
aliases:
  - pidsley2013
  - pidsleyDatadrivenApproachPreprocessing2013
cssclass: article
publish: true
authors:
  - Ruth Pidsley
  - Chloe C Y Wong
  - Manuela Volta
  - Katie Lunnon
  - Jonathan Mill
  - Leonard C Schalkwyk
article-type: research
journal: BMC Genomics
year: 2013
cohorts: none
---
# A data-driven approach to preprocessing Illumina 450K methylation array data
**DOI:** [10.1186/1471-2164-14-293](https://www.doi.org/10.1186/1471-2164-14-293)
**Zotero:** [Click here](zotero://select/items/@pidsleyDatadrivenApproachPreprocessing2013)

## Abstract
Over here I should write shortly what this paper is about, their hypothesis and their main findings
> Abstract Background As the most stable and experimentally accessible epigenetic mark, DNA methylation is of great interest to the research community. The landscape of DNA methylation across tissues, through development and in disease pathogenesis is not yet well characterized. Thus there is a need for rapid and cost effective methods for assessing genome-wide levels of DNA methylation. The Illumina Infinium HumanMethylation450 (450K) BeadChip is a very useful addition to the available methods for DNA methylation analysis but its complex design, incorporating two different assay methods, requires careful consideration. Accordingly, several normalization schemes have been published. We have taken advantage of known DNA methylation patterns associated with genomic imprinting and X-chromosome inactivation (XCI), in addition to the performance of SNP genotyping assays present on the array, to derive three independent metrics which we use to test alternative schemes of correction and normalization. These metrics also have potential utility as quality scores for datasets. Results The standard index of DNA methylation at any specific CpG site is β = M /( M + U + 100) where M and U are methylated and unmethylated signal intensities, respectively. Betas ( β s) calculated from raw signal intensities (the default GenomeStudio behavior) perform well, but using 11 methylomic datasets we demonstrate that quantile normalization methods produce marked improvement, even in highly consistent data, by all three metrics. The commonly used procedure of normalizing betas is inferior to the separate normalization of M and U, and it is also advantageous to normalize Type I and Type II assays separately. More elaborate manipulation of quantiles proves to be counterproductive. Conclusions Careful selection of preprocessing steps can minimize variance and thus improve statistical power, especially for the detection of the small absolute DNA methylation changes likely associated with complex disease phenotypes. For the convenience of the research community we have created a user-friendly R software package called wateRmelon, downloadable from bioConductor, compatible with the existing methylumi, minfi and IMA packages, that allows others to utilize the same normalization methods and data quality tests on 450K data.

## Methods
...

## Results
...

## Conclusion
...

## Discussion
...

## References
- [[@bibikovaGenomewideDNAMethylation2009]]