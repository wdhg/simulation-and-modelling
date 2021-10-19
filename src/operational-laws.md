# Operational Laws

 Given an arbitrary system (real, simulated, etc), if measurements can be made upon it then the 'operational laws' link these quantities together.

For example, take an "open" system (more on this later) which has arrivals entering it and completions exiting it:

```

  Arrivals        Completions
  ------->(System)---------->

```

For an amount of time `T`, let:

- `A` represent the number of a arrivals
- `C` represent the number of completions

From this, we can begin to determine three relationships:

1. The _arrival rate_ is `λ = A/T` (arrivals per unit time)
2. The _average inter-arrival time_ is `λ^-1 = T/A` (average amount of time between arrivals)
3. The _throughput (traffic rate)_ is `X = C/T` (completions per unit time)

(Note that throughput can be meassured on any arc).
