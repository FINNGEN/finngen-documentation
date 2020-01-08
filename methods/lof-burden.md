# Loss of function burden

We estimated the loss of function \(LoF\) burden of each gene on every endpoint. 

First, we calculated per individual and gene whether any loss of function variant\(s\) was present, yielding a $$n \times p$$ matrix with 0 and 1 values \( $$n$$being the number of individuals and $$p $$ the number of genes\). 

Then we used the new summarised variables as input in the SAIGE GWAS, replacing the genotype matrix that was used in the regular GWAS. 

