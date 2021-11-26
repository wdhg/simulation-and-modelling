# Sampling Discrete Distributions

Once again, we can apply the inverse transform method by finding the inverse of the c.d.f.

Take an arbitrary random variable \\( X \\); its c.d.f will be a "step function":


```

                            F(x)
                               ^
  *---*--------*------*   1.00 |               +---+
  | x | P(X=x) | F(x) |   0.81 |           +---+   |
  *---*--------*------*   0.66 |       +---+   |   |
  | 0 |  0.15  | 0.15 |        |       |   |   |   |
  | 1 |  0.24  | 0.39 |   0.39 |   +---+   |   |   |
  | 2 |  0.22  | 0.61 |        |   |   |   |   |   |
  | 3 |  0.20  | 0.81 |   0.15 +---+   |   |   |   |
  | 4 |  0.19  | 1.00 |        |   |   |   |   |   |
  *---*--------*------*        +---+---+---+---+---+--->
                                 0   1   2   3   4     x

```

Thus, take a uniform random variable \\( U \\sim U(0, 1) \\), then the inverse transform method gives us:

\\[
X = \\min \\{ x : F(x) \\ge U \\}
\\]

In practice, this can be done by simply looking up the which value in the c.d.f is greater than \\( U \\):

```
Sample U from U(0, 1)

For each x:
  If U <= F(x):
    Return x
```


## Sampling in Constant Time (Alias Method)

The previous solution runs in \\( O(n) \\), but it is possible to sample the distribution in \\( O(1) \\). The idea is to convert the p.d.f, which looks like this

```
  f(x) ^
       |   +---+
       |   |   |   +---+
       |   |   +---+   |
       |   |   |   |   +---+
       +---+   |   |   |   |
       |   |   |   |   |   |
       |   |   |   |   |   |
       +---+---+---+---+---+-->
         0   1   2   3   4    x
```

into something that looks like this:

```

       ^
       |
       |
   1/n +---+---+---+---+---+
       |   |   |   |   +---+
       +---+   |   |   |   |
       |   |   |   |   |   |
       |   |   |   |   |   |
       +---+---+---+---+---+-->
         0   1   2   3   4    x
```

where \\( 1 \\over n \\) is the average height of each column. Note that in this diagram, each "block" no longer corresponds to the horizontal coordinate of the graph.

### Construction Algorithm

This rectangle can be constructed by breaking up columns that exist above the average height \\( m \\) into smaller chunks, then putting all of these smaller chunks back together.

```
Caluclate m
Let smaller be the set of tuples (x, p) where p = p(x) and p <= m
Let larger be the set of tuples (x, p) where p = p(x) and p > m
Let result be an empty list of tuples (x1, x2, alias)

For each column in the output result:
  Pop (x1, p1) from the smaller set
  Pop (x2, p2) from the larger set
  Let (x3, p3) = (x2, p2 - p1)
  Let result[column] = (p1, x1, x2)

  If p3 <= m:
    Push (x3, p3) to smaller
  Else:
    Push (x3, p3) to larger
```

Note the algorithm above is simplified just to convey the general idea (i.e. it doesn't handle the case where \\( p(x) = {1 \\over n} \\)).

### Sampling Algorithm

To sample this new graph, two uniform random numbers will be needed:

1. \\( U_1 \\sim U(0,4) \\) is a *discrete* random variable which will pick which column is to be sampled.
2. \\( U_2 \\sim U(0, m) \\) is a *continuous* random variable which will decide which chunk of the column is chosen.

Then, using the list `result` from the construction algorithm:

```
Let u1 be a sample from U1
Let u2 be a sample from U2
Let (x1, x2, alias) = result[u1]

If u2 <= alias:
  Return x1
Else:
  Return x2
```

It is obvious that this algorithm will run in \\( O(1) \\) if the sampling methods for \\( U_1, U_2 \\) run in \\( O(1) \\) (which they do).
