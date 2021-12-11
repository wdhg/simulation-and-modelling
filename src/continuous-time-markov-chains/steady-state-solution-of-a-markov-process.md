# Steady-state Solution of a Markov Process

Let \\( p_s(t) = P(S(t) = s) \\) be the probability that at time \\( t \\) the current state of the process is \\( s \\in S \\). To find the **steady-state** (or **equilibrium**) solution, we need to derive a set of linear equations that will define the convergent solution for \\( p_s(t) \\) as \\( t \\rightarrow \\infty \\) (also known as \\( p_s \\)).

There are two approaches:

- **Numerical**: solve the system of linear equations to calculate the steady-state probabilities.
- **Analytical**: for certain systems, it is possible to spot direct solutions to the linear system, which is preferable.

Once we have the steady-state probabilities of \\( p_s, s \\in S\\), we can use it to caluclate other performance measures of the system. This can also be done numerically or analytically.

## Linear Equations

Given a **irreducible** (also known as _ergodic_) CTMC, meaning every state can reach every other state, with a finite or countably infinite number of states in \\( S \\), then at equilibrium the **probability flux** of leaving any state \\( s \\in S \\) should be equal to the **probability flux** coming into that state:

\\[
p_i \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} = \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, \\, i}
\\]

These are known as the (Global) **Balance Equations**. The left-hand side is equal to the probability of leaving the state, and the right-hand side is equal to the probability of entering the state. The derivation can be found here [here](/continuous-time-markov-chains/steady-state-solution-of-a-markov-process/derivation-of-balance-equations.html).

At equilibrium, a _finite_ CTMC with a finite generator matrix will statisfy the following equation:

\\[
\\vec{p} \\, \\boldsymbol{Q} = \\boldsymbol{0}
\\]

where \\( \\vec{p} = \\begin{bmatrix} p_1 & p_2 & \\dots & p_n \\end{bmatrix} \\).

### Theorem

If a CTMC is finite and irreducible, then there exists a limiting distribution:

\\[
\\vec{p} = \\lim_{t \\rightarrow \\infty} \\vec{p}(t)
\\]

## Solving Balance Equations

Since an irreducible CTMC will have a singular generator matrix (every row sums to \\( 0 \\)), no inverse matrix will exist. This means that there isn't a unique solution. However, by encoding the normalising condition:

\\[
\\sum_{s \\in S} p_s = 1
\\]

into \\( \\boldsymbol{Q} \\), then it will become non-singular, so a unique solution for \\( \\vec{p} \\) can be found.

To do this, pick a random column \\( c, \\, 1 \\le c \\le n \\) and set all of its values to \\( 1 \\):

\\[
\\begin{bmatrix}
q_{1,1} & q_{1,2} & \\dots & q_{1,c-1} & 1 & q_{1, c+1} & \\dots & q_{1, n} \\\\
q_{2,1} & q_{2,2} & \\dots & q_{2,c-1} & 1 & q_{2, c+1} & \\dots & q_{2, n} \\\\
\\dots \\\\
q_{n,1} & q_{n,2} & \\dots & q_{n,c-1} & 1 & q_{n, c+1} & \\dots & q_{n, n}
\\end{bmatrix} = \\begin{bmatrix}
0 & 0 & \\dots & 0 & 1 & 0 & \\dots & 0
\\end{bmatrix}
\\
\\]

where the output vector is a vector with \\( n - 1 \\) zeros and a single \\( 1 \\) in column \\( c \\).

### Theorem

An irreducible CTMC with \\( n \\) states will have a generator matrix with rank \\( n-1 \\).

### Corollary

Given an irreducible CTMC with \\( n \\) states, the normalised generator matrix with one column set all to \\( 1 \\) will be rank \\( n \\) and as a result it will be non-singular and invertible.
