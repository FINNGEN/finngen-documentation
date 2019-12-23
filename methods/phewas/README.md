# GWAS

We used the [SAIGE](https://github.com/weizhouUMICH/SAIGE/) software for running the R2 GWAS. 

[SAIGE](https://github.com/weizhouUMICH/SAIGE/) is a mixed model logistic regression R/C++ package. We used code of `version 0.29.4`. 

We analysed:

* ​1,488​​ endpoints
* 100,355 analyzed samples \(102,739 before QC\)
* ?? variants

We included the following covariates in the model: sex, age, 10 PCs, genotyping batch. 

Github repository for pipeline: [https://github.com/FINNGEN/saige-pipelines](https://github.com/FINNGEN/saige-pipelines). 

