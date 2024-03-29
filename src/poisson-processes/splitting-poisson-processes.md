# Splitting Poisson Processes

If we split a Poisson process with rate \\( \\lambda \\) into two streams, such that there is:

- chance \\( p \\) (\\( 0 \\le p \\le 1\\)) that the arrival will go to the first stream.
- chance \\( 1 - p \\0 that the arrival will go into the second stream.

then the resulting two processes will independent Poisson processes with rates \\( \\lambda p \\) and \\( \\lambda (1 - p) \\) respectively. From this we can say that:

\\[
P(N_1(t) = m) = {(\\lambda t p)^m * e^{-\\lambda t p} \\over m!}
\\]

and

\\[
P(N_2(t) = n) = {(\\lambda t (1 - p))^n * e^{-\\lambda t (1 - p)} \\over n!}
\\]

where:

- \\( t \\) is the time interval.
- \\( N_1(t) \\), \\( N_2(t) \\) are the number of arrivals seen at both output streams respectively during interval \\( t \\).
