Avellaneda-Stoikov is a widely used [[Market making]] model.[^1]

The model relies on:

- Price following a brownian motion process
- Orders following a [[Poisson distribution]]

# Reservation price

The reservation (indifference) price represents the price at which the market maker is indifferent to buying or selling the asset, considering the current inventory.

For a limited time horizon:

$$
r(t)=s(t)-q(t)\gamma\sigma^2(T-t)
$$

Where $q(t)$ is the current inventory, $\gamma$ is risk aversion, $\sigma$ is volatility, $T$ is time horizon and $t$ is current time (often both normalized, with $T=1$ and $0\leq t\leq 1$).

For an unlimited time horizon:

$$
r(t)=\frac{r_a(t)+r_b(t)}2
$$

Where $r_a(t)$ is the optimal ask price and $r_b(t)$ is the optimal bid price:

$$
r_a(t)=r(t)+\frac\delta2
$$

$$
r_b(t)=r(t)-\frac\delta2
$$

Where

$$
\delta=\frac2\gamma\log(1+\frac\gamma k)
$$

Where $k$ is the market impact parameter.

# Order execution

Orders are executed following a Poisson distribution, whose intensity depends exponentially on the distance between the quoted price and the mid price:

$$
\lambda_a=Ae^{-k(r_a(t)-s(t))}
$$

$$
\lambda_b=Ae^{-k(s(t)-r_b(t))}
$$

Where $A$ is base intensity.

The probability of an order being executed in a small interval $dt$ is:

$$
P(\text{ask executed})=1-e^{-\lambda_a dt}
$$

$$
P(\text{bid executed})=1-e^{-\lambda_b dt}
$$

[^1]: [Avellaneda & Stoikov (2006), *High-frequency trading in a limit order book*](https://people.orie.cornell.edu/sfs33/LimitOrderBook.pdf)
