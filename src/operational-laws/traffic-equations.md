# Traffic Equations

Consider an arbitrary system with `n` nodes, where each node `k` in `1 <= k <= n` has `C_k` completions. When the system is at equilibrium, the number of arrivals is equal to the system to the number of completions `A = C`, and each job arrives exactly once to the system.

Now consider two arbitrary and distinct nodes `i` and `j` where `1 <= i, j <= n`. Assume that a job that comletes at `i` has a fixed probability `r_ij` of moving to node `j`. Then for any node `k`, the number of completions `C_k` must equal the sum of:

1. the number of arrivals to the system `A` multiplied by the probability that an arriving job will move to node `k` directly, denoted as `a_k`.
2. the sum of the products of every node's number of completions and probability that a job will move to `k` (note this includes the cyclic arc from `k` to `k`).

```
C_k = A * a_k
      + C_1 * r_1k
      + C_2 * r_2k
      + ...
      + C_n * r_nk
```

If both sides are divided by the total number of completions in the system `C` we get an equation for the number of visits `V_k = C_k / C`:

```
V_k = a_k
      + V_1 * r_1k
      + V_2 * r_2k
      + ...
      + V_n * r_nk
```

Note that `A = C` hence why it disappears from `A * a_k`.

If we divide by the total time `T` instead, we get an equation for the node throughput `X_k`:

```
X_k = γ_k
      + X_1 * r_1k
      + X_2 * r_2k
      + ...
      + X_n * r_nk
```

where `γ_k = X * a_k` is the direct contribution to throughput from external arrivals.

We can now take these equations and turn them into vector equations:

```
V * (I - R) = a
X * (I - R) = γ
```

where:

- `V` is the vector of number of visits for each node.
- `I` is the identity matrix.
- `R` is the maxtrix of probabilities that a job goes from node `i` to node `j`.
- `γ` is the vector of direct contributions to throughput from external arrivals for each node.

Note that often we use arrival rate of node `i` (denoted as `λ_i`) instead of throughput. Since arrival rate is the same as throughput, we can write:

```
λ * (I - R) = γ
```
