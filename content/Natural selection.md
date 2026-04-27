Natural selection drift is the violation of the 2nd assumption of HWE in [[Mendelian inheritance]]: gametes aren't preferentially chosen from the gene pool.

It is the original mechanism proposed by Darwin (1859) for [[Evolution]]:

- Individuals have far more offspring that can survive to reproduce (reproductive excess).
- There is variation between individuals and some of that variation is heritable.
- Some of that heritable variation gives an advantage to the individual, increasing the chance they reproduce over others.
- Over time, this variation spreads through the population.

But selection is different from evolution by natural selection. Selection acts on phenotypes, regardless of their genetic basis in each generation. Evolution over time depends on genetic variation.

> Natural selection is not evolution.
>
> —Ronald Fischer (1930)

# Fitness definition

Fitness has many definitions, it captures and individual's contribution to the next generation.

It can be a property of an individual, a genotype, or an allele, depending on the scope of study.

The most exact and general definition is:

$$
\text{Fitness}=\frac{\text{number of offspring}}{\text{population mean of number of offspring}}
$$

Fitness is linked to ecology and is a function of an individual's contribution to population growth.

For instance, for a diploid population:

![[selection_cycle.png]]

# Measures of fitness and population growth

Fitness can be absolute or relative.

$$
\text{Absolute fitness}=\text{expected number of offspring produced by a parent of a given genotype}
$$

$$
\text{Relative fitness}=\frac{\text{absolute fitness}}{\text{highest absolute fitness}}
$$

Absolute fitness can connect genotypes to population growth:

$$
N_{t+1}=p^2 N_t w_{11} + 2p(1-p)N_t w_{12} + (1-p)^2 N_t w_{22}
$$

We can define mean population fitness as:

$$
\overline w=p^2 w_{11} + 2p(1-p)w_{12} + (1-p)^2 w_{22}
$$

Population then grows at a rate scaled by mean population fitness:

$$
N_{t+1}=\overline w N_t
$$

# Population dynamics

Population growth rate $r$ is a central parameter in population biology, for example in the Lotka-Volterra predator-prey models.

Linking genotypic fitness to population growth rate is straightforward:

$$
N_{t+1}=N_t \overline w \approx N_t e^r
$$

Meaning that $r \approx ln(\overline w)$.

For example, if $N=1000$ and $r=0.1$, we have

$$
\overline w = \frac{1000e^{0.1}}{1000}
$$

$$
\overline w = e^{0.1}
$$

$$
\overline w = 1.1
$$

Similarly:

$$
r=ln(1.1)
$$

$$
r \approx 0.1
$$

# Change of mean fitness with allele frequencies

The rate of increase of $\overline w$ given allele frequencies can be determined by the derivative $w$ with respect to $p$:

$$
\frac{d \overline w}{dp}=\frac{d}{dp}(p^2 w_{11}+2p(1-p)w_{12}+(1-p)^2w_{22})
$$

$$
\frac{d \overline w}{dp}=2p w_{11}+2(1-2p)w_{12}-2(1-p)w_{22}
$$

$$
\frac{d \overline w}{dp}=2p w_{11}+2(1-2p)w_{12}-2(1-p)w_{22}
$$

We can now infer how the rate of mean population fitness changes as a function of allele frequencies.

The shape of this function is a feature of the degree of dominance $h$.

![[dominance.png]]

When expression is additive ($h=0.5$), the shape is linear and $\frac{d \overline w}{dp}$ is a constant. 

When expression is recessive ($h=0$), the shape is parabolic and $\frac{d \overline w}{dp}$ increases linearly as a function of $p$.

# Viability and frequency-dependent selection

This model assumes that

- Selection is acting on survivorship (viability selection).
- Genotype fitness is constant and independent of $p$ (frequency-independent selection).

Selection acts on genotype, not directly on alleles. However, assuming HWE, we can calculate the marginal fitness of each allele:

- $w_1^* = P(\text{paired with another }A_1)w_{11}+P(\text{paired with an }A_2)w_{12}$
- $w_2^* = P(\text{paired with another }A_2)w_{22}+P(\text{paired with an }A_1)w_{12}$

Assuming random mating:

- $w_1^* = pw_{11}+(1-p)w_{12}$
- $w_2^* = pw_{12}+(1-p)w_{22}$

We can then write the mean population fitness:

$$
\overline w = pw_1^* + (1-p)w_2^*
$$

Then

$$
\frac{d \overline w}{dp}=2(w_1^*-w_2^*)
$$

$w_1^*$ and $w_2^*$ are the expected number of descendants of $A_1$ and $A_2$ in the next generation .

If we take $n_1$ and the actual number of $A_1$ alleles in the next generation, then $n=n_1+n_2$. Thus $p_1=\frac{n_1}{n}$.

$$
p_{t+1}=\frac{n_1w_1^*}{n \overline w}=p_t\frac{w_1^*}{\overline w}
$$

We can thus scale fitness without effect.

The change in allele frequency in the next generation is:

$$
\Delta p=p_{t+1}-p_t
$$

