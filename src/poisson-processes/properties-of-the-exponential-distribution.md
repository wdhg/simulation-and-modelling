# Properties of the Exponential Distribution

Here are three properties of the exponential distribution that will be useful to recap:

1. The exponential distribution is _memoryless_, meaning that the future is independent to the past:

```
P(X <= t + s | X > t) = 1 - P(X > t + s & X > t) / P(X > t)
                      = 1 - P(X > t + s)/P(X > t)
                      = 1 - e^(-λ(t + s)) / e^(-λt)
                      = 1 - e^(-λs) * e^(-λt) / e^(-λt)
                      = 1 - e^(-λs)
                      = P(X <= s)
```

2. If `X_1 ~ exp(λ_1)` and `X_2 ~ exp(λ_2)` then `min(X_1, X_2) ~ exp (λ_1 + λ_2)`:

```
P(min(X_1, X_2) <= t) = 1 - P(min(X_1, X_2) > t)
                      = 1 - P(X_1 > t & X_2 > t)
                      = 1 - e^(-λ_1 * t) * e^(-λ_2 * t)
                      = 1 - e^(-t(λ_1 + λ_2))
```

3. If `X_1 ~ exp(λ_1)` and `X_2 ~ exp(λ_2)` then

```
               ∞
P(X_1 < X_2) = ∫ P(X_1 < X_2 | X_1 = x) * λ_1 * e^(-λ_1 * x) dx
               0
               ∞
             = ∫ P(X_2 > x) * λ_1 * e^(-λ_1 * x) dx
               0
               ∞
             = ∫ e^(-λ_2 * x) * λ_1 * e^(-λ_1 * x) dx
               0
                   ∞
             = λ_1 ∫ e^(-x(λ_1 + λ_2)) dx
                   0
                                                        ∞
             = [-λ_1 / (λ_1 + λ_2)] * [e^(-x(λ_1 + λ_2))]
                                                        0
             = [-λ_1 / (λ_1 + λ_2)] * (0 - 1)
             = λ_1 / (λ_1 + λ_2)

P(X_2 < X_1) = λ_2 / (λ_1 + λ_2)
```
