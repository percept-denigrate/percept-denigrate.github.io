Measurement invariance is a property of factor models produced by [[Factor analysis]] being consistent across different datasets or different groups. Its goal is to test whether a construct holds validity in different groups.

There are multiple levels of measurement invariance, each one being more specific than the last:

- Configural: same items 
- Metric (weak): same loadings
- Scalar (strong): same intercepts
- Residual (strict): same residual variance

Measurement invariance is tested with MGCFA (multi-group confirmatory factor analysis), a specific type of CFA.

# Model estimation

The first step is to estimate a baseline model and models with invariance properties.

All parameters (loadings, intercepts...) are estimated via error-reducing methods:

- Maximum likelihood is most common
- Robust ML
- WLSMV for ordinal data

## Baseline model

For an individual $i$ in group $g$, the factor model is:

$$
x_{ig}=\tau_g+\Lambda_g \eta_{ig}+\epsilon_{ig}
$$

Where $x_{ig}$ is the observed variables vector, $\tau_g$ is the intercept vector, $\Lambda_g$ is the loadings matrix, $\eta_{ig}$ is the latent factor vector, and $\epsilon_{ig}$ is the residual (unique variance) vector.

The global covariance structure of observed variables is:

$$
\Sigma_g=\Lambda_g\Phi_g\Lambda_g^T+\Theta_g
$$

Where $\Sigma_g$ is the observed covariance matrix , $\Phi_g$ is the factor covariance matrix, and $\Theta_g$ is the residual covariance matrix.

All these parameters are estimated per group.

## Configural invariance

Loading patterns are the same across groups: whether or not an item has factor loading is independent of the group, with no condition on the specific values of the loadings.

## Metric invariance

Factor loadings are equal:

$$
\Lambda_1=\Lambda_2=\text{...}
$$

If it holds, we can compare regression slopes between factors and observed variables.

## Scalar invariance

Intercepts are equal:

$$
\tau_1=\tau_2=\text{...}
$$

If it holds, we can compare latent means.

## Residual invariance

Residual variances are equal:

$$
\Theta_1=\Theta_2=\text{...}
$$

It is rarely required and tested for in practice.

# Model comparison

The second step is to compare the baseline model to the more constrained invariant models, and see if the constraint induces worse model fit.

The models are sometimes first compared with [[Chi-squared]] difference test.

More common tests include approximate fit indices:

- CFI (comparative fit index): most common
- RMSEA (root mean square error of approximation)
- SRMR (standardized root mean square residual): especially for ordinal data

We typically look for the conditions:

- $\Delta CFI \leq 0.01$
- $\Delta RMSEA \leq 0.015$
- $\Delta SRMR \leq 0.01$ for metric invariance and $\Delta SRMR \leq 0.015$ for scalar invariance
