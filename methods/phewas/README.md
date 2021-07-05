# GWAS

We used the SAIGE software for running R5 GWAS as we did in previous releases. SAIGE is a mixed model logistic regression R/C++ package. We used code of version 0.36.3.2: [https://github.com/weizhouUMICH/SAIGE/tree/finngen\_r5\_jk    
](https://github.com/weizhouUMICH/SAIGE/tree/finngen_r5_jk) We made two modifications to SAIGE 0.36.3.2 codebase \(neither modification affects the method\):

* Null model .rda objects were trimmed to reduce RAM consumption
* Het and alt hom counts in cases and controls are included in the output

We analyzed:

* ​2,803 endpoints
* 218,792 samples
* 16,962,023 variants

We included the following covariates in the model: sex, age, 10 PCs, genotyping batch.

