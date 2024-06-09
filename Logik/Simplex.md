
It is common to represent the coefficients in the input problem using an $m$ by $(n+m)$ matrix $A$. The variables $x_1, \dots,x_n, s_1,\dots s_m$ are written as a vector $x$. Following this notation, our problem is equivalent to the existence of a vector $x$ such that
$$Ax = 0 \quad \text{and}\quad \bigwedge^m_{i=1} l_i \le s_i \le u_i$$
where $l_i \in\lbrace -\infty\rbrace \cup \mathbb Q$ is the lower bound of $x_i$ and $u_i \in \lbrace-\infty\rbrace\cup\mathbb Q$ is the upper bound of $x_i$. The infinity values are for the case that a bound is not set.

Consider the following problem in [General Simplex Form](General%20Simplex%20Form.md)

$$\begin{align}
x + y -s_1 &= 0 \land\\
2x - y -s_2 &= 0 \land\\
-x + 2y-s_3 &= 0 \land\\
s_1&\ge 2\land\\
s_2&\ge 0\land\\
s_3&\ge 1
\end{align}$$

We receive the matrix

$$\begin{pmatrix}
1 & 1 & -1 &0 &0\\
2 & -1 & 0 &-1 &0\\
-1 & 2 & 0 & 0 & -1\\
\end{pmatrix}$$

A large portion of this matrix is regular: the columns that are added for the additional variables $s_1, \dots, s_m$ correspond to an $m$ by $m$ diagonal matrix, where the diagonal coefficients are $-1$. This is a direct consequence of using general form.
The variables corresponding to these columns are called the  _basic variables_ $\mathcal B$. We also call them dependent variables, as their values are determined by those of the _nonbasic variables_ $\mathcal N$

## Tableau

We can store $A$ as a _Tableau_, which is simply $A$ without the basic variables. The columns correspond to the basic variables and each row is associated with a basic variable. For our example this would be:

|       | x    | y    |
| ----- | ---- | ---- |
| $s_1$ | $1$  | $1$  |
| $s_2$ | $2$  | $-1$ |
| $s_3$ | $-1$ | $2$  |

The tablaeu is simply another representation of $A$, since $Ax = 0$ can be rewritten into 
$$\bigwedge_{x_i \in\mathcal B}\left(x_i = \sum_{x_j \in\mathcal N} a_{ij} x_j\right)$$
## Upper and Lower Bounds

The general simplex algorithm maintains, in addition to the tableau, an assignment $\alpha : \mathcal B \cup\mathcal N \to \mathbb Q$. The algorithm initializes its data structures as follows:

- The set of basic variables $\mathcal B$ is the set of additional variables
- The set of nonbasic variables $\mathcal N$ is the set of problem variables
- For any $x_i$ with $i\in\lbrace 1,\dots, n+m\rbrace, \alpha(x_i) = 0$.

## General Simplex

__Input__: A linear system of constraints $S$
__Output__: "Satisfiable" if the system is satisfiable, and "Unsatisfiable" otherwise

1. Transform the system into the general form 
   $$Ax = 0 \quad\text{and}\quad \bigwedge^m_{i=1} l_i \le s_i \le u_i$$
2. Set $\mathcal B$ to be the set of additional variables $s_1, \dots, s_m$.
3. Construct the tableau for $A$
4. Determine a fixed order on the variables
5. If there is a no basic variable that violates its bounds, return "Satisfiable". 
   Otherwise, let $x_i$ be the first basic variable in the ordering that violates its bounds.
6. Search for the first suitable nonbasic variable $x_j$ in the order for pivoting $x_i$. If there is no such variable return "Unsatisfiable"
7. Perform the pivot operation on $x_i$ and $x_j$
8. Go to step 5.

## Changing a value
Let $x_i$ be the smallest basic variable that violates its bounds, 
$x_i$ is a linear combination of nonbasic variables
$$x_i = \sum_{x_j\in\mathcal N} a_{ij} x_j$$
Let $\theta$ denote by how much we have to increase(or decrease) $\alpha(x_j)$ in order to meet its bound
$$\theta = \frac{b_j - \alpha(x_i)}{a_{ij}}$$
Where $b_i$ denotes the violated bound.
### Suitable variables
- The value of $x_i$ can be reduced by decreasing the value of a nonbasic variable $x_j$ such that $a_{ij} > 0$ and its current assignment is higher that its lower bound $l_j$ or by increasing the value of a variable $x_j$ such that $a_{ij} < 0$ and its current assignment is lower than its supper bound $u_j$
- The value of $x_i$ can be increased by increasing the value of a nonbasic variable $x_j$ such that $a_{ij} > 0$ and its current assignment is lower than its upper bound $u_j$ or by decreasing the value of a variable $x_j$ such that $a_{ij} < 0$ and its current assignment is higher that its lower bound $l_j$
Such a variable $x_j$ is called suitable. If there are no suitable variables then the problem is unsatisfiable and the algorithm terminates.

## Pivoting

>[!DEFINITION]
Given two variables $x_i$ and $x_j$, the coefficient $a_{ij}$ is called the pivot element. The column of $x_j$ is called the pivot column. The row $i$ is called the pivot row.

A precondition for swapping two variables $x_i$ and $x_j$ is that their pivot element is nonzero, $a_{ij} \not = 0$. The pivot operation is performed as follows:

1. Solve row $i$ for $x_J$.
2. For all rows $l \not = i$ eliminate $x_j$ by using the equality for $x_j$ obtained from row $i$.

