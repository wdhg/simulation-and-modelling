# Derivation of Balance Equations

Assume the CTMC has a finite or countably infinite number of states in \\( S \\). Given some rate parameter \\( r \\), the probability that a specific number of events \\( N \\) occur in some time interval \\( \\Delta \\) is given by:

\\[
P(N = n) = {({r \\Delta t})^n e^{-r \\Delta t} \\over n!}
\\]

as \\( \\Delta t \\) is Poisson distributed. Also remember that the expansion of \\( e^x \\) is:

\\[
e^x = 1 + x + {x^2 \\over 2!} + {x^3 \\over 3!} + \\dots
\\]

Then the probability that there are no events be rewritten as:

\\[
\\begin{align}
P(N = 0) &= {({r \\Delta t})^0 e^{-r \\Delta t} \\over 0!} \\\\
         &= e^{-r \\Delta t} \\\\
         &= 1 - r \\Delta t + {(r \\Delta t)^2 \\over 2!} - {(r \\Delta t)^3 \\over 3!} + \\dots \\\\
         &= 1 - r \\Delta t + o(\\Delta t)
\\end{align}
\\]

where \\( o(\\Delta t) \\) represents a summation of higher orders of \\( \\Delta t \\) such that:

\\[
\\lim_{\\Delta t \\rightarrow 0} {o(\\Delta t) \\over \\Delta t} = 0
\\]

Similarly, the probability that there is exactly one event that occurs is:

\\[
\\begin{align}
P(N = 1) &= (r \\Delta t) e^{-r \\Delta t} \\\\
         &= r \\Delta t + o(\\Delta t)
\\end{align}
\\]

and the probability that more than one event occurs is:

\\[
P(N \\gt 1) = o(\\Delta t)
\\]

Applying this to the CTMC transition rates, if \\( X_{i, \\, j} \\sim exp(q_{i, \\, j}), i \\ne j \\), the probability of there being no state transitions out of state \\( i \\) in a time period \\( \\Delta t \\) is equal to:

\\[
\\prod_{j \\in S, \\, j \\ne i} \\left( 1 - q_{i, \\, j} \\Delta t + o(\\Delta t) \\right) = 1 - \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} \\Delta t + o(\\Delta t)
\\]

and therefore the probability of there being exactly one transition is \\( q_{i, \\, j} \\Delta t + o(\\Delta t) \\) and the probability of there being more than one transition is \\( o(\\Delta t) \\).

Combining these equations together, the probability of being in state \\( i \\) at time \\( t + \\Delta t \\) is given by the sum of:

- The probability of being in state \\( i \\) and no transitions occuring.
- The sum of the probabilities of being in state \\( j \\) where \\( i \\ne j \\) and there being one transition from state \\( j \\) to state \\( i \\).
- The sum of the probabilities of being in some arbitrary state and there being \\( 2 \\) or more transitions that end up in state \\( i \\).

Therefore:

\\[
\\begin{align}
p_i(t + \\Delta t) &= p_i(t) \\left( 1 - \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} \\Delta t \\right) \\\\
                   & \\quad + \\sum_{j \\in S, \\, j \\ne i} p_j(t) q_{j, i} \\Delta t \\\\
                   & \\quad + o(\\Delta t)
\\end{align}
\\]

This can then be rearranged to get:

\\[
{p_i(t + \\Delta t) - p_i(t) \\over \\Delta t} = -p_i(t) \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} + \\sum_{j \\in S, \\, j \\ne i} p_j(t) q_{j, i} + {o(\\Delta t) \\over \\Delta t}
\\]

Recall that this is the equation for differentiation from first principals. Thus, in the limit \\( \\Delta t \\rightarrow 0 \\):

\\[
{dp_i(t) \\over dt} = -p_i(t) \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} + \\sum_{j \\in S, \\, j \\ne i} p_j(t) q_{j, i}
\\]

If for all states \\( i \\in S \\) there exists some limit \\( p_i \\) such that as \\( t \\rightarrow \\infty, \\, p_i(t) \\rightarrow p_i \\) (i.e. there exists a steady state probability for all states) then:

\\[
\\lim_{t \\rightarrow \\infty} {dp_i(t) \\over dt} = 0
\\]

which means:

\\[
0 = -p_i \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} + \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, i} \\\\
\\]

so finally we get the **balance equations**:

\\[
p_i \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} = \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, i}
\\]

### Vector/Matrix Form

To go a step futher, remember that the diagonal entries to the generator matrix are equal to the negative sum of each row. As a result, we can rewrite the equation above:

\\[
\\begin{align}
p_i \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j} &= \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, i} \\\\
-p_i q_{i,i} &= \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, i} \\\\
0 &= p_i q_{i,i} + \\sum_{j \\in S, \\, j \\ne i} p_j q_{j, i} \\\\
0 &= \\sum_{j \\in S} p_j q_{j, i}
\\end{align}
\\]

and if we let \\( \\vec{p} = \\begin{bmatrix} p_1 & p_2 & \\dots & p_n \\end{bmatrix} \\) then we can then rewrite the balance equations as the following:

\\[
\\begin{align}
\\vec{p} \\boldsymbol{Q} = \\boldsymbol{0}
\\end{align}
\\]
