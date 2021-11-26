# Inverse Transform Method

Assume that the goal is to sample the continuous random variable \\( X \\), which has a c.d.f \\( F(x) = P(X \\le x) \\). Since \\( F(x) \\) is a c.d.f, there are a couple of properties to note:

1. \\(0 \\le F(x) \\le 1 \\)
2. \\( F(x) \\) increases monotonically (i.e. at all points it is increasing in value).

As a result, if we let \\( U \\sim U(0, 1) \\) then we get:

\\[
\\begin{align}
P \\left( X \\le x \\right) &= P \\left( F^{-1} (U) \\le x \\right) \\\\
                            &= P \\left( U \\le F(x) \\right) \\\\
                            &= F(x)
\\end{align}
\\]

This demonstates that if \\( F^{-1}(x) \\) exists, then by setting \\( F(X) \\) (notice how it's \\( X \\) not \\( x \\) as we are dealing with sampling the random variable) equal to the uniform random variable \\( 0 \\le U \\le 1 \\) we can manipulate the equation to get \\( X \\) in terms of \\( U \\).

### Example 1

If \\( X \\sim U(a,b) \\) then:

\\[
F(x) = {x - a \\over b - a}, \\quad a \\le x \\le b
\\]

From setting \\( U = F(X) \\) and inverting \\( F \\) we get:

\\[
\\begin{align}
U &= F(X) \\\\
U &= {X - a \\over b - a} \\\\
X - a &= U * (b - a) \\\\
X &= U * (b - a) + a
\\end{align}
\\]

This also matches what we'd expect intuitively: \\( U \\sim U(0,1) \\) so \\( U * (b - a) + a \\sim U(a,b) \\).

### Example 2

If \\( X \\sim exp(\\lambda) \\) Then

\\[
F(x) = 1 - e^{-\\lambda x}, \\quad X \\ge 0
\\]

From setting \\( U = F(X) \\) and inverting \\( F \\) we get:

\\[
\\begin{align}
U &= 1 - e^{-\\lambda X} \\\\
1 - U &= e^{-\\lambda X} \\\\
log_e(1 - U) &= -\\lambda X \\\\
{-log_e(1 - U) \\over \\lambda} &= X
\\end{align}
\\]

As a result, if \\( U \\sim U(0,1) \\) then \\( -log_e(1 - U) / \\lambda \\sim exp(\\lambda) \\). Notice that we can also replace \\( 1 - U \\) with \\( U \\) as \\( 1 - U \\sim U(0,1) \\) as well. This means that \\(-log_e(U) / \\lambda \\sim exp(\\lambda) \\).

