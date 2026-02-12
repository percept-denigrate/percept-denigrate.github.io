The goal of this algorithm is to obtain a shared secret that is never sent directly. 

- Alice and Bob both know a prime number $p$ and a base $g$.
- Alice chooses a number $a$ and Bob chooses a number $b$.
- Alice sends $g^a \mod p$ to Bob, and Bob send $g^b \mod p$ to Alice.
- Alice computes $g^{ab} \mod p = (g^b)^a \mod p$  and Bob computes $g^{ab} \mod p = (g^a)^b \mod p$. This is the shared secret they can derive a symmetric key from.

An eavesdropper sees $p$, $g$, $g^a \mod p$, and $g^b \mod p$. But computing $g^{ab} \mod p$ requires solving the discrete logarithm problem, which is computationally infeasible for properly chosen parameters.

The algorithm doesn't ensure authentication, it is possible to do [[MitM]] if no authentication mechanism is put in place. [[TLS]] does so.

[[ECDH]] is the analogous algorithm over elliptic curves.