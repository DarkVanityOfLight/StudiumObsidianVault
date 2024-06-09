
The general simplex form allows:
- Equalities of the form: $$a_1 x_1 + \dots + a_n x_n = 0\quad(a_i \in\mathbb Q)$$
- Elementary atoms: Lower/Upper bounds on the variables $$l_i \le x_i \le u_i\quad(l_i, q_i \in \mathbb Q \cup \lbrace - \infty, \infty \rbrace)$$
## Conversion to general form

Given a constraint $L \bowtie R$ with $\bowtie \in\lbrace =,\le, \ge\rbrace$, we transform it as follows. Let $m$ be the number of constraints. For the $i$th constraint $1 \le i\le m$:

1. Move all addends in $R$ to the left hand side to obtain $L' \bowtie b$, where $b$ is a constant
2. Introduce a new variable $s_1$. Add the constraints $$L' - s_i = 0 \quad\text{and}\quad s_i \bowtie b$$
   If $\bowtie$ is the equality, we rewrite $s_i = b$ to $s_i \ge b$ and $s_i \le b$

The new variables $s_1, \dots, s_m$ are called the additional variables. The variables $x_1,\dots, x_n$ in the original constraints are called problem variables.