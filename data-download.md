# Data download

To download FinnGen summary statistics, go to [this link](https://elomake.helsinki.fi/lomakkeet/102575/lomake.html).

## Using FinnGen data for publications

Please remember to **acknowledge** the FinnGen study when using these results in publications. 

You can use the following text: 

> _We want to acknowledge the participants and investigators of FinnGen study_.

## Description

For each endpoint there is a `.gz` and `gz.tbi` file \(tbi generated with [tabix](https://github.com/samtools/htslib)\). For example, endpoint `I9_CHD` has `I9_CHD.gz`  and `I9_CHD.gz.tbi`.

To learn more about the methods used, see [GWAS](methods/phewas/).  

| Column name | Description |
| :--- | :--- |
| `chrom` | chromosome on build GRCh38 \(`1-22, X`\) |
| `pos` | position in base pairs on build GRCh38 |
| `ref` | reference allele |
| `alt` | alternative allele \(effect allele\) |
| `rsids` | variant identifier |
| `nearest_genes` | nearest gene name from variant |
| `pval` | p-value from [SAIGE](https://github.com/weizhouUMICH/SAIGE) |
| `beta` | effect size estimated with [SAIGE](https://github.com/weizhouUMICH/SAIGE) |
| `sebeta` | standard deviation of effect size estimated with [SAIGE](https://github.com/weizhouUMICH/SAIGE) |
| `maf` | minor allele frequency |
| `maf_cases` | minor allele frequency among cases |
| `maf_controls` | minor allele frequency among controls |



