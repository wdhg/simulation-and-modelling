# Forced Flow Law

Take a system which contains multiple resources inside it and has \\( C \\) completions. Consider an arbitrary resource \\( k \\) inside the system, with \\( C_k \\) completions:

```

      *------------------*
      |           C_k    | C
  --->| ... -->(k)--> ...|--->
      |                  |
      *------------------*
            System

```

Note that \\( C_k \\) can be **more** than \\( C \\) if jobs go to resource \\( k \\) multiple times inside the system.

Let \\( V_k = {C_k \\over C} \\) be the average number of visits each job makes to resource \\( k \\). Rearranging and dividing by both sides by \\( T \\) gives \\( X_k = V_k X \\), where \\( X_k \\) is the throughput of resource \\( k \\).

