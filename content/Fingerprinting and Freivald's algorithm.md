# Rood-Solomon fingerprinting

Randomness provides power and efficiency to many proof systems.

Example: Alice and Bob live across the country from one another. They each have a large file of n characters: Alice has $(a_1,...,a_n)$ and Bob has $(b_1,...,b_n)$. They want to know whether they have the same file. They can't send the whole file, but if they're allowed to use a randomized procedure that can output a wrong answer a fraction of the time, they can prove with way less communication.

Alice picks a hash function $h$ at random from a small family of hash functions $H$. $h(x)$ is a short fingerprint of $x$ (nearly unique identifier). Bob checks that $h(a)=h(b)$.

Only a hash is transmitted, saving communication  .

# Freivald's algorithm

We have 2 $n*n$  matrices $A$ and $B$ over $\mathbb F_p$, with $p>n^2$ a prime number. The goal is to verify the product *AB* has been computed, and doing so more efficiently than the costly full matrix multiplication.

- Chose a random $r\in \mathbb F_p$, let $x=(1,r,r^2,..., r^{n-1})$
- Compute $y=Cx$ and $z=ABx$
- Output yes if $y=z$, and no otherwise

The algorithm runs in $O(n ^2)$, saving compute time.