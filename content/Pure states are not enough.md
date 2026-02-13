It's very hard to build hidden variable models that explain quantum mechanics.

A case where pure states and quantum mechanics produce the same results:

Classical [[Phase space]] for angular momentum: 

$$
\vec{L} = [L_x, L_y, L_z] = [L \sin \theta \cos \phi, L \sin \theta \sin \phi, L \cos \theta]
$$

Quantum state space for spin $\frac12$ (qubit): 

$$
\ket{\psi} = \cos \frac{\theta}{2} \ket{z^+} + e^{l \phi} \sin \frac{\theta}{2} \ket{z^-}
$$

Both are 2D spheres, the state space by itself is not enough to tell whether we are in a classical or quantum system.

The statistical ensembles for angular momentum is the set of probability densities: 

$$
 \rho (\theta, \phi) >= 0 
$$

$$
 \int \rho (\theta, \phi) d \theta d \phi = 1
$$

It is an infinite-dimensional convex set.

But the quantum ensembles for spin $\frac12$ (qubit) is the set of density matrices:

$$
 \rho = r \sin \theta \cos \phi \ket{x^+} \bra{x^+} + r \sin \theta \sin \phi \ket{y^+} \bra{y^+} + r \cos \theta \ket{z^+} \bra{z^+} 
$$

It is a 3D ball.

The ensembles space tell us whether we are in a classical or quantum system.
