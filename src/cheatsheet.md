# Cheatsheet

## Variables

### Scalars

- \\( A \\): Number of arrivals.
- \\( C \\): Number of completions.
- \\( T \\): Amount of time (duration).
- \\( \\lambda \\): Arrival rate.
- \\( \\lambda^{-1} \\): Average inter-arrival time.
- \\( X \\): Average throughput.
- \\( N \\): (Average) number of jobs in the system.
- \\( B \\): Average busy time for a resource.
- \\( U \\): Average utilisation for a resource.
- \\( S \\): Average service time at a resource.
- \\( \\mu \\): Average service rate.
- \\( I \\): "Request-seconds".
- \\( R \\): Average response time.
- \\( Z \\): Average think time.
- \\( V_k \\): Average number of visits at node \\( k \\).
- \\( D_k \\): Service demand.
- \\( D_{max} \\): The maximum service demand.
- \\( D \\): The sum of service demands.
- \\( \\gamma_k \\): The direct contribution to throughput for node \\( k \\) from external arrivals.
- \\( \\rho \\): The ratio \\( \\lambda / \\mu \\).

### Vectors/Matricies

- \\( \\boldsymbol{R} \\): The routing matrix of probabilities that a job goes from node \\( i \\) to node \\( j \\).
- \\( \\boldsymbol{Q} \\): The square generator matrix for a CTMC, indexed by \\( q_{i, \\, j} \\).

## Functions

- \\( f(x) \\): Distribution p.d.f.
- \\( F(x) \\): Distribution c.d.f.
- \\( h(x) \\): A function which dominates f(x).
- \\( g(x) \\): h(x) but scaled such that it's total area under the curve equals 1 (p.d.f).
- \\( G(x) \\): The c.d.f of g(x).

## Equations

\\[
\\lambda = {A \\over T}
\\]

---

\\[
\\begin{align}
X &= {C \\over T} \\\\
  &= {N \\over R + Z} \\\\
  &= {N \\over D + Z}
\\end{align}
\\]

---

\\[
\\begin{align}
U   &= {B \\over T} \\\\
    &= XS \\\\
U_k &= D_k X
\\end{align}
\\]

---

\\[
S = {B \\over C}
\\]

---

\\[
\\begin{align}
N &= XR \\\\
  &= X * (R + Z) \\\\
R &= {N \\over X} - Z \\\\
R &\\le N D_{max} - Z \\\\
\\end{align}
\\]

---

\\[
V_k = {C_k \\over C}
\\]

---

\\[
\\begin{align}
D_k &= V_k S_k \\\\
    &= {U_k \\over X}
\\end{align}
\\]

---

\\[
\\gamma_k = X a_k
\\]

---

\\[
\\begin{align}
C_k &= A a_k + C_1 r_{1, k} + C_2 + r_{2, k} + \\dots + C_n r_{n, k} \\\\
V_k &= a_k + V_1 r_{1, k} + V_2 + r_{2, k} + \\dots + V_n r_{n, k} \\\\
X_k &= \\gamma_k + X_1 r_{1, k} + X_2 + r_{2, k} + \\dots + X_n r_{n, k}
\\end{align}
\\]

---

\\[
\\begin{align}
\\vec{V} (\\boldsymbol{i} - \\boldsymbol{R}) &= \\vec{a} \\\\
\\vec{X} (\\boldsymbol{i} - \\boldsymbol{R}) &= \\vec{\\gamma} \\\\
\\vec{\\lambda} (\\boldsymbol{i} - \\boldsymbol{R}) &= \\vec{\\gamma}
\\end{align}
\\]
