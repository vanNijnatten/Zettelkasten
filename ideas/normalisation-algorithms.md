---
tags: ✍️
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
# Normalisation

## CPM (EdgeR)
_CPM_ litterally means 'Counts Per Million'. A raw CPM calculated from a count matrix is
$$CPM=\cfrac{count}{lib size}*1\mathrm{e}{6}$$
In which _count_ is the count for a given gene in a sample, and _libsize_ is the total reads in a sample.

_LogCPM_ is the log (base 2) transformed version of _CPM_. The calculation however is totally different and takes into account a _prior_. This _prior_ is a number (per sample) added to the gene counts to make sure the log transformation can also happen even if the count for a gene is 0.

See also [[CPM.xlsx]].

## RPKM (EdgeR)

## TMM (EdgeR)

## VST (DESeq2)
Variance Stabilizing Transformation

## Voom (Limma)

## Others
 - RLE (DESeq2)
 - MRN (???)
