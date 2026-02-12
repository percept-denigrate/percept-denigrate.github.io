The Price equation dictates the evolution of the mean of a trait.

Given a trait $z$ in a population, the fitness $w$ and the variation between individuals and their offspring $\delta z$:

$$\Delta z = \frac{1}{w}cov(w_i,z_i) + \frac{1}{w}E(w_i \delta z_i)$$

The term $\frac{1}{w}cov(z_i,w_i)$ encompasses [[Natural selection]] and [[Genetic drift]], and the term $\frac{1}{w}E(w_i \delta z_i)$ encompasses [[Mutation]] and recombination.

The strength of this equation comes from the fact it is very general and makes very few hypothesis.

# Proof

Let's take a population that produces a new generation. Each individual $i$ has a value $z_i$ for the trait. Each parent $i$ has a number $w_i$ of children. Each child $ij$ inherits the trait $z_i$ from its parent $i$ with a small variation $\delta z_{ij}$.

![[population.png]]

Then the average trait of the new generation is:

$$z' = \frac{\displaystyle\sum_{i=1}^{N} \displaystyle\sum_{j=1}^{w_i} z_i + \delta z_{ij}}{\displaystyle\sum_{i=1}^{N} w_i}$$

$$z' = \frac{\displaystyle\sum_{i=1}^{N} w_i z_i + \displaystyle\sum_{i=1}^{N} \displaystyle\sum_{j=1}^{w_i} \delta z_{ij}}{\displaystyle\sum_{i=1}^{N} w_i}$$

$$z' = \frac{\displaystyle\sum_{i=1}^{N} w_i z_i + \displaystyle\sum_{i=1}^{N} \displaystyle\sum_{j=1}^{w_i} \delta z_{ij}}{N w}$$

$$z' = \frac{\displaystyle\sum_{i=1}^{N} w_i z_i + \displaystyle\sum_{i=1}^{N} w_i E(\delta z_{i})}{N w}$$

$$wz' = \frac{\displaystyle\sum_{i=1}^{N} w_i z_i + \displaystyle\sum_{i=1}^{N} w_i E(\delta z_{i})}{N}$$

$$wz' = E(w_i z_i) + E(w_i \delta z_{i})$$

Now by definition $\Delta z = z' - z$, so:

$$w \Delta z = E(w_i z_i) - w z + E(w_i \delta z_{i})$$

$$w \Delta z = E(w_i z_i) - E(w_i)E(z_i) + E(w_i \delta z_{i})$$

$$w \Delta z = cov(w_i,z_i) + E(w_i \delta z_{i})$$

Which gives the Price equation:

$$\Delta z = \frac{1}{w}cov(w_i,z_i) + \frac{1}{w}E(w_i \delta z_i)$$