# Genotype data

Chip genotype data processing and QC Samples were genotyped with Illumina \(Illumina Inc., San Diego, CA, USA\) and Affymetrix arrays \(Thermo Fisher Scientific, Santa Clara, CA, USA\).

Genotype calls were made with GenCall and zCall algorithms for Illumina and AxiomGT1 algorithm for Affymetrix data.

Chip genotyping data produced with previous chip platforms and reference genome builds were lifted over to build version 38 \(GRCh38/hg38\) following the protocol described here: [dx.doi.org/10.17504/protocols.io.nqtddwn](https://dx.doi.org/10.17504/protocols.io.nqtddwn).

## Quality control

In **sample-wise** quality control, individuals with ambiguous gender, high genotype missingness \(&gt;5%\), excess heterozygosity \(+-4SD\) and non-Finnish ancestry were excluded. In **variant-wise** quality control variants with high missingness \(&gt;2%\), low HWE P-value \(&lt;1e-6\) and minor allele count, MAC&lt;3 were excluded.

## Pre-phasing

Prior imputation, chip genotyped samples were pre-phased with [Eagle 2.3.5](https://data.broadinstitute.org/alkesgroup/Eagle/) with the default parameters, except the number of conditioning haplotypes was set to 20,000.

