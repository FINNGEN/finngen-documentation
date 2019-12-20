# Genotypes

FinnGen individuals were [genotyped](./) with Illumina and Affymetrix arrays \(Illumina Inc., San Diego, and Thermo Fisher Scientific, Santa Clara, CA, USA\). Genotypes were imputed using the population-specific [SISu v3 imputation reference panel](./) of 3,775 whole genomes with Beagle 4. Merged imputed genotype data is composed of 31 data sets \(Supplementary table 1\) from FINRISK, Botnia, H2000/H2011, GeneRisk and Psychiatric Family Collections, Auria, Borealis, DIME, FT17, HBP, Iddmgen, VPU, YA cohorts. Post-imputation QC involved excluding variants with imputation INFO &lt;0.7.

* Total number of individuals: 102,739
* Total number of variants \(merged set\): 17,054,975
* Reference assembly:         GRCh38/hg38

Programs used:

* Cromwell-29 and 31
* Wdltool-0.14
* Plink 1.9 and 2.0 
* BCFtools 1.5 and 1.7
* Eagle 2.3.5
* Beagle 4.1
* R 3.4.1, packages: data.table 1.10.4, sm 2.2-5.4 

