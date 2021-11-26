# Convolution Method

A distribution is a **convolution** of other distributions is it is the sum of their individual random variables. This sum can be weighted.

### Example

An \\( Erlang(k, \\theta) \\) random variable is defined as the sum of \\( k \\) random variables, each following an \\( exp(\\theta) \\) distribution.

The expected value is given by:

\\[
E(X) = {1 \\over \\theta} + {1 \\over \\theta} + \\dots + {1 \\over \\theta} = {k \\over \\theta}
\\]

Therefore, we can generate samples for an \\( Erlang(k, \\theta) \\) random variable using the inverse transform technique on the exponential distribution. If \\( X_i \\sim exp(\\theta) \\):

\\[
X = \\sum_{i = 1}^k X_i \\sim Erlang(k, \\theta)
\\]

Additionally, if \\( U_i \\sim U(0, 1) \\) then \\( X_i \\) is sampled using:

\\[
-\\ln{U_i \\over \\theta}
\\]

Calculating the logarithm of a value can be quite computationally expensive, so we can manipulate the result from a summation to a product:

\\[
\\begin{align}
X &= \\sum_{i = 1}^k - {\\ln{U_i} \\over \\theta} \\\\
  &= - {1 \\over \\theta} \\ln \\prod_{i = 1}^k U_i
\\end{align}
\\]
