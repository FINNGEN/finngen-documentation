# Association tests

## Endpoint 

We included 1,801 endpoints from the phenotype/registry teams’ pipeline in the analysis. Endpoints with OMIT in the endpoint definition file were excluded, as well as endpoints with less than 100 cases among the 135,638 samples. “Smoking: yes” and “Smoking: current or former” were created based on the respective smoking data in the phenotype data file. 

## Null models

For the null model calculation for each endpoint, we used age, sex, 10 PCs and genotyping batch as covariates. 

For calculating the genetic relationship matrix, we used the genotype dataset where genotypes with GP &lt; 0.95 have been set missing. Only variants imputed with an INFO score &gt; 0.95 in all batches were used. Variants with &gt; 3 % missing genotypes were excluded as well as variants with MAF &lt; 5 %. The remaining variants were LD pruned with a 1Mb window and r2 threshold of 0.1. This resulted in a set of 35,557 common, well-imputed variants for GRM calculation. 

[SAIGE](https://github.com/weizhouUMICH/SAIGE/) options for the null computation:

* `LOCO = false`
* `numMarkers = 30`
* `traceCVcutoff = 0.0025`
* `ratioCVcutoff = 0.001`

## Association tests

We ran association tests against each of the 1,801 endpoints with [SAIGE](https://github.com/weizhouUMICH/SAIGE/) for each variant with a minimum allele count of 10 from the imputation pipeline \(SAIGE option`minMAC = 10`\). The alternative allele is always the effect allele.

