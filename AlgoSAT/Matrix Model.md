[Variables](Variable.md) are usually best understood as arranged in a matrix.
The variables are indexed by multiple dimensions
$$ X = (x_{i, j})\text{ with } i\in[n], j\in[m]$$
Each row and column corresponds to a meaningful entity. Symmetries often arise from permuting rows and columns


## Row Symmetry
Let $M := (l_{i, j})$ be an $n\times m$ matrix comprising a subset of $Lit(F)$.

Then $M$ exhibits row symmetry if there are symetries
$\{\varphi_{i_1, i_2}\}_{i_1, i_2 \in [1, n]}\subseteq Aut(F)$ that swap rows $i_1$ and $i_2$ via

$$\varphi_{i_1, i_2}(\ell) = \begin{cases}
\ell_{i_2, j} &\text{ if } \ell = \ell_{i_1, j} \text{ for some } j\in[1, m]\\
\ell_{i_2, j} &\text{ if } \ell = \ell_{i_2, j} \text{ for some } j\in[1, m]\\
\ell_{i, j} &\text{ if } \ell = \ell_{i, j}\in M \text{ and } i\not\in\{i_1, i_2\}
\end{cases}$$

## Symmetry breaking

There is an efficient, complete SBP for row symmetry. We use the column-major ordering.
Then using [lex-constraints](Total%20Order%20and%20Lexicographic%20Order.md) exchanging rows $i$ with $i+1$ for each $i$ is a [Complete Symmetry Breaking](Complete%20Symmetry%20Breaking.md) constraint.

There are two main ways of detecting row symmetry:
- Look for candidate row swaps in a given generating set, and try to build a matrix model for them
- Detect the matrix directly on the graph using individualization-refinement


A simple sketch
1. Pick a column
2. For each vertex $v$ from the column, individualize $v$. As the row of $v$, collect all other vertices $v'$ that get split
3. Verify that permutations of collected rows are symmetries.

