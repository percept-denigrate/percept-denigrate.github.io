Gene flow is the violation of the 6th assumption of HWE in [[Mendelian inheritance]]: alleles aren't added to the gene pool from other populations.

It is the movement of alleles between populations or species.

Models of gene flow may be spatial or non-spatial.

Population structure ([[Non-random mating]]) is an emergent property of limited gene flow.

# Population models

Hierarchy of terms:

- Species
- Population
- Subpopulation/deme/patch

- Migration: movement of genes between discrete demes
- Dispersal: indivual-based movements on a continuous landscape

![[gene_flow_populqtion.png]]

Migration is typically measured in rates rather than absolute numbers.

## Continent-island

Represents unidirectional flow.

![[gene_flow_continent.png]]

Change in allele frequency is the change in the resident vs migrant frequency of the island population:

$$
p_I'=p_I(1-m_{C\rightarrow I})+p_Cm_{C\rightarrow I}
$$

$$
p_I'=p_I-m_{C\rightarrow I}(p_I-p_C)
$$

$$
\Delta p_I=-m_{C\rightarrow I}(p_I-p_C)
$$

For example:

| $p_C$     | $p_I$ | m_{C\rightarrow I} |
| --------- | ----- | ------------------ |
| $0.8$<br> | $0.5$ | $0.05$             |

$$
\Delta p_I=0.015
$$

- If $p_I<p_C$, $p_I$ increases
- If $p_I>p_C$, $p_I$ decreases

Equilibrium is when $p_I=p_C$. Gene flow homogenizes allele frequencies.

The rate wat which equilibrium is approached is a function of $m$.

## Wright's island

Represents $k$ demes with rates of migration $m_{ij}$ between each other.

![[gene_flow_wright.png]]

$$
p_I'=\displaystyle\sum_{j=1}^km_{i\rightarrow j}p_j
$$

Since migrants come from any subpopulation, their allele frequencies converge towards the global average allele frequency $\bar p$.

$$
p_t=p_{t-1}(1-m)+\bar pm
$$

It is of the same form as the equation for forward and backward [[Mutation]]:

$$
p_{t+1}=p_t(1-u)+(1-p_t)v
$$

Hence, migration behaves like mutation, it maintains diversity in populations.

## Isolation by distance

Represents multiple subpopulations only connected to their immediat neighbors.

![[gene_flow_isolation.png]]

Such models generate correlations between neighbors.[^1] $F_{ST}$ between two lineages separated by $l$ demes ($d$) is:

$$
F_{ST}\approx\frac1{1+\frac{4dNm}{l(d-l)}}
$$

![[gene_flow_isolation_fst.png]]

[^1]: [Kimua & Weiss (1964), *The stepping stone model of population structure and the decrease of genetic correlation with distance*](https://academic.oup.com/genetics/article-abstract/49/4/561/6033676)
