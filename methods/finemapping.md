# Fine-mapping

To identify potential causal variants in GWAS signals, we fine-mapped each genome-wide significant \(p &lt; 5e-8\) region from the 2,444 GWAS endpoints. Each region was fine-mapped with [SuSiE](https://github.com/stephenslab/susieR) and [FINEMAP](http://www.christianbenner.com/). We used in-sample LD for fine-mapping.

We used a 3-megabase window \(+- 1.5M\) around each lead variant, merged overlapping regions into one, and used these regions for fine-mapping.

