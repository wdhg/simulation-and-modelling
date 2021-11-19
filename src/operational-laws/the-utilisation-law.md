# The Utilisation Law

\\[
\\begin{align}
  U &= {B \\over T} \\\\
    &= {B \\over T} * {C \\over C} \\\\
    &= {B \\over C} * {C \\over T} \\\\
    &= XS
\\end{align}
\\]

Since service rates are used a lot, this also comes out to \\( U = {X \\over \\mu} \\). Note that because \\( B \\le T \\) and \\( U = {B \\over T} \\) then \\( U \\le 1 \\), so using \\( U = {X \\over \\mu} \\) we know that \\( {X \\over \\mu} \\le 1 \\) so \\(X \\le \\mu \\). What this means is that the throughput must always be less than or equal to the service rate for the system to be stable.

Note that in the situation where the arrival rate equals the service rate (\\( \\lambda = \\mu \\)) this might seem like it would be a stable system but in general (and depending on the distributions of the inter-arrival times and service times) it is actually unstable (more on this later).

