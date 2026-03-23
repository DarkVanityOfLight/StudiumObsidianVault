

Let $(X, \le)$ be a [WQO](Well-quasi-ordering.md) such that $X$ is countable. For every subset $I\subset X$, the following are equivalent:

1. $I$ is an [ideal](Ideal.md)
2. $I$ is [Downward Closed](Downward%20Closed.md), non-empty and for any two downward closed sets $D_1, D_2, \subseteq X$, we have $I\subseteq D_1 \cup D_2$ implies that $I\subseteq D_1$ or $I \subseteq D_2$.
3. There is an ascending chain $y_1 \le y_2 \le \dots \in I$ such that $I = \{y_1, y_2, \dots\}\downarrow$.



$(1) \implies (2)$

Suppose $I\not\subseteq D_1$ and $I \not\subseteq D_2$, then there is an $x_1 \in I \setminus D_1$ and $x_2 \in I\setminus D_2$. Since $I$ is upward directed, there is a $y\in I$ with $x_1 \le y$ and $x_2\le y$. Since $I\subseteq D_1 \cup D_2$, we have either $y\in D_1$ or $y\in D_2$, thus $x_1 \in D_1$(symmetric for $D_2$), but both are impossible, which is an contradiction.


$(2) \implies (1)$
Since $I$ is downward closed, it remains to be shown that $I$ is upward directed. Suppose $I$ is not upward directed, then there are $x_1, x_2\in I$ such that there is no $y\in I$ with $x_1 \le y$ and $x_2 \le y$. In particular, $x_1 \nleq x_2$  and $x_2 \nleq x_1$. Consider the following subsets
$$D_1 = \{x\in I | x_1 \nleq x\} \quad D_2 = \{x\in I | x_2 \nleq x\}$$
Then $I \subseteq D_1 \cup D_2$ because there is no $y$ as above. By assumption $I\subseteq D_1$ or $I\subseteq D_2$. In the first case, we have $x_1 \in D_1$, in the second case, we have $x_2 \in D_2$, which is a contradiction.


$(3) \implies (1)$

Clearly, the set $I = \{y_1, y_2, \dots\}\downarrow$ is downward closed, and non-empty. It remains to show that $I$ is upward directed. So let $x_1, x_2 \in I$. Then there are $y_i, y_j$ with $x_1 \le y_i$ and $x_2 \le y_j$. Set $m = \max\{i, j\}$. Since $y_1 \le y_2 \le \dots$, we have $y_i, y_j \le y_m$ and thus $x_1, x_2 \le y_m$.
Hence $I$ is upward directed.

$(1) \implies (3)$
Since $X$ is countable, $I$ is countable as well: There is a sequence $x_1, x_2, \dots$ such that $I = \{x_1, x_2, \dots\}$.
We construct $y_1, y_2, \dots$ successively as follows:

1. $y_1 = x_1$
2. Suppose we have $y_1, \dots, y_i$. Since $I$ is upward directed, there is some $y\in I$ with $y_i \le y$and $x_{i+1} \le y$. Take $y_{i+1} := y$
We claim that $I = \{ y_1, y_2, \dots \}\downarrow$.
Since $y_i \in I$ for every $i\in\mathbb N$, we clearly have $\supseteq$.
If $x\in I$, then $x = x_i$ for some $i\in\mathbb N$, then we have $x_i \le y_i$ and thus $x = x_i\in\{y_1, y_2,\dots\}\downarrow$.

