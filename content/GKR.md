The #SAT example is unrealistic because the problem is not **P**. GKR (Goldwasser, Kalai, and Rothblum) is a scaled-down [[Interactive proof]] for **P**, **NC** (solvable by parallel algorithms) or **L** (logarithmic space) problems.

# Costs

$V$ and $P$ agree on a log-space uniform arithmetic circuit $C$, the goal is to compute its output gate(s).

Letting $S$ be the size (number of gates) of $C$ and $n$ the number of variables, the prover runs in poly($S$) and can be linear. If $S=2^{O(n)}$, it's much better than the #SAT protocol seen in [[Sum-check protocol]]. The verifier's cost is $O(d\log S)$, growing linearly with the depth $d$ of $C$, but logarithmically with S.

# Protocol

$C$ is assumed to be in layered form, meaning the circuit can be decomposed into layers, and wires only connect gates in adjacent layers. The layers are numbered from 0 (output) to $d$ (input).

In the first message, $P$ tells $V$ the claimed output. The protocol then works iteratively towards the input layer. Each iteration$i$ reduces a claim about the values of the gates at layer $i$ to a claim about the values at layer $i+1$. The reduction is done with the [[Sum-check protocol]].

![[gkr.png]]
