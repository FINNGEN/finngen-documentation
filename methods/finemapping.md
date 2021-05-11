# Fine-mapping

We fine-mapped each region from the GWASs where a variant reached p &lt; 1-6. Each region was fine-mapped with [SuSiE](https://github.com/stephenslab/susieR) 0.8.1.0545 and [FINEMAP](http://www.christianbenner.com/) v1.4\_0510.

We used a 3-megabase window \(+- 1.5M\) around each lead variant and merged overlapping regions into one. After merging, a handful of regions became too large to computationally handle with SuSiE. For such regions, we only merged two overlapping pieces when the LD between the two lead variants was r2 &gt; 0.2. When LD was less than that, we made each of the two overlapping regions non-overlapping by splitting the overlap in half.

The codebase, workflow, and inputs we used for R5 fine-mapping is here: [https://github.com/FINNGEN/finemapping-pipeline/releases/tag/r5](https://github.com/FINNGEN/finemapping-pipeline/releases/tag/r5)

## Integration to PheWeb

The "Credible Sets"-table on a phenotype page in the [PheWeb](https://r5.finngen.fi/) browser shows the SuSiE-fine-mapped credible sets of that phenotype. The variant shown per credible set is the maximum PIP \(posterior inclusion probability\) variant of that credible set. In addition to the causal variants, variants that were in sufficient LD \(pearsonr^2 &gt; 0.05\), had a small enough p-value \(pval &lt; 0.01\), and were close enough to the lead variant \(distance to lead variant &lt; 1.5 megabases\) were clumped together with the credible set. Variants have been compared against GWAS Catalog and annotated. The LD grouping, annotation and GWAS Catalog comparison were done using the autoreporting pipeline.

The columns of the table are explained below:

| Column name | Explanation |
| :--- | :--- |
| top PIP variant | variant with largest PIP int he credible set. Click the arrow to the left of the variant to show the credible set variants |
| CS quality | This column shows whether the credible set is well-formed. a 'true' value means that the credible set is likely trustworthy, and a 'false' value means that the credible set is likely not trustworthy. Undefined for R5 |
| chromosome | The chromosome in which the credible set lies |
| p-value | p-value of the top PIP variant |
| effect size \(beta\) | effect size of the top PIP variant |
| Finnish Enrichment | Finnish enrichment of the top PIP variant |
| Alternate allele frequency | alternate allele frequency of the top PIP variant |
| Lead Variant Gene | A probable gene of the top PIP variant |
| \# coding in cs | number of coding variants in the credible set. Hover over the number to see the variant, the consequence, and the correlation \(pearsonr squared\) to the lead variant |
| \# credible variants | number of variants in the credible set |
| Credible set bayes factor \(log10\) | The bayes factor related to the credible set |
| CS matching Traits | Number of matches found in GWAS Catalog for the credible set variants. Hover over the number to see the trait, as well as the associated variant's LD \(pearsonr squared\) to the lead variant. |
| LD Partner Traits | Number of matches found in GWAS Catalog to the group of credible variants and variants in LD with the top PIP variant.Hover over the numbr to see the trait, as well as the associated variant's LD \(pearsonr squared\) to the lead variant. |
| UKBB | Matching Pan-UKBB trait association |

