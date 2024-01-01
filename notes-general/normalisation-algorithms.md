---
tags: _durability/fleeting 
aliases: 
  - logcpm
  - cpm
  - logrpkm
  - rpkm
  - vst
  - voom
cssclass: idea
publish: true
---

See also [[statistics-writing|statistics]]

# Normalisation
<mark style="background: #FFF3A3A6;">TODO</mark>:
- When is each method used?

## CPM
Used in [[edger|EdgeR]] as the function `edger::cpm()`. _CPM_ literally means 'Counts Per Million'. A raw CPM calculated from a count matrix is
$$CPM=\cfrac{count}{lib size}*1\mathrm{e}{6}$$
In which _count_ is the count for a given gene in a sample, and _libsize_ is the total reads in a sample.

See also [[CPM.xlsx]].

## Log<sub>2</sub>(CPM)
Used in [[limma|Limma]] as the function `limma::voom()`. _Log<sub>2</sub>(CPM)_ is the log (base 2) transformed version of _CPM_. The calculation however is totally different and takes into account a _prior_. This _prior_ is a number (per sample) added to the gene counts to make sure the log transformation can also happen even if the count for a gene is 0.

## RPM
... [^1]

## RPKM
Used in [[edger|EdgeR]]? _RPKM_ literally means 'Reads Per Kilobase per Million'.
... [^1] [^2]

## FPKM
... [^1] [^2] [^3]

## TMM
Used in [[edger|EdgeR]]. 
...

## TPM
_TPM_ literally means 'Transcripts per Million'. This is a method for normalising the library sizes, rather than normalising read counts. [^1] [^2] [^3]

## FPM
... [^1] [^2] [^3]

## VST
Used in [[deseq2|DESeq2]]. _VST_ literally means 'Variance Stabilizing Transformation'.

## Quantile Normalisation
(methylation? R package: quantro?)
... [^4]

## Others
 - RLE ([[deseq2|DESeq2]])
 - MRN (???)

# References:
[^1]: https://www.biostars.org/p/273537/
[^2]: https://www.youtube.com/watch?v=TTUrtCY2k-w
[^3]: https://haroldpimentel.wordpress.com/2014/05/08/what-the-fpkm-a-review-rna-seq-expression-units/
[^4]: https://www.biorxiv.org/content/10.1101/012203v1