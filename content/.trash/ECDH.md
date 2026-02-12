The goal of this algorithm is to obtain a shared secret that is never sent directly. 

- Alice and Bob both know a prime number $p$ and a base $g$.
- Alice chooses a number $a$ and Bob chooses a number $b$.
- Alice sends $aG \mod p$ to Bob, and Bob send $bG \mod p$ to Alice.
- Alice computes $abG \mod p = a(bG) \mod p$  and Bob computes $abG \mod p = b(aG) \mod p$. This is the shared secret they can derive a symmetric key from.

The algorithm doesn't ensure authentication, it is possible to do [[MitM]].