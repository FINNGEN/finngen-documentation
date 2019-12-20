# GWAS

We used the SAIGE software for running the R2 GWAS for

* 2,444 endpoints
* 176,899 analyzed samples
* 16,962,023 variants
* covariates: sex, age, 10 PCs, genotyping batch

SAIGE is a mixed model logistic regression R/C++ package. We used code of version 0.35.8.8: [https://github.com/weizhouUMICH/SAIGE/releases/tag/0.35.8.8](https://github.com/weizhouUMICH/SAIGE/releases/tag/0.35.8.8)

## Principles

* All positions are on GRCh38
* Variant identifiers are \`chr&lt;CHR&gt;\_&lt;POS&gt;\_&lt;REF&gt;\_&lt;ALT&gt;\`
* Chromosomes are either indicated with numbers \(\`1-25\`\) or letters \(\`chr1-chr22\`, \`chrX\`, \`chrY\`, \`chrMT\`\)

Github repository: [https://github.com/FINNGEN/saige-pipelines](https://github.com/FINNGEN/saige-pipelines)

## 

