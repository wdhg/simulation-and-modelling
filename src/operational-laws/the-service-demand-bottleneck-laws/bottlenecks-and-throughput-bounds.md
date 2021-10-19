# Bottlenecks and Throughtput Bounds

Since `U_k = D_k * X` and `U_k <= 1`, then we know `X <= 1 / D_k` for every node `k` in the system. From this we get that `X <= 1 / D_max` where `D_max` is the maximum of `D_k`.

In a system under heavy load we can say that `U_max ≈ 1` and `X ≈ 1 / D_max`. What this means is that `1 / D_max` is the **upper asymptotic bound on throughput under heavy load**, and the resource with the highest demand `D_max` is the **bottleneck** resource of the system. Note that if the system is open, then `λ = X` so we also require that `λ <= 1 / D_max` for the system to be stable.

In a system under light load jobs are never queued and so the average total time they spend at each resource `k` is just `D_k` (remember `D_k` is the product of the average number of visits per job and the average service time at that resource), so we can say that for the entire system the response time `R` is the sum of all service demands:`R = D_1 + D_2 + ... + D_k`. In a closed system, we can apply this to the response time law:

```
  X = N / (R + Z)
    = N / (D + Z)
```

where `D = D_1 + D_2 + ... + D_k`. This means that `N / (D + Z)` is the **upper asymptotic bound on throughput under light load**.

Combining these two limits, we can say that in general: `X <= min(1 / D_max, N / (D + Z))`. Note that in an open system we say that `Z = 0` but we also recognise that `N` is not fixed. The bound still applies, however it is not as tight as in a closed system.

When throughput is plotted against the number of jobs, it typically looks like this:

![A graph of throughput X against number of jobs N being bounded](./images/throughput-plot.png)

