---
tags:
  - _durability/fleeting
aliases:
  - dataset
cssclasses:
  - idea
publish: true
---
See also [[cohort-datasets]].

## GSE20257 (idk)
2010
Affymetrix human genome U133 plus 2.0 array
https://doi.org/10.1007/s00018-010-0500-x
airway epithelial cells obtained by bronchoscopy and brushing
23 COPD samples with long-term smoking
53 nonsmoker normal samples
derrived studies:
https://doi.org/10.1016/j.intimp.2021.108308

## Dummy Datasets
### Phenotype dataset
```R
library(wakefield) # devtools::install_github("trinker/wakefield")

myDummyPheno <- r_data_frame(
  n = 500,
  id,
  race,
  age,
  sex,
  hour,
  iq,
  height,
  died
)
```
### DE result dataset
```R
library(tidyverse)
library(normentR) # devtools::install_github("norment/normentR")

gwas.dat <- simulateGWAS(nSNPs = 1e6, nSigCols = 3)

sig.dat <- gwas.dat %>%
  subset(P < 0.05)
notsig.dat <- gwas.dat %>%
  subset(P >= 0.05) %>%
  slice(sample(nrow(.), nrow(.) / 5))
gwas.dat <- rbind(sig.dat,notsig.dat)
```