$$
\Delta p=p_t\frac{w_1^*}{\overline w}-p_t\frac{\overline w}{\overline w}
$$

$$
\Delta p=p\frac{w_1^*-\overline w}{\overline w}
$$

This result is very robust, it's true whether the population is in HWE, whether selection is frequency-dependent, and is there are more than 2 alleles.

Using $\overline w = pw_1^* + (1-p)w_2^*$:

$$
\Delta p=\frac{p(w_1^*-pw_1^*-(1-p)w_2^*)}{\overline w}
$$

$$
\Delta p=p(1-p)\frac{(w_1^*-w_2^*)}{\overline w}
$$

![[dominance_frequencies.png]]

# Adaptive landscape

When fitness is independent of frequency, we use $\frac{d \overline w}{dp}=2(w_1^*-w_2^*)$ to get:

$$
\Delta p=\frac{p(1-p)}{2\overline w}\frac{d\overline w}{dp}
$$

$$
\Delta p=\frac{p(1-p)}2\frac{d\ln(\overline w)}{dp}
$$

This is Wright's adaptive landscape, it links population growth $\ln(\overline w)=r$ with the variance in phenotype frequency and the change in allele frequency due to selection.

Populations are "climbing" to local maxima of $\overline w$.

Thus, we can define adaptation as the evolution of traits that permit organisms to maximize population growth rate in a given environment.

![[fitness_landscape.png]]

Some features of the adaptive landscape are unstable, meaning the direction of $\Delta p$ depends on the starting condition of $p$.

Directional selection moves towards an equilibrium irrespective of starting condition.

Stabilizing selection favors intermediate frequencies and moves towards these irrespective of starting condition.

Disruptive selection depends entirely on the starting condition and therefore has an unstable equilibrium.

![[selection_types.png]]

# Frequency-dependent selection and extinction

Often, fitness is not independent of allele frequency. For example, in a population with a worker and a stealer strategy, the stealer strategy has greater fitness when the stealer phenotype is rarer. Relaxing this assumption leads to interesting results:

$$
\frac{d \overline w}{dp}=2p w_{11}+2(1-2p)w_{12}-2(1-p)w_{22}+p^2\frac{dw_{11}}{dp}+2(1-p)\frac{dw_{12}}{dp}+(1-p)\frac{dw_{22}}{dp}
$$

Summing these is the average of the derivative of genotypic fitness with respect to allele frequency:

$$
E(\frac{dw}{dp})=\sum p^2\frac{dw_{11}}{dp}+2(1-p)\frac{dw_{12}}{dp}+(1-p)\frac{dw_{22}}{dp}
$$

Plugging into Wright's adaptive landscape:

$$
\Delta p =\frac{p(1-p)}{2\overline w}[\frac{d\overline w}{dp}-E(\frac{dw}{dp})]
$$

It represents the additive genetic variance of fitness * the average change in genotype fitness with change in allele frequency.

![[frequency-dependent_selection.png]]

In frequency-dependent selection, adaptation can lead to extinction. This is sometimes called evolutionary suicide or darwinian extinction, and these traits are called kamikaze traits.

It is a kind of [[Fischerian runaway]] selection.

Cancer is an empirical example of natural selection leading to the death of individuals.

# Fisher's theorem

Fisher's fundamental theorem of natural selection: the change in mean population fitness is proportional to the genetic variance in fitness.

$$
\Delta w=\frac{V_A}{\overline w}+E(\delta w)
$$

$\Delta p =\frac{p(1-p)}{2\overline w}[\frac{d\overline w}{dp}-E(\frac{dw}{dp})]$ represents the change in $p$ given the variation on allele frequency and frequency-dependent selection

There is both a mean fitness effect $w$ and a variance $V_A(w)$, this is the additive genetic variance of fitness.

$\frac{p(1-p)}{2\overline w}$ represents the variance in genotype frequencies divided by mean fitness. We can rewrite $\Delta p$ with respect to the slop of the regression line of fitness against genotype:

$$
\Delta p=\frac1{\overline w}V(g)\beta_{gw}=\frac{p(1-p)}{2\overline w}\beta_{wg}
$$

![[fitness_regression.png]]

Thus

$$
V_A(w)=\overline w\Delta p\beta_{wg}=\overline w\Delta p[\frac{d\overline w}{dp}-E(\frac{dw}{dp})]
$$

If $\Delta p$ is not too large, then $\Delta p(\frac{d\overline w}{dp}) \approx \Delta \overline w$. Rewriting $\Delta pE(\frac{dw}{dp})$ as $E(\delta w)$:

$$
V_A(w)=\overline w\Delta\overline w-\overline wE(\delta w)
$$

Solving for $\Delta\overline w$, we get Fisher's theorem:

$$
\Delta w=\frac{V_A}{\overline w}+E(\delta w)
$$

The second term accounts for the fact that frequency-dependence can decrease fitness.

This equation can also be derived from the [[Price equation]], when using fitness itself as the trait.

---

From [Zach B. Hancock, *Fitness & Natural Selection | The Causes of Evolution | Ep. 3*](https://www.youtube.com/watch?v=tzI3DVI3zok)
