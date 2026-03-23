Let $(X, \le)$ be a [quasi-ordering](Halbordnung.md), we define $(X^*, \le_*)$ 
- $X^*$ is the set of finite sequences over $X$ 
	$$X^* := \lbrace (x_1, \dots, x_n) | n\in\mathbb N, x_1, \dots, x_n\in X\rbrace$$
- We have $(x_1, \dots, x_n) \le_* (y_1, \dots, y_m)$ iff $n \le m$ and there is a function $f: \{1, ..., n\} \to \{1, ..., m\}$ with $f(i+1) > f(i)$ for $i\in\{1, ..., n-1\}$ and 
	$$x_i \le y_{f(i)} \forall i\in\{1, ..., n\}$$

