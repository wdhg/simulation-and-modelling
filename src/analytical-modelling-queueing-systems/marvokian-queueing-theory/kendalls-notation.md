# Kendall's Notation

**Kendall's notatation** \\( A/S/c/k/N-d \\) is used to describe a system with these parameters.

The common abbreviations for the arrival process \\( A \\) and the service time distribution \\( S \\) are:

- \\( M \\): "Memoryless"
- \\( D \\): "Deterministic" (constant)
- \\( E_j \\): Erlang-j distrRbuted (a sum of \\( j \\) exponential random variables)
- \\( G \\): General (arbitrary)
- \\( GI \\): General independent (no trends, bursts, periodicities, etc)

The common abbreviations for the discipline \\( d \\) are:

- FCFS: First-Come-First-Server (a FIFO buffer)
- LCFS: Last-Come-First-Server (a LIFO buffer)
- PS: Processor Sharing (equivilant to round robin as the time slice/quantum tends to 0, with zero context switching time)
- IS: Infinite Server (i.e. just a delay, no queue)
- SIRO: Service-in-Random-Order

For example, an \\( M/M/1 \\) queue has:

- A Poisson arrival process (inter-arrival times are exponentially distributed, and so they are _memoryless_)
- Exponentially distributed (again, _memoryless_) service times
- A single server
- First-come, first-served scheduling
