---
tags: _durability/permanent
aliases: 
  - DNA methylation
  - DMR
  - CpG site
  - CpG
cssclass: idea
publish: true
---
# DNA methylation
This note should mention
- Array: [[@bibikovaGenomewideDNAMethylation2009|bibikova2009]], [[@bibikovaHighDensityDNA2011|bibikova2011]]
- DNA methylation sequencing: [[@morrisonEvaluationWholegenomeDNA2021|morrison2021]], [[@rauluseviciuteDNAMethylationData2019|rauluseviciute2019]]
- Processing: [[@aryeeMinfiFlexibleComprehensive2014|aryee2014]] (minfi), [[@pidsleyDatadrivenApproachPreprocessing2013|pidsley2013]] (wateRmelon)
- DMRs packages review: [[@lentDetectingDifferentiallyMethylated2021|lent2021]], [[@sudermanDmrffIdentifyingDifferentially2018|suderman2018]]
- DMR packages: [[@lentComparisonNovelExisting2018|lent2018]] (dmrff), [[@pedersenCombpSoftwareCombining2012|pedersen2012]](comb-p), [[@petersNovoIdentificationDifferentially2015|peters2015]](dmrcate), [[@koldeSeqlmMDLBased2016|kolde2016]](seqlm), [[@jaffeBumpHuntingIdentify2012|jaffe2012]](bumphunter), (globalP), (Aclust), (GetisDMR), (DMRFinder), (Probe Lasso), (DMRMark), (SKAT), (aSPUw)

To date, a number of methods have been developed to detect/quantify DNA methylation including: high-performance capillary electrophoresis (4) and methylation-sensitive arbitrarily primed PCR (5). However, the most common technique used today remains the bisulfite conversion method (6). This technique involves treating methylated DNA with bisulfite, which converts unmethylated cytosines into uracil. Methylated cytosines remain unchanged during the treatment. Once converted, the methylation profile of the DNA can be determined by PCR amplification followed by DNA sequencing (see next page). https://fnkprddata.blob.core.windows.net/domestic/data/datasheet/ZYR/D5023.pdf
(spontaneous) deamination = cytosine => uracil. uracil-DNA glycosylase  is there to repair the DNA
5-methylcytosine => thymine. uracil-DNA glycosylase cannot repair the DNA. Mismatch repair (really inefficient) via thymine-DNA glycosylase (TDG). Because of this inefficient mechanism, methylation is the most stable epigenetic marker.
CG suppression
cpg-island = at least 200 bp in length, GC% > 50%, Observed/Expected CpG ratio > 60%, tend to be unmethylated. (cpg islands tend to be in active regions with active genes as the cpgs are unmethylated - they are protected). 70% of human promotors have high percentages of cpgs
cpg sites are expected to occur in the genome at 6,...%, however only occur about 1%
SssI methylase, which globally methylates all double-stranded CpG sites
bisulfite conversion can fragment DNA ?
Ten‑eleven translocation (TET) enzymes remove methylation: 5mC is first converted to 5-hydroxymethyl cytosine (5hmC), Then to 5-formylcytosine (5fC), then to 5-carboxylcytosine (5caC), each by TET1-3 (Ito et al., 2011), 5fC and 5caC can both be converted to unmodified Cytosine by Terminal deoxynucleotidyl transferase (TdT).
DNA methyltransferases (DNMTs) are present in the human genome. Three of them (DNMT1, DNMT3A and DNMT3B) catalyze the addition of a methyl-group to 5mC. Two (DNMT2 and DNMT3L) have the motif present to do so, but lack the DNMT activity.

## Methylation methods
A number of methods have been developed to detect and quantify DNA methylation:
 - High-performance capillary electrophoresis
 - Methylation-sensitive arbitrarily primed PCR
 - Bisulfite conversion method (most common used technique)

DNA Methylation protocols almost always include a bisulfite processing step.
Unmethylated Cytosine will be transformed to Uracil during this process. Then during the PCR step, the Uracil will be transcribed as a Thymine. The methylated Cytosine (also known as 5-methylcytosine) will stay the same.

### Methyl-Seq / Bisulfite-Seq
...

### Illumina Infinium microarray

> [!NOTE] Alternative names
> Infinium Human Methylation 25K BeadChip
> Infinium Human Methylation 450K BeadChip
> Infinium MethylationEPIC microarray

Company: Illumina
Infinium = microarray technology [workflow][https://www.illumina.com/Documents/products/workflows/workflow_infinium_ii.pdf]
Beadchip


https://www.illumina.com/science/technology/microarray.html
https://www.illumina.com/documents/products/technotes/technote_hm450_data_analysis_optimization.pdf

https://www.illumina.com/content/dam/illumina/gcs/assembled-assets/marketing-literature/automated-bisulfite-infinium-methylation-tech-note-m-gl-00144/automated-bisulfite-Infinium-methylation-tech-note-m-gl-00144.pdf
https://support.illumina.com/bulletins/2016/02/which-bisulfite-conversion-kit-should-i-use-for-the-infinium-methylation-arrays.html
https://www.zymoresearch.com/products/ez-96-dna-methylation-kit

https://www.youtube.com/watch?v=bc3wtVXyAXo

## Statistics
Because commonly used β values are heteroscedastic, M values were used for all statistical tests where equal variance is assumed ([29](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4068945/#bib29), [30](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4068945/#bib30))

## Gene
regulatory region, transcription start, 5' untranslated region, start codon, open reading frame, stop codon, 3' untranslated region, transcription end
upstream enhancer, tata box (transcription start), promotor sequences, introns, exons
x chromosome silencing
- Genes involved in DNA methylation: ... [^1]
  - DNA methyltransferases (DNMTs: [[DNMT1]], [[DNMT3A]], [[DNMT3B]])
## References

[^1]: [[@mooreDNAMethylationIts2013|Moore2013]]