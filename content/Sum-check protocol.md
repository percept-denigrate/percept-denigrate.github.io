The sum-check protocol is an [[Interactive proof]] to prove a polynomial has been computed.

Suppose we have a $v$-variate polynomial $g$ defined over a finite field $\mathbb F$. The purpose of the sum-check protocol is for the prover to provide the verifier with the sum

$$
H := \sum_{b_1\in\{0,1\}} \sum_{b_2\in\{0,1\}} ... \sum_{b_v\in\{0,1\}} g(b_1,...,b_v)
$$

The verifier could compute $H$ with this formula by evaluating $g$ on $2^v$ inputs, but that has exponential complexity. Using the sum-check protocol, the verifier's runtime will be

$$
O(v + \text{cost of evaluating g at a single input in }\mathbb F^v)
$$

# Mechanism

- At the start, the prover sends a value $C_1$ claimed to equal $H$
- In the first round, $P$ sends the univariate polynomial $g_1(X_1)$ claimed to equal

$$
\sum_{(x_2,...,x_v)\in\{0,1\}^{v-1}} g(X_1,x_2,...,x_v)
$$

And $V$ checks that $C_1=g_1(0)+g_1(1)$ and that $g_1$ is a univariate polynomial of degree at most $\text{deg}_1(g)$

- $V$ sends a random $r_1\in\mathbb F$
- In the $j$th round, for $1<j<v$, $P$ sends $V$ a univariate polynomial $g_j(X_j)$ claimed to equal

$$
\sum_{(x_{j+1},...,x_v)\in\{0,1\}^{v-1}} g(r_1,...,r_{j-1},X_j,x_{j+1},...,x_v)
$$

And $V$ checks that $g_{j-1}(r_{j-1})=g_j(0)+g_j(1)$ and that $g_j$ is a univariate polynomial of degree at most $\text{deg}_j(g)$

- $V$ sends a random $r_j\in\mathbb F$
- Round $v$: 

# Application: SAT

A boolean formula over variables $x_1,...,x_n$ is a binary tree with each leaf labeled by a variable $x_i$ or its negation, and each non-leaf node computing the AND or OR of its two children. The size $S$ of the formula is the number of leaves (can be larger than $n$).

Let $\Phi$ be a boolean formula on $n$ variables of size $S$. In the the #SAT problem, the goal is to compute the number of satisfying assignments of $\Phi$, or equivalently

$$
\sum_{x\in\{0,1\}^n} \Phi(x)
$$

It is a very difficult problem, with exponential complexity. But the proof has polynomial complexity.

The previous equation is similar to the $H$ of the sum-check protocol. We need a polynomial extension $g$ of $\Phi$ of total degree poly($S$) over a field. The fact that $g$ extends $\Phi$ will ensure the equality between the sums. And we need the verifier to be able to evaluate $g$ at a random point $r$ in polynomial time.

Let $\mathbb F$ be a finite field of size at least $S^4$. The soundness error will be at most $\frac S {|\mathbb F|}\approx\frac1{S^3}$.

We can turn $\Phi$ into an arithmetic circuit $\Psi$  over $\mathbb F$ that computes $g$, by turning AND($y$,$z$) into $yz$ and OR($y$,$z$) into $y+z-yz$. $g$ will have degree at most $S$.

# Application: matrix multiplication

Given two $n\times n$  matrices $A$ and $B$, the goal of MATMULT is to compute the product $C=AB$.

[[Fingerprinting and Freivald's algorithm|Freivald's algorithm]] requires the prover to send the computed matrices, requiring quadratic communication. For large matrices, this can mean terabytes of data.

## Protocol

We interpret $A$, $B$ and $C$ as functions $f_A$, $f_B$ and $f_C$ mapping $\{0,1\}^{\log n}\times\{0,1\}^{\log n}$ to $\mathbb F$ via

$$
f_A(i_1,...,i_{\log n},j_1,...,j_{\log n})=A_{ij}
$$
$\tilde f_A$, $\tilde f_B$ and $\tilde f_C$ are the multilinear extensions of those.

The goal is to evaluate $\tilde f_C$ at any point $(r_1,r_2)\in\mathbb F^{\log n\times\log n}$. The protocol for computing $\tilde f_C(r_1,r_2)$ exploits the representation of the polynomial $\tilde f_C(x,y)$.

We have $\tilde f_C(x,y)=\sum_{b\in\{0,1\}^{\log n}}\tilde f_A(x,b)\tilde f_B(b,y)$

