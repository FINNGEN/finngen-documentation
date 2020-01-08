# Association tests

## Null models

For the null model calculation for each endpoint, we used age, sex, 10 PCs and genotyping batch as covariates.

For calculating the genetic relationship matrix, we used 49,811 independent, common, well-imputed variants with a posterior genotyping probability &gt;0.95 and missingness &lt;0.05 \(LD r2 &lt; 0.1, MAF &gt; 0.05, INFO &gt; 0.95\).

[SAIGE](https://github.com/weizhouUMICH/SAIGE/) options for the null computation: 

* `LOCO = false`
* `numMarkers = 30`
* `traceCVcutoff = 0.0025`
* `ratioCVcutoff = 0.001`

## Association tests

We ran association tests against each of the 1,488 endpoints with [SAIGE](https://github.com/weizhouUMICH/SAIGE/) for each variant with a minimum allele count of 10 from the imputation pipeline \(SAIGE option`minMAC = 10`\). The alternative allele is always the effect allele. 

## 

