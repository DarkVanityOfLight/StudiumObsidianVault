
## Definable Integer Relations

A formula $\varphi(\overline x)$ (with $\overline x = (x_1, \dots, x_k)$ ) over $\mathcal Z_+$ defines the $k$ ary integer relation $[[\varphi]] := \lbrace \overline n\in\mathbb Z^k : \mathcal Z_+ \vDash \varphi(\overline n)\rbrace$

A relation $R\subseteq \mathbb Z^k$ is $\mathcal Z_+$-_definable_ if there exists a formula $\varphi(\overline x)$ such that $[[\varphi]] = R$

## Real Linear Arithmetic
$$\mathcal R_+ := (\mathbb R; <, +, 0,1 )$$
We can add rational constant symbols interpreted as themselves
$$c \quad (c\in \mathbb Q)$$
and the scalar multiplication unary function symbols
$$c\cdot : n\mapsto c\cdot n\quad (c\in\mathbb Q)$$

A formula $\varphi(\overline x)$ (with $\overline x = (x_1, \dots, x_k)$ ) over $\mathcal R_+$ defines the $k$ ary integer relation $[[\varphi]] := \lbrace \overline n\in\mathbb Z^k : \mathcal R_+ \vDash \varphi(\overline n)\rbrace$

A relation $R\subseteq \mathbb R^k$ is $\mathcal R_+$-_definable_ if there exists a formula $\varphi(\overline x)$ over $\mathcal R_+$ such that $[[\varphi]] = R$.

>[!THEOREM]
>Every $\mathcal R_+$ definable set $S\subseteq \mathbb R$ is expressible as a finite union of intervals with rational endpoints.


