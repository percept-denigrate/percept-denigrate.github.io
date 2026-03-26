GWAS (genome-wide association studies) are observational studies designed to locate genetic loci responsible for phenotypical characteristics.

They identify correlations between a trait and SNPs (single-nucleotide polymorphisms), variation of a single base pair on a given locus. Identified SNPs are called GWAS hits.

We can use these GWAS hits to calculate PGS (polygenic scores) that estimate variation in traits.

# Problems with simple GWAS

However simple GWAS establishing correlations between SNPs and phenotype can capture non-causal correlations due to stratification. If we were to do a GWAS on the whole human population, we would be able to identify "chopstick genes" (SNPs correlated with chopstick usage which is a purely cultural phenomenon), just because they have higher frequency in asian populations. Studies have established that many simple GWAS hits are due to stratification.

The SNP heritability of many psychological and social traits, such as educational attainment and psychiatric troubles, has been overestimated[^1]:

![[gwas_confounded.webp]]

This is particularly true for ADHD, whose family GWAS heritability estimation is significantly lower than [[Twin studies]] estimations.

# Family GWAS

This issue is mitigated by within-family GWAS, that only look at the random segregation of SNPs within families (by looking at the deviation from parents or siblings mean). This effectively controls for stratification.

But they do not fully mitigate [[Non-random mating]].

[[Linkage disequilibrium]] can also produce non-causal GWAS hits, when causal and non-causal SNPs are correlated.

[^1]: [Tan et al. (2024), *Family-GWAS reveals effects of environment and mating on genetic associations*](https://www.medrxiv.org/content/10.1101/2024.10.01.24314703v1)