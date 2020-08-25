---
description: File naming pattern and file structure
---

# Data description

## Summary association statistics

GWAS summary statistics \(tab-delimited, bgzipped, genome build 38, filtered to INFO &gt; 0.6, [tabix](https://github.com/samtools/htslib) index files included\) are named as `{endpoint}.gz`. For example, endpoint `I9_CHD` has `I9_CHD.gz` and `I9_CHD.gz.tbi`.

To learn more about the methods used, see section [GWAS](methods/phewas/).

The `{endpoint}.gz` have the following structure:

| Column name | Description |
| :--- | :--- |
| **`#chrom`** | chromosome on build GRCh38 \(`1-22, X`\) |
| **`pos`** | position in base pairs on build GRCh38 |
| **`ref`** | reference allele |
| **`alt`** | alternative allele \(effect allele\) |
| **`rsids`** | variant identifier |
| **`nearest_genes`** | nearest gene name from variant |
| **`pval`** | p-value from [SAIGE](https://github.com/weizhouUMICH/SAIGE) |
| **`beta`** | effect size estimated with [SAIGE](https://github.com/weizhouUMICH/SAIGE) for the alternative allele |
| **`sebeta`** | standard deviation of effect size estimated with [SAIGE](https://github.com/weizhouUMICH/SAIGE) |
| **`maf`** | alternative \(effect\) allele frequency |
| **`maf_cases`** | alternative \(effect\) allele frequency among cases |
| **`maf_controls`** | alternative \(effect\) allele frequency among controls |

## Fine-mapping results

Two fine-mapping methods were used:

* [SuSiE](https://stephenslab.github.io/susie-paper/index.html)
* [FINEMAP](http://www.christianbenner.com)

Fine-mapping results are tab-delimited and bgzipped.

SuSiE results have the following filename pattern:

* `{endpoint}.SUSIE.cred.bgz` 
* `{endpoint}.SUSIE.snp.bgz`

FINEMAP results have the following filename pattern:

* `{endpoint}.FINEMAP.region.bgz`
* `{endpoint}.FINEMAP.snp.bgz`
* `{endpoint}.FINEMAP.cred.bgz`  

To learn more about the methods used, see section [fine-mapping](methods/finemapping.md).

SuSiE output files `{endpoint}.SUSIE.snp.bgz` have the following structure:

| **Column name** | **Description** |
| :--- | :--- |
| **trait** | endpoint name |
| **region** | chr:start-end |
| **v** | variant identifier |
| **rsid** | rs variant identifier |
| **chromosome** | chromosome on build GRCh38 \(`1-22, X`\) |
| **position** | position in base pairs on build GRCh38 |
| **allele1** | reference allele |
| **allele2** | alternative allele \(effect allele\) |
| **maf** | minor allele frequency |
| **beta** | effect size GWAS |
| **se** | standard error GWAS |
| **p** | p-value GWAS |
| **mean** | posterior expectation of true effect size |
| **sd** | posterior standard deviation of true effect size |
| **prob** | posterior probability of association |
| **cs** | identifier of 95% credible set \(-1 = variant is not part of credible set\) |

## LD estimation

Linkage disequilibrium \(LD\) was estimated from [SISU v3](methods/genotype-imputation/sisu-reference-panel.md) for each chromosome. Use the tool [LDstore \(v1.1\)](http://www.christianbenner.com/ldstore_v1.1_x86_64.tgz) for further usage of the bcor files.

`ldstore --bcor FG_LD_chr1.bcor --incl-range 20000000-50000000 --table output_file_name.table`

To learn more about the methods used, see section [LD estimation](methods/genotype-imputation/ld-estimation.md).

