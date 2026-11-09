Given two $n\times n$  matrices $A$ and $B$, the goal of MATMULT is to compute the product $C=AB$, and provide an [[Interactive proof]] of that computation.

[[Fingerprinting and Freivald's algorithm|Freivald's algorithm]] requires the prover to send the computed matrices, requiring quadratic communication. For large matrices, this can mean terabytes of data.

# Protocol

We interpret $A$, $B$ and $C$ as functions $f_A$, $f_B$ and $f_C$ mapping $\{0,1\}^{\log n}\times\{0,1\}^{\log n}$ to $\mathbb F$ via

$$
f_A(i_1,...,i_{\log n},j_1,...,j_{\log n})=A_{ij}
$$

$\tilde f_A$, $\tilde f_B$ and $\tilde f_C$ are the multilinear extensions of those.

The goal is to evaluate $\tilde f_C$ at any point $(r_1,r_2)\in\mathbb F^{\log n\times\log n}$. The protocol for computing $\tilde f_C(r_1,r_2)$ exploits the representation of the polynomial $\tilde f_C(x,y)$.

We have $\tilde f_C(x,y)=\sum_{b\in\{0,1\}^{\log n}}\tilde f_A(x,b)\tilde f_B(b,y)$

For example, having $A=\begin{bmatrix}   0 & 1\\  2 & 0 \end{bmatrix}$ and $B=\begin{bmatrix}   1 & 0\\  0 & 4 \end{bmatrix}$ over $\mathbb F_5$, we can check that

$$
AB = \begin{bmatrix}   0 & 4 \\   2 & 0 \end{bmatrix}
$$

The functions are

$$
\tilde f_A(x_1,x_2)=(1-x_1)x_2+2x_1(1-x_2)=-3x_1x_2+2x_1+x_2
$$

$$
\tilde f_B(x_1,x_2)=(1-x_1)(1-x_2)+4x_1x_2=1-x_1-x_2
$$

Thus

$$
\sum_{b\in\{0,1\}}\tilde f_A(x_1,b)\tilde f_B(b,x_2)=-x_1x_2+2x_1-x_2
$$

And

$$
\tilde f_C(x_1,x_2)=4(1-x_1)x_2+2x_1(1-x_2)=-x_1x_2+2x_1-x_2
$$

# Costs

- Communication: $g$ is a log$n$-variate polynomial of degree 2 in each variable, the total communication is $O(\log n)$ over $\log n$ rounds.
- $V$'s runtime: $V$ must evaluate $g(r_3)=\tilde f_A(r_1,r_3)\tilde f_B(r_3,r_2)$, which can be done by evaluating $\tilde f_A(r_1,r_3)$ and $\tilde f_B(r_3,r_2)$. Using the matrices $A$ and $B$, this can be done in $O(n^2)$.
- $P$'s runtime: $O(n^2)$ for the proof
\tilde f_B(r_3,r_2)

# Applications

As matrix multiplication is used in many problems, the IP can be used in many settings as well.

- Counting triangles in dense graphs is done with the adjacency matrix: $\sum_{i,j\in\{1,...,n\}}(A^2)_{ij}A_{ij}$. $A^2$ is an intermediate object.
- Computing matrix powers: we can prove we computed $A^k$ by proving $A^{k/2}A^{k/2}$ 
- [[GKR]]
