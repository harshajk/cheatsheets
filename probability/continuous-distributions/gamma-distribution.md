# Gamma distribution

The integral

```math
\Gamma(\alpha) = \int_{0+}^{\infty} x^{\alpha - 1} e^{-x} dx  \tag{1}
```

converges or diverges according as $\alpha > 0$  or $\le 0$. For $\alpha > 0$ the integral above is called the *gamma function*. In particular, if $\alpha = 1, \Gamma(1) = 1$

```math
f(y) = \begin{cases}
    \frac{1}{\Gamma(\alpha)\beta^\alpha}\small{y}^{\alpha-1}e^{-y/\beta} & 0 < y < \infty, \\
    0 & y \leq 0.

\end{cases}
\tag{2}
```

defines a PDF for $\alpha > 0,\ \beta > 0.$

A RV $X$ with PDF defined by euqation (2) is said to have a gamma distribution with parameters $\alpha$ and $\beta$. We done this as $X \sim G(\alpha, \beta)$

![Gamma](/probability/continuous-distributions/gamma-distribution-ex-1.png)

