# GWAS

We used the SAIGE software for running the R2 GWAS for 
- 2,444 endpoints
- 176,899 analyzed samples
- 16,962,023 variants
- covariates: sex, age, 10 PCs, genotyping batch

SAIGE is a mixed model logistic regression R/C++ package. We used code of version 0.35.8.8: https://github.com/weizhouUMICH/SAIGE/releases/tag/0.35.8.8


## Principles

* All positions are on GRCh38
* Variant identifiers are \`chr&lt;CHR&gt;\_&lt;POS&gt;\_&lt;REF&gt;\_&lt;ALT&gt;\`
* Chromosomes are either indicated with numbers \(\`1-25\`\) or letters \(\`chr1-chr22\`, \`chrX\`, \`chrY\`, \`chrMT\`\)

Github repository: [https://github.com/FINNGEN/saige-pipelines](https://github.com/FINNGEN/saige-pipelines)

## Null models
For the null model computation for each endpoint, we used age, sex, 10 PCs and genotyping batch as covariates. Each genotyping batch was included as a covariate for an endpoint if there were at least 10 cases and 10 controls in that batch to avoid convergence issues. One genotyping batch need be excluded from covariates to not have them saturated. We excluded Thermo Fisher batch 16 as it was not enriched for any particular endpoints.
For calculating the genetic relationship matrix, we used the genotype dataset where genotypes with GP < 0.95 have been set missing. Only variants imputed with an INFO score > 0.95 in all batches were used. Variants with > 3 % missing genotypes were excluded as well as variants with MAF < 1 %. The remaining variants were LD pruned with a 1Mb window and r2 threshold of 0.1. This resulted in a set of 58,888 well-imputed not rare variants for GRM calculation.
SAIGE options for the null computation were - LOCO false
- numMarkers 30
- traceCVcutoff 0.0025
- ratioCVcutoff 0.001

## Association tests
We ran association tests against each of the 2,444 endpoints with SAIGE for each variant with a minimum allele count of 5 from the imputation pipeline (SAIGE option minMAC = 5). We filtered the results to include variants with an imputation INFO > 0.6.


## Summary statistics
GWAS summary stats (tab-delimited, bgzipped, genome build 38, filtered to INFO > 0.6, tabix index files included) are available in
gs://finngen-production-library-green/finngen_R4/finngen_R4_analysis_data/summary_st ats/release/
Manhattan and QQ plots are located in
gs://finngen-production-library-green/finngen_R4/finngen_R4_analysis_data/summary_st ats/plots/
Endpoint case/control counts for analyzed samples, genomic control lambdas, approximate number of genome-wide significant loci (crude 500kb window, LD not considered):
gs://finngen-production-library-green/finngen_R4/finngen_R4_analysis_data/finngen_R4_ pheno_n.tsv
Additional files
The covariate/phenotype file is available in the red library
/finngen_R4/finngen_R4_phenotype_2.0/finngen_R4_phenotype_data/finngen_R4_cov_p heno_1.0.txt.gz
FinnGen variant annotations (tabix index included) are available in
gs://finngen-production-library-green/finngen_R4/finngen_R4_analysis_data/annotations/ finngen_R4_annotated_variants.gz

