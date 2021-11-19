# The Service Demand/Bottleneck Laws

Given an arbitrary node \\( k \\) inside an arbitrary system, the _Service demand_ \\( D_k = V_k S_k \\) is the product of average number of visits \\( V_k \\) and the average service time \\( S_k \\).

If we multiply the RHS of this equation by \\( X_k \\over X_k \\):

\\[
\\begin{aligned}
  D_k &= V_k S_k {X_k \\over X_k} \\\\
      &= \\left( S_k X_k \\right) \\left( {V_k \\over X_k} \\right) \\\\
      &= {U_k \\over X}
\\end{aligned}
\\]

where X is the global throughput of the system. Rearranging gives \\( U_k = D_k X \\), whichs shows that every \\( U_k \\) and \\( V_k \\) is linked by the global throughput.

