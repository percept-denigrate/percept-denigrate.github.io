Factor analysis is a class of algorithms aiming at discovering latent variables that explain observable variables in datasets.

It is often used in psychometrics, because many psychological constructs cannot be measured directly. There is no PCR test for autism, no radiography for anxiety. We need to characterize such traits based on how their manifestations cluster together in populations.

![[factor_analysis.png]]

The value of each item $i$ is given by the factors $F_j$, the loadings $\lambda_{ij}$ and unique variance (error + specific variance) $\epsilon_i$:

$$
Y_i=\displaystyle\sum_j\lambda_{ij}F_j + \epsilon_i
$$

Factors are assumed to have mean 0 and variance 1, which can be achieved through normalization.

# EFA

EFA (exploratory factor analysis) is the factor analysis algorithm to discover latent structure.

It is used with a chosen number of factors. Loadings are freely estimated.

# CFA

CFA (confirmatory factor analysis) to test the validity of a factor model, where factors can load onto limited item subsets