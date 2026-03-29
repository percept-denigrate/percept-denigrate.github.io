The Legendre transform is a transformation of convex functions.

The Legendre transform of a function $f(x)$ expresses the same function, but as a function of its derivative $p=\frac{df}{dx}$. 

![[legendre.png]]

Formally: let $f$ a convex function defined on an interval $I$. Then the Legendre transform of $f$ is

$$
f^*(p) = \displaystyle\sup_{x \in I}(px-f(x)), x \in I^*
$$

Where $I^*$ is the interval where $\displaystyle\sup_{x \in I}(px-f(x)) < \infty$. 

The Legendre transform is involutive on convex functions: for any convex function $f$, $f^{**} = f$. If $f$ is not convex, then $f^{**}$ is the [[Convex hull]] of $f$.

# Examples

For $f(x)=e^x$:

$$
f^*(p) = \displaystyle\sup_{x \in I}(px-e^x), x \in I^*
$$

We need to find the value of $x$ where $px-f(x)$ is maximized. As $f$ is differentiable, we calculate

$$
\frac{d}{dx}(px-e^x)=p-e^x
$$

This value is $0$ when $p=e^x$, or $x=\ln(p)$. Therefore 

$$
f^*(p)=p\ln(p)-e^{\ln(p)}
$$

$$
f^*(p)=p(\ln(p)-1)
$$

On domain $I^*=[0,\infty]$, corresponding to all possible values of $f'$.

For $f(x)=x^2$:

$$
f^*(p) = \displaystyle\sup_{x \in I}(px-x^2), x \in I^*
$$

$px-x^2$ is maximized when:

$$
\frac{d}{dx}(px-x^2)=0
$$

$$
p-2x=0
$$

$$
x=\frac{p}2
$$

Therefore

$$
f^*(p)=p\frac{p}2-(\frac{p}2)^2
$$

$$
f^*(p)=\frac{p^2}2-\frac{p^2}4
$$

$$
f^*(p)=\frac{p^2}4
$$

On domain $I^* = \mathbb R$.

# Behavior under operations

| Operation     | Operation on the Legendre transform |
| ------------- | ----------------------------------- |
| $\alpha f(x)$ | $\alpha f^*(\frac{p}\alpha)$        |
| $f(\alpha x)$ | $f^*(\frac{p}\alpha)$               |
| $f(x)+\alpha$ | $f^*(p)-\alpha$                     |
| $f(x+\alpha)$ | $f^*(p)-\alpha p$                   |

Just like a point in the domain is represented by a complex exponential in the conjugate domain by the [[Fourier transform]], each point of the domain is represented by a line in the conjugate domain by the Legendre transform.

# Uses in physics

The Legendre transform is used in optimization to solve a problem's dual problem. Instead of solving

$$
\displaystyle\min_x f(x)
$$

We write

$$
f(x)=\displaystyle\sup_p(px-f^*(p))
$$

The problem then becomes

$$
\displaystyle\min_x\sup_p(px-f^*(p))
$$

If $f$ is convex, we can swap $\text{min}$ and $\text{sup}$:

$$
\displaystyle\sup_p\min_x(px-f^*(p))
$$

Which becomes

$$
\displaystyle\max_p-f^*(p)
$$

Or

$$
\displaystyle\min_pf^*(p)
$$

It is used to convert functions of one quantity (like position) as a function of its conjugate quantity (like momentum). The [[Laplacian]] and the [[Hamiltonian]] are the Legendre transform of one another.
