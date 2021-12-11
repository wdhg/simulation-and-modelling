# Continuous-Time Markov Chains CTMCSs

**Continuous-Time Markov Chains** (also known as **Markov Processes (MPs)** ) are a form of stochastic processes which is defined by a set of states \\( S \\) and a square matrix known as a **transition rate matrix** or **generator matrix** \\( \\boldsymbol{Q} \\) with dimensions \\( \\lvert S \\rvert \\times \\lvert S \\rvert \\). For example, a CTMC with \\( 3 \\) states will have the following generator matrix:

\\[
\\begin{bmatrix}
  -(q_{1,2} + q_{1,3}) & q_{1,2} & q_{1,3} \\\\
  q_{2,1} & -(q_{2,1} + q_{2,3}) & q_{2,3} \\\\
  q_{3,1} & q_{3,2} & -(q_{3,1} + q_{3,2}) \\\\
\\end{bmatrix}
\\]

where \\( q_{i, \\, j} \\) is the **transition-rate** from state \\( i \\) to state \\( j \\), \\( 1 \\le i, j \\le \\lvert S \\rvert \\) (more on generator matricies later).

In a CTMC there are no self-loops as they don't affect the transitions out of the system (remember that Poisson Processes are memoryless). This means that the diagonal terms \\( q_{i,i} \\) are effectively unused, and so they can be used for something else. By convention, the negative sum of each row is stored in the diagonals:

\\[
q_{i,i} = - \\sum_{j \\in S, \\, j \\ne i} q_{i, \\, j}
\\]

This will be useful later.

## State Holding Times

Since \\( q_{i, \\, j} \\) is the rate parameter of an exponentially distributed random variable, if \\( X_{i, \\, j} \\sim exp(q_{i, \\, j}) \\) then we get the following:

\\[
\\begin{align}
F_{i,\\,j}(x) &= 1 - e^{- q_{i, \\, j} x} \\\\
f_{i,\\,j}(x) &= q_{i, \\, j} e^{- q_{i, \\, j} x}
\\end{align}
\\]

where \\( x \\ge 0 \\) and \\( q_{i, \\, j} \\ge 0 \\). As a result, if there are multiple transitions out of a state, then they will "race" with each other: the first event to trigger will be the state transition taken. Thus, the **state holding time** is the **minimum** of the samples of each exponentially distributed random variable out of the current state:

\\[
\\begin{align}
P \\left( \\left( \\, \\min_{1 \\le j \\le n} X_{i,\\,j} \\right) \\le x \\right) &= 1 - P \\left( X_1 \\gt x \\land \\dots \\land X_n \\gt x \\right) \\\\
&= 1 - \\prod_{j = 1}^n e^{-r_{i, \\, j} x} \\\\
&= 1 - e^{-(r_{i,1} + \\dots + r_{i,n}) x} \\\\
&= 1 - e^{q_{i,i} x}
\\end{align}
\\]

Remember that the minimum of a set of exponentially distributed random variables is also an exponentially distributed random variable (see [here](poisson-processes/properties-of-the-exponential-distribution.html)).

Therefore, the state holding time can be modelled by an exponentially distributed random variable with rate parameter \\( q_{i, i} \\).

## The Markov Property

Since the state holding time is exponentially distributed, it means that it is also memoryless. As a result, the next transition in the system is determined only by the current state. If \\( S(t) \\in S \\) is defined as the state of the process at time \\( t \\), then the **Markov Property** for \\( t_1 \\lt t_2 \\lt \\dots \\lt t_n \\) is defined as:

\\[
P \\left( S( t_n ) = s_n \\mid S(t_{n-1}) = s_{n-1}, \\dots , S(t_1) = s_1 \\right) = P \\left( S(t_n) = s_n \\mid S(t_{n-1}) = s_{n-1} \\right)
\\]

