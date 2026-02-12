Non-random mating  is the violation of the 1st assumption of HWE in [[Mendelian inheritance]]: alleles are drawn from the gene pool and paired randomly.

It changes the heritable characteristics of a population but in a limited way. It only causes change until an equilibrium is reached ans doesn't change allele frequencies. It is thus a weak evolutionary force.

# Inbreeding

The simplest case is selfing: some individuals self-fertilize.

It doesn't change anything for homozygotes as their offspring are homozygotes too. But when heterozygotes self, half of their offspring are homozygotes.

Often measured with the inbreeding coefficient. Given the theoritcal number of heterozygotes $H_0 = 2pq$ and the observed number of heterozygotes $H$:

$$F = \frac{H_0 - H}{H_0}$$

In the case of selfing, we lose half the heterozygotes in one generation, so:

$$F = \frac{0.47 - 0.237}{0.47} = 0.5$$ 

The reduction in heterozygosity due to inbreeding is:

$$H = 2pq - 2pqF$$

The contribution to homozygosity is:

$$f(AA) =p^2+2pqF$$

Non-random mating change genotype frequencies but not allele frequencies.

# Assortative mating

Positive assortative mating: individuals mate more with individuals with the same genotype.

Negative assortative mating: individuals mate less with individuals with the same genotype.

Positive assortative mating only resembles inbreeding with respect to the locus involved.

Negative assortative mating changes allele frequencies, until they reach a stable equilibrium.

![[negative_assortative_mating_equilibrium.png]]

# Structure

If we have two separated subpopulations each randomly mating, they can still have different allele frequencies.

![[population_structure.png]]

In reality it's hard to detect population structure. If we consider those two subpopulations as a single population, we find less heterozygotes (Wahlfund effect).

The excess homozygosity is the variance in the allele frequency:

$$\sigma^2=\frac{p_1^2+p_2^2}2-\overline p^2$$

$$\sigma^2=0.023$$

$$f(AA)_T-f(\overline A)^2=0.027$$

The loss of homozygosity is thus:

$$H_0 - H_E=-(\sigma_A^2+\sigma_a^2)$$

$$H_0 - H_E=-2\sigma^2$$

Like with inbreeding, $F_{ST}$ measures the deficiency of heterozygotes relative to expectation due to population structure:

$$F_{ST} = \frac{H_E-H_0}{H_E}$$

$$F_{ST} =0.09$$

As $H_0-H_E=-2\sigma^2$:

$$F_{ST}=\frac{\sigma^2}{\overline p\overline q}$$

It is a direct measure of the amount of evolution that has occurred between two populations.

$F_{ST}$ is a fundamental concept in population genetics, and is related to the probability of being identical by descent. It means inbreeding exists despite each subpopulation randomly mating.

# Random mating is still a decent assumption

In population genetics, you sample a small number of individuals in the population.

Thus, how long ago your sample set has a common ancestor dictates whether random mating as an assumption is justified. What matters is how related individuals are.

This is shaped by population size, dispersal potential, and range configuration.

![[random_mating.png]]

Past a certain distance, individuals are equally related (red, blue and yellow subpopulations).

![[random_mating_position.png]]