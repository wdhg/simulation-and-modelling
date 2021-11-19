# Merging Poisson Processes

When two independent Poisson processes with rates \\( λ_1 \\) and \\( λ_2 \\) are merged together, the result is also a Poisson process with rate \\( λ_1 + λ_2 \\).

### Proof

Let:

- \\( T_1 \\) and \\( T_2 \\) be the time until the next arrival for two Poisson processes.
- \\( T \\) be the time until the next arrival for the merged process.

Then we get:

\\[
\\begin{aligned}
P(T \\le t) &= P(min(T_1, T_2) \\le t) \\\\
            &= 1 - e^{-t(λ_1 + λ_2)}
\\end{aligned}
\\]

Note that this is described more in detail in the [Properties of the Exponential Distribution section](./properties-of-the-exponential-distribution.md).

This shows that the inter-arrival times of the merged process is exponential distributed, and so the merged process is Poisson.

## Generalised Merging

We can also generalise this for \\( n \\ge 2 \\) processes. Consider a binary tree of merges. Since the output of a merge is Poisson, it can be merged with another process, thus creating a chain of merges:

```
  ()()
   \/ merge
   ()()
    \/ merge
    ()()
     \/ merge
     ()
```

## Probability of Arrival Orders

The probability that the first arrival will come from the first stream is given by:

\\[
P(T_1 \\lt T_2) = {\\lambda_1 \\over \\lambda_1 + \\lambda_2}
\\]

and likewise the probability that the first arrival is from the second stream is:

\\[
P(T_2 \\lt T_1) = {\\lambda_2 \\over \\lambda_1 + \\lambda_2}
\\]

Note that this is described more in detail in the [Properties of the Exponential Distribution section](./properties-of-the-exponential-distribution.md).
