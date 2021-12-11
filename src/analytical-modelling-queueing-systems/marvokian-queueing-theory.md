# Markovian Queueing Theory

Some Markov Processes (CTMCs) have direct analytical solutions to balance equations:

\\[
\\vec{p} \\boldsymbol{Q} = \\boldsymbol{0}
\\]

and these class of models are known as **Marvokian Queues**.

A **queueing system** is a single-queue system characterised by:

- \\( A \\): The arrival process
- \\( S \\): The service time distribution
- \\( c \\): The number of servers
- \\( k \\): The capacity of the queue buffer (default is \\( \\infty \\))
- \\( N \\): The capacity of the job source (default is \\( \\infty \\))
- \\( d \\): The scheduling discipline (default FCFS)
