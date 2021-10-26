# Splitting Poisson Processes

If we split a Poisson process with rate `λ` into two streams, such that there is:

- chance `p` (`0 <= p <= 1`) that the arrival will go to the first stream.
- chance `1 - p` that the arrival will go into the second stream.

then the resulting two processes will independent Poisson processes with rates `λp` and `λ(1 - p)` respectively. From this we can say that:

```
P(N_1(t) = m) = (λtp)^m * e^(-λtp) / m!
```

and

```
P(N_2(t) = n) = (λt(1 - p))^n * e^(-λt(1 - p)) / n!
```

where:

- `t` is the time interval.
- `N_1(t)`, `N_2(t)` are the number of arrivals seen at both output streams respectively during interval `t`.
