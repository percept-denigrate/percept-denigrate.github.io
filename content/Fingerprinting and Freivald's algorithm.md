# Rood-Solomon fingerprinting

Randomness provides power and efficiency to many proof systems.

Example: Alice and Bob live across the country from one another. They each have a large file of n characters: Alice has $(a_1,...,a_n)$ and Bob has $(b_1,...,b_n)$. They want to know whether they have the same file. They can't send the whole file, but if they're allowed to use a randomized procedure that can output a wrong answer a fraction of the time, they can prove with way less communication.

Alice picks a hash function $h$ at random from a small family of hash functions $H$. $h(x)$ is a short fingerprint of $x$ (nearly unique identifier). Bob checks that $h(a)=h(b)$.

Only a hash is transmitted, saving communication  .

# Freivald's algorithm

We have 2 $n*n$  matrices $A$ and $B$ over $\mathbb F_p$, with $p>n^2$ a prime number. The goal is to verify the product *AB* has been computed, and doing so more efficiently than the costly full matrix multiplication.

- Chose a random $r\in \mathbb F_p$, let $x=(1,r,r^2,..., r^{n-1})$
- Compute $y=Cx$ and $z=A(Bx)$
- Output yes if $y=z$, and no otherwise

The algorithm runs in $O(n ^2)$, saving compute time.

# Lagrange interpolation

The Reed-Solomon encoding of a vector $a$ interprets it as the *coefficients* of a univariate polynomial $p_a$ of degree $n-1$.

But it is also possible to view $a_1,...,a_n$ as the *evaluations* of $p_a$ over some given numbers. Defining $p_a$ this way the the Lagrange interpolation for univariate polynomials.

For any vector $a=(a_1,...,a_n)\in \mathbb F^n$, there is a unique polynomial $p_a$ of degree at most $n-1$ such that

$$
\forall 0\leq i\leq n-1, p_a(i)=a_{i+1}
$$

For each $i$ we define the Lagrange basis polynomial 

$$
\delta_i(X) = \prod_{0\leq k \leq n-1, k\neq i} (X-k)(i-k)
$$

$\delta_i$ has degree at most $n-1$, since the product has $n-1$ terms. It also maps $i$ to 1 and all other points in $[0,n-1]$ to 0. It acts as an indicator function for $i$

Then we express $p_a$ in terms of the Lagrange basis polynomials:

$$
p_a(x)=\sum_{j=0}^{n-1}a_{j+1}\delta_j(X)
$$

Verifying the values of $p_a$ can be done in $O(n)$.
