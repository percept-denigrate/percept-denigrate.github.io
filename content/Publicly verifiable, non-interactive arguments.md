# Random oracle model

The random oracle model captures the fact that hash functions are computationally indistinguishable from random functions. By a random function $R$ mapping some domain $D$ to $\{0,1\}^k$, we mean that for any $x\in D$, $R$ chooses its output $R(x)$ uniformly at random from $\{0,1\}^k$.

The ROM simply assumes the prover and verifier have query access to a random function $R$. In practice it's a robust hash function.

# Fiat-Shamir transformation 

The Fiat-Shamir transformation takes any random-based interactive protocol and transforms it into a non-interactive publicly verifiable protocol.

It replaces each of the verifier's messages from the interactive protocol with a value derived from the oracle.

It is often implemented with hash chaining: rather than choosing the round-$i$ verifier challenge $r_i$ to be the hash of all previous messages $g_1,...,g_i$, $r_i$ is simply the hash of $(x,i,r_{i-1},g_i)$.

If an adversary can choose the input $x$, at is important to append it to the data hashed in each round. This property of soundness against provers that can choose $x$ is called adaptive soundness. Otherwise the prover can skip the rounds and choose $x$ *ad-hoc* to build a coherent transcript.

# Security

When the Fiat-Shamir transformation is applied to a sufficiently sound *constant-round* IP, the non-interactive proof is sound against cheating provers running in polynomial time.