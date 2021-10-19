# The Service Demand/Bottleneck Laws

Given an arbitrary node `k` inside an arbitrary system, the _Service demand_ `D_k = V_k * S_k` is the product of average number of visits `V_k` and the average service time `S_k`.

If we multiply the RHS of this equation by `X_k / X_k`:

```
  D_k = V_k * S_k * X_k / X_k
      = (S_k * X_k) * (V_k / X_k)
      = U_k / X
```

where X is the global throughput of the system. Rearranging gives `U_k = D_k * X`, whichs shows that every `U_k` and `V_k` is linked by the global throughput.

