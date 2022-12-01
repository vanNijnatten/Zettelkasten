---
tags: 📱
title: "Dmrff: Identifying differentially methylated regions efficiently with power and control"
aliases:
  - suderman2018
  - sudermanDmrffIdentifyingDifferentially2018
cssclass: article
publish: true
authors:
  - Matthew Suderman
  - James R Staley
  - Robert French
  - Ryan Arathimos
  - Andrew Simpkin
  - Kate Tilling
journal: 
year: 2018
cohorts: none
---
# Dmrff: Identifying differentially methylated regions efficiently with power and control
**DOI:** [10.1101/508556](https://www.doi.org/10.1101/508556)
**Zotero:** [Click here](zotero://select/items/@sudermanDmrffIdentifyingDifferentially2018)
**Authors:**
  - Matthew Suderman
  - James R Staley
  - Robert French
  - Ryan Arathimos
  - Andrew Simpkin
  - Kate Tilling

## Abstract
See also: [[dna-methylation|DNA methylation]] .

DMR: genomic region in which DNA methylation is consistently positive or negatively associate with a phenotype or exposure

Nessecary for proper DMR identification/trying to overcome
- control false positive rates
- low power
- modelling flexibility

## Methods
### DMRff
DMRff does not assume independence between CpG sites, as this is rarely the case. Instead it uses "an extension of inverse-variance weighted meta-analysis"[^1].

- EWAS (limma) effect with the same sign
- EWAS nominal p-value <0.05
- B/S statistic is calculated for each region (distance) and sub-region
  - Most extreme statistic that do not overlap with previously identified candidated
- P-values are Bonferroni-adjusted

### Validation
- Limma for EWAS
- Max distance = 500bp

## Results
...

## Conclusion
...

## Discussion
...

## References
[^1]: [[@burgessCombiningInformationMultiple2016|burgess2016]]
