# GWAS

We used the [SAIGE](https://github.com/weizhouUMICH/SAIGE/) software for running the R2 GWAS. 

[SAIGE](https://github.com/weizhouUMICH/SAIGE/) is a mixed model logistic regression R/C++ package, able to account for related samples. We used code of `version 0.29.4`. 

We analyzed:

* ​1,488​​ endpoints
* 96,499 analyzed samples
* ?? variants

We included the following covariates in the model: sex, age, 10 PCs, genotyping batch. 

Github repository for pipeline: [https://github.com/FINNGEN/saige-pipelines](https://github.com/FINNGEN/saige-pipelines). 

