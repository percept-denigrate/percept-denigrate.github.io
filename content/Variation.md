Phenotypic variation comes from
- genetic variation
- environment
- development (fingerprints)

# Population structure

Population structure: individuals living next to each other are more similar

Environment and alleles can be correlated without causal link. For example, trees on the edge of forests have branches on their whole trunk, whereas trees inside the forest only have branches in the canopy. And trees on the edge are younger and can have accumulated some mutation. It would be easy to wrongly associate this phenotype to these mutations, but it is confounded.

This can lead to associations between alleles and environmentally driven phenotypes. For example, many genetic variants associated with height in Europe are actually confounded by population structure.[¹]

[^1]: [Nordborg & McCarth (2019), *Reduced signal for polygenic adaptation of height in UK Biobank*](https://pmc.ncbi.nlm.nih.gov/articles/PMC6428572/)

# Disentangling these effects

Assuming the influences of genes and environment are additive:
$$P_i = \overline P + G_i + E_i$$

The population mean $\overline P$ has variance:

$$\sigma_p^2 = \sigma_g^2 + \sigma_e^2$$

Evolution is fundamentally concerned with heritable variation $\sigma_g^2$, so we define [[Heritability]] as:

$$H^2 = \frac{\sigma_g^2}{\sigma_p^2} = \frac{\sigma_g^2}{\sigma_e^2 + \sigma_p^2}$$

![[selection.png]]

Selection differential: difference between the selected group and the population mean

$$S = \overline P_S - \overline P_t$$

Response to selection: difference between the mean phenotype of progeny and the previous generation

$$R = \overline {P_{t+1}} - \overline {P_t}$$

Expected response if thus:

$$R = h^2 S$$

Where $h^2 = \frac{\sigma_a^2}{\sigma_p^2}$ is narrow-sense [[Heritability]].

If $R = 1$ and $S = 2$, then $h^2 = \frac{R}S = 0.5$. Half of the variance in the trait is due to genetic effects and half to environmental effects.

# How genetic variation is partitioned across the genome

Because of recombination in diploid species, gene trees across the genome are not uniform.

Ancestral recombination graph: full relationship of all sampled individuals across the pedigree and the genome

![[arg.png]]

Each part of the genome has different trees.

Recombination splits lineages backward in time, coalescence brings the back together.

# How variation is measured

Pairwise comparisons: summing the number of differences in each pair of individuals

Nucleotide diversity:

$$\pi = \frac{\sum P_{\text{diff}}}{N_{\text{diff}} \frac{n(n-1)}2 + N_{\text{same}} \frac{n(n-1)}2}$$

For example:
 ![[variation.png]]
$$\pi = 0.0158$$
Site frequency spectrum: stable populations have high number of singletons, very low numbers of high frequency alleles .

Most new mutations are lost to drift in the first generation.

![[sfs.png]]