# Poisson Processes

A _Poisson arrival processes_ is an arrival stream where the inter-arrival times `T` are both independent and _exponentially distributed_:

```
P(T <= t) = 1 - e^(-λt)
```

Here, `λ` is often called the processes' "rate" parameter and is equal to the reciprocal of the average inter-arrival time.

Since the inter-arrival times are exponentially distributed, for a fixed time window the number of arrivals is _poisson distributed_:

```
P(A_t = n) = [(λt)^n * e^(-λt)] / n!
```

where `A_t` is the number of arrivals for time interval `t`. Note the square brackets here `[]` are just used as an alternative bracket to make it easier to read, they don't have an alternative meaning.

Poisson processes are often an effective approximation for real world random arrival processes as arrivals are typically:

1. independent to each other.
2. ignorant of previous arrivals and the state of the system they are arriving at.
