# Properties of the Exponential Distribution

Here are three properties of the exponential distribution that will be useful to recap:

1. The exponential distribution is _memoryless_, meaning that the future is independent to the past:

\\[
\\begin{aligned}
P(X \\le t + s | X > t) &= 1 - {P(X \\gt t + s \\land X \\gt t) \\over P(X > t)} \\\\
                        &= 1 - {P(X \\gt t + s) \\over P(X \\gt t)} \\\\
                        &= 1 - {e^{-\\lambda (t + s)} \\over e^{-λt}} \\\\
                        &= 1 - {e^{-\\lambda s} * e^{-\\lambda t} \\over e^{-\\lambda t}} \\\\
                        &= 1 - e^{-\\lambda s} \\\\
                        &= P(X \\le s)
\\end{aligned}
\\]

2. If \\( X_1 \\sim exp(\\lambda_1) \\) and \\( X_2 \\sim exp(\\lambda_2) \\) then \\( min(X_1, X_2) \\sim exp(\\lambda_1 + \\lambda_2) \\):

\\[
\\begin{aligned}
P(min(X_1, X_2) \\le t) &= 1 - P(min(X_1, X_2) \\gt t) \\\\
                        &= 1 - P(X_1 \\gt t \\land X_2 \\gt t) \\\\
                        &= 1 - e^{-\\lambda_1 t} e^{-\\lambda_2 t} \\\\
                        &= 1 - e^{-t(\\lambda_1 + \\lambda_2)}
\\end{aligned}
\\]

3. If \\( X_1 \\sim exp(\\lambda_1) \\) and \\( X_2 \\sim exp(\\lambda_2) \\) then

\\[
\\begin{aligned}
P(X_1 < X_2) &= \\int_0^{\\infty} P(X_1 \\lt X_2 | X_1 = x) * \\lambda_1 * e^{-\\lambda_1 x} dx \\\\
             &= \\int_0^{\\infty} P(X_2 \\gt x) * λ_1 * e^{-\\lambda_1 * x} dx \\\\
             &= \\int_0^{\\infty} e^{-\\lambda_2 x} * \\lambda_1 * e^{-\\lambda_1 x} dx \\\\
             &= \\lambda_1 \\int_0^{\\infty} e^{-x(\\lambda_1 + \\lambda_2)} dx \\\\
             &= \\lambda_1 \\left[ {-e^{-x(\\lambda_1 + \\lambda_2)} \\over \\lambda_1 + \\lambda_2}  \\right]_0^\\infty \\\\
             &= \\lambda_1 {0 - (-1) \\over \\lambda_1 + \\lambda_2}  \\\\
             &= {\\lambda_1 \\over \\lambda_1 + \\lambda_2} \\\\
\\end{aligned}
\\]

and therefore by swapping \\( X_1 \\) and \\( X_2 \\):

\\[
P(X_2 < X_1) = {\\lambda_2 \\over \\lambda_1 + \\lambda_2}
\\]
