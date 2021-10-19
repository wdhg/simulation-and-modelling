# The Utilisation Law

```
  U = B/T
    = B/T * C/C
    = B/C * C/T
    = X * S
```

Since service rates are used a lot, this also comes out to `U = X/µ`. Note that because `B <= T` and `U = B/T` then `U <= 1`, so using `U = X/µ` we know that `X/µ <= 1` so `X <= µ`. What this means is that the throughput must always be less than or equal to the service rate for the system to be stable.

Note that in the situation where the arrival rate equals the service rate (`λ = µ`) this might seem like it would be a stable system but in general (and depending on the distributions of the inter-arrival times and service times) it is actually unstable (more on this later).

