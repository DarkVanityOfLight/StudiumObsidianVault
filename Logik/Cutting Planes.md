
Cutting Planes are constraints that are added to a linear system that remove only noninteger solutions.

## Gomory Cuts

The assignment to the basic variable has to be fractional; second, the assignment to all the nonbasic variables have to correspond to one of their bounds. 

Consider the $i$th constraint:
$$x_i = \sum_{x_j \in \mathcal N} a_{ij} x_j$$
where $x_i\in\mathcal B$. Let $\alpha$ be the assignment returned by the general Simplex algorithm. Thus,
$$\alpha(x_i) = \sum_{x_j \in\mathcal N} a_{ij} \alpha(x_j)$$
We now partition the nonbasic variables to those that are currently assigned their lower bound and those that are currently assigned their upper bound:
$$\begin{align}
&J = \lbrace j | x_j \in\mathcal N \land \alpha(x_j) = l\rbrace\\
&K = \lbrace j | x_j \in\mathcal N\land \alpha(x_j) = u_j
\end{align}$$
Subtracting the assignment from the constraint and taking the partition into account leaves us with:
$$ x_i -\alpha(x_i) = \sum_{j\in J} a_{ij}(x_j - l_j) - \sum_{j\in K} a_{ij} (u_j - x_j)$$
Let $f_0 = \alpha(x_i) - \lfloor \alpha(x_i)\rfloor$. Since we assumed that $\alpha(x_i)$ is not an integer then $0 < f_0 < 1$. We can now rewrite the equation as:
$$x_i - \lfloor \alpha(x_i)\rfloor = f_0 + \sum_{j\in J}a_{ij}(x_j - l_j) - \sum_{j\in K} a_{ij}(u_j -x_j)$$
The left hand side is now an integer. We have to consider two cases:
- If $\sum_{j\in J} a_{ij}(x_j - l_j) - \sum_{j\in K} a_{ij} (u_j - x)j) > 0$ then, since the right hand side must be an integer, $$f_0 + \sum_{j\in J} a_{ij} (x_j -l_j) - \sum_{j\in K} a_{ij}(u_j - x_j) \ge 1$$ We now split $J$ and $K$ as follows: 
  $$\begin{align}
  &J^+ = \lbrace j | j\in J \land a_{ij} > 0\rbrace\\
  &J^- = \lbrace j | j\in J \land a_{ij} < 0\rbrace\\
  &K^+ = \lbrace j | j\in K \land a_{ij} > 0\rbrace\\
  &K^- = \lbrace j | j\in K \land a_{ij} < 0\rbrace
  \end{align}$$
  Gathering only the positive elements in the left hand side gives us
  $$\sum_{j\in J^+}a_{ij}(x_j -l_j) - \sum_{j\in K^-} a_{ij} (u_j - x_j) \ge 1 -f_0$$
  or equivalently
  $$\sum_{j\in J^+} \frac{a_{ij}}{1 -f_0} (x_j -l_j) - \sum_{j\in K^-} \frac{a_{ij}}{1 -f_0}(u_j - x_j) > 1$$
  
- If $\sum_{j\in J} a_{ij}(x_j -l_j) - \sum_{j\in K} a_{ij} (u_j - x) \le 0$, then again the right hand side must be an integer 
  $$f_0 + \sum_{j\in J} a_{ij} (x_j - l_j) - \sum_{j\in K} a_{ij}(u_j -x_j) \le 0$$
  This implies
  $$\sum_{j\in J^-} a_{ij}(x_j -l_j) - \sum_{j\in K^+} a_{ij}(u_j -x_j) \le -f_0$$
  Dividing by $-f_0$ gives us
  $$- \sum_{j\in J^-} \frac{a_{ij}}{f_0} (x_j - l_j) + \sum_{j\in K^+} \frac{a_{ij}}{f_0} (u_j -x_j) \ge 1$$
Note that the left hand side is greater than zero. Therefore these two equations imply

$$\begin{align}
\sum_{j\in J^+} \frac{a_{ij}}{1-f_0} (x_j - l_j) - \sum_{j\in J^-} \frac{a_{ij}}{f_0}(x_j -l_j) + \sum_{j\in K^+} \frac{a_{ij}}{f_0} (u_j) -x_{j} - \sum_{j\in K} \frac{a_{ij}}{1 - f_0} (u_j - x_j) \ge 1
\end{align}$$

Since each of the elements on the left hand side is equal to zero under the current assignment $\alpha$ is ruled out by the new constraint. In other words, the solution to the linear problem augmented with the constraint is guaranteed to be different from the previous one.

