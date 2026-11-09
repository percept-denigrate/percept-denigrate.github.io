Interactive proofs are based on asking the prover a question or giving it a task to do with the data.

For example: a cloud provider stores a customer's data, and the customer only stores a summary of it. The customer can ask questions about the data, the cloud provider computes the answer and sends it to the customer, who can then check it.

IPs are not transferable, the verifier can not use the prover's proof to prove the statement to a third party.

# Definition

Given a function $f$ mapping $\{0,1\}^n$ to a finite range $R$, a $k$-message interactive proof system (IP) for $f$ consistes of

- a probabilistic verifier algorithm $V$ running in polynomial time 
- a prescribed (honest) deterministic prover algorithm $P$

Both $V$ and $P$ are given a common input $x\in\{0,1\}^n$, at the start of the protocol $P$ provides a value $y$ claimed to equal $f(x)$. Then $P$ and $V$ exchanges messages $m_1,...,m_k$: the IP designates one of them to send the first message, then they send messages alternating.

Both $V$ and $P$ are thought of as next-message computing algorithms: when it's $V$'s turn to send a message $m_i$, $V$ is run on input $(x,m_1,...,m_{i-1})$ to produce $m_i$ (and conversely).

The output is 0 or 1, depending on whether the verifier accepts the proof.

# Soundness and completeness

$(V,P)$ has completeness error $\delta_C$ when for every $x$

$$
P[out(V,x,r,P)=1]\geq1-\delta_C
$$

$(V,P)$ has soundess error $\delta_S$ when for every $x$ and every deterministic prover strategy $P'$, if $P'$ sends $y\neq f(x)$ at the start, then

$$
P[out(V,x,r,P')=1]\leq\delta_S
$$

And IP is valid when both are $\leq\frac1{3}$
