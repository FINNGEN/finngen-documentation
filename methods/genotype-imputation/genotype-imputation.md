# Genotype imputation

Genotype imputation was done with the population-specific [SISu v3 reference panel ](sisu-reference-panel.md).

Variant call set was produced with GATK HaplotypeCaller algorithm by following GATK best-practices for variant calling.

Genotype-, sample- and variant-wise QC was applied in an iterative manner by using the Hail framework \([https://github.com/hail-is/hail](https://github.com/hail-is/hail)\) v0.1 and the resulting high-quality WGS data for 3,775 individuals were phased with Eagle 2.3.5 as described in the previous section.

Genotype imputation was carried out by using the population-specific SISu v3 imputation reference panel with Beagle 4.1 \(version 08Jun17.d8b, [https://faculty.washington.edu/browning/beagle/b4\_1.html](https://faculty.washington.edu/browning/beagle/b4_1.html)\) as described in the following protocol: dx.doi.org/10.17504/protocols.io.nmndc5e.

Post-imputation quality-control involved checking expected conformity of the imputation INFO-value distribution, MAF differences between the target dataset and the imputation reference panel and checking chromosomal continuity of the imputed genotype calls.

Optional: Post-imputation quality control also involved excluding variants imputed with imputation INFO&lt;0.7.

