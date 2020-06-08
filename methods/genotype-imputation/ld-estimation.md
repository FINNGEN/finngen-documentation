# LD estimation

The [BCOR](http://www.christianbenner.com/) files were created using [LDstore](http://www.christianbenner.com/) from the Finnish [SISU](sisu-reference-panel.md) panel v3. 

The panel has been divided per chromosome. For example, to use the LD information in the first chromosome, `FG_LD_chr1.bcor` would be the file to use.

### **Settings used** 

* number of samples: 3775 
* window size: 1500 kb 
* accuracy: low 
* number of threads: 96 
* LD threshold to include correlations: 0.05

### Example usage

[LDstore v1.1](http://www.christianbenner.com/ldstore_v1.1_x86_64.tgz) can be downloaded via: 

```bash
wget http://www.christianbenner.com/ldstore_v1.1_x86_64.tgz
```

And an example to extract variant range 20 Mb - 50 Mb from chromosome 7 is as follows:

```bash
ldstore --bcor FG_LD_chr7.bcor --incl-range 20000000-50000000 --table output_file_name.table
```



