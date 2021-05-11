# Association tests

## Endpoint

We included ​​**2,803**​ endpoints from the phenotype/registry teams’ pipeline in the analysis. Endpoints with less than 100 cases among the **218,792** samples were excluded.

## Null models

For the null model computation for each endpoint, we used age, sex, 10 PCs and genotyping batch as covariates. Each genotyping batch was included as a covariate for an endpoint if there were at least 10 cases and 10 controls in that batch to avoid convergence issues. One genotyping batch need be excluded from covariates to not have them saturated. We excluded Thermo Fisher batch 16 as it was not enriched for any particular endpoints.

For calculating the genetic relationship matrix, we used the genotype dataset where genotypes with GP &lt; 0.95 have been set missing. Only variants imputed with an INFO score &gt; 0.95 in all batches were used. Variants with &gt; 3 % missing genotypes were excluded as well as variants with MAF &lt; 1 %. The remaining variants were LD pruned with a 1Mb window and r2 threshold of 0.1. This resulted in a set of 58,702 well-imputed not rare variants for GRM calculation.

[SAIGE](https://github.com/weizhouUMICH/SAIGE/) options for the null computation:

* `LOCO = false`
* `numMarkers = 30`
* `traceCVcutoff = 0.0025`
* `ratioCVcutoff = 0.001`

## Association tests

We ran association tests against each of the 2,803 endpoints with [SAIGE](https://github.com/weizhouUMICH/SAIGE/) for each variant with a minimum allele count of 5 from the imputation pipeline \(SAIGE option`minMAC = 5`\). We filtered the results to include variants with an imputation INFO &gt; 0.6.

