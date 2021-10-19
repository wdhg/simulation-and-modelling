# Response Time Bounds

Just like with throughput, we can calculate the bounds for response time. In a system under high load, since the throughtput is bounded by `X <= 1 / D_max` we know that:

```
  R = N/X - Z
    >= N * D_max - Z
```

In a system under low load, every job experiences the average service demand at each node without needing to queue. That means that the response time is equal to the sum of the service demands `D`, thus `R >= D`.

Putting these together we get `R >= max(D, N * D_max - Z)`. When response time is plotted against number of jobs it looks like:

![A graph of response time R against number of jobs N being bounded](./images/response-time-plot.png)


