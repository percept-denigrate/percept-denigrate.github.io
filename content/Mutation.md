Natural selection drift is the violation of the 4th assumption of HWE in [[Mendelian inheritance]]: alleles can't change from individual to gene pool.

It is the process that generates novelty, all evolutionary change requires this mechanism.

A mutation is the spontaneous change of an allele from a parent to its offspring.

# Population genetics approach

## Mutations as an evolutionary force

In the simplest case, forward mutations $u$ occur from $q$ to $p$ only. For $p=0.5$ and $u=0.001$:

Genotypes:

| $p²=0.25$                            | $2pq=0.5$                              | $q^2=0.25$                            |
| ------------------------------------ | -------------------------------------- | ------------------------------------- |
| $(p+u)^2=0.2505$                     | $2(p+pu)(q-qu)=0.4999$                 | $(q-qu)^2=0.2405$                     |
| $p_{\text{diff}}=0.2505-0.25=0.0005$ | $2pq_{\text{diff}}=0.4999-0.5=-0.0001$ | $q_{\text{diff}}=0.2405-0.25=-0.0005$ |

Alleles:

| $p=0.5$                             | $q= 0.5$                             |
| ----------------------------------- | ------------------------------------ |
| $p'=p+pu=0.5005$                    | $q'=q-qu=0.4995$                     |
| $p_{\text{diff}}=0.5005-0.5=0.0005$ | $q_{\text{diff}}=0.4995-0.5=-0.0005$ |

For even high mutation rates ($u=10^{-5}$), recurrent mutation is very slow. For a realistic mutation rate ($u=10^{-8}$), it would take ~69M generations for $q$ to fo from 0.5 to 0.25.

Because of that, many geneticists thought that mutation pressure alone was not an important evolutionary force.

With both forward and backward mutation $u$ and $v$:

$p_{t+1}=p_t(1-u)+(1-p_t)v$

$\Delta p=p_{t+1}-p_t=v(1-p)-up$

The stable equilibrium is:

$$
p^*_t=\frac{v}{u+v}
$$

![[mutation_delta_p.png]]

## Role in evolutionary theory

Mendelians viewed mutation as central. Darwinists viewed it as supplying the "raw material" of evolution: selection picks and chosses from these materials.

Early theoretical population genetics treated populations as having effectively infinite [[Variation]].

The common view is that mutation is random while selection is purposeful. This why highlighted by the [[Lederberg experiment]].

# Biology

## DNA replication

Most mutation happens during replication. During replication, the DNA helix is unwinded and each strand is duplicated. One is replicated continuously (the leading strand) and the other discontinuously.

DNA polymerases have an error-correcting mechanism. If they put the wrong nucleotide, they can stop and take a single step back to correct it.

![[mutation_dna.png]]

## Mutation mechanisms

Mutation =/= DNA damage! Mutations are the consequence of inexact repair of damage or inexact replication.


1. DNA polymerase III and I inexact copying and failure to identify mismatch. It can be substitution, deletion or addition. Rates are ~$10^{-8}$ in humans.
2. Error prone trans-lesion synthesis: when polymerase III falls off on a damaged site and is replaced with IV or V, which can bypass the site but is error-prone.
# Randomness

# Examples
