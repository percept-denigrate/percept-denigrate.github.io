The Fourier transform is a type of linear transformation that expressions functions of a variable (for example time) as functions of a conjugate variable (for example frequency or pulsation).

The Fourier transform of a square-integrable function $f$ on a domain $E$ is

$$
f^*(\omega)=\int_E e^{-i\omega t}f(t)dt
$$

# Examples

For $f(t)=e^{i\alpha t}$:

$$
f^*(\omega)=\int_E e^{-i\omega t}e^{i\alpha t}dt
$$

$$
f^*(\omega)=\int_E e^{it(\alpha-\omega)}dt
$$

$$
f^*(\omega)=\delta_{\alpha}(\omega)
$$

# Behavior under operations

| Operation                | Operation on the Fourier transform     |
| ------------------------ | -------------------------------------- |
| $\alpha f(t)+\beta g(t)$ | $\alpha f^*(\omega)+\beta g^*(\omega)$ |
| $f(\alpha t)$            | $f^*(\frac{\omega}\alpha)$             |
| $f(t+\alpha)$            | $f^*(\omega)e^{-i\omega \alpha}$       |
| $f(t)e^{it \alpha}$      | $f^*(\omega+\alpha)$                   |

# Contravariance

Because the space where $\omega$ lives is the dual of the space where $t$ lives, transformations on them are contravariant.

The more a function is concentrated on time, the more spread out it is on frequencies, and vice-versa. This means that very short sounds such as clicks have components on all frequencies.

This is also the reason we have Heisenberg's uncertainty principle. The more a wave function is concentrated on the position space, the more spread out it is on the momentum space, and vice-versa. The wave function cannot be both concentrated on position and momentum, hence $\Delta x\Delta p \geq \frac{h}2$
