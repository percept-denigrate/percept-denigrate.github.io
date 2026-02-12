Mendel's fundamental discoveries:
- Inheritance is particulate (not blending)
- Law of segregation: gametes receive only 1 randomly drawn copy from each parent
- Law of independent assortment: genes are inherited independently from one another

Violations:
- Segregation distortion: alleles are inherited at greater than 50% probability due to an epistatic interaction with the alternate allele

![[segregation_distortion.png]]

- Linkage disequilibrium: two alleles appear together more often than expected under independent assortment

![[linkage_disequilibrium.png]]

Mendelian population: population of size $N$ with $2N$ genome (when 1 locus).

![[mendelian_population.png]]

We can predict the distribution of alleles in the next generation.

One model is considering all alleles are part the gene pool, and the next generation is populated with combinations of alleles in the gene pool.

![[gene_pool.png]]

In that case:

$$f(A) = \frac8{13} = 0.62$$

$$f(a) = \frac5{13} = 0.38$$

We can predict the genotype distribution of the next generation.

HWE assumptions represent the simplest possible case:
1. Draw alleles from the gene pool and randomly pair them
2. Alleles are drawn infinitely with replacement
3. Allele frequencies are the same between sexes
4. Alleles can't change from individual to gene pool
5. Alleles aren't preferentially chosen
6. Alleles aren't added to the gene pool from other populations
7. Individuals don't keep contributing to the gene pool in the next generation

Given these assumptions:

$$f(AA) = f(A)f(A) = p^2= 0.38$$

$$f(aa) = f(a)f(a) = q^2= 0.14$$

$$f(Aa) = f(A) f(a) + f(a) f(A)=2pq= 0.47$$

This model gives the same results as calculating offspring genotype frequencies based on parents genotype.

This model shows no change in allele frequencies from generation to the next. Therefore evolution must lie within the violation of one or more of the assumptions.