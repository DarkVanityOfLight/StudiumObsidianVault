
## Exercise 1


$$\delta(a, q) = (q' a', R)$$
$w = \# c_1 \# \dots \# c_k$

$|c_i| = m+1$
$c_i$ bcqade
$c_i+1$ bca'q'de

$$\varphi_{q, n} = \bigvee_{k=1}^{m-1} \bigwedge_{i=1}^{m-1} (\bigvee_{b \in \Gamma} X^i b \land X^{m+2+i} b) \land X^k q \land X^{m+3+k} q' \land X^{k+1} a \land X^{m+2+k} a' \bigwedge^{m+1}_{i= k+2}(\bigvee_{b \in\Gamma X^i } X^i b \land X^{m+2+i} b)$$


## Exercise 2

__LTL(X) is in NP__
$\varphi$ LTL(X)
$X(\varphi \lor \psi) = X\varphi \lor X\psi$

$k$ max depth of next operators $+1$


$\psi$ bool formula over $x_{i,j}$
$j \in \lbrace 1, \dots, |\Sigma|$
$\Sigma = \lbrace w_1 \dots, w_m\rbrace$
$X^i w_j \to x_{i, j}$

$\varphi \to \psi'$
$\psi = \psi' \land \bigwedge^k_{i = 1} \bigvee^m_{j=1} x_{i, j} \land \bigwedge_{j' \not = j} \neg x_{i, j'}$
$x_{i,j} sat \psi \iff w = a_1, \dots, a_k \qquad a_i = w_j \iff x_{i j} = 1$
$w \vDash \varphi$

__LTL(X) is NP hard__

$\psi$ bool formula


$\varphi = \psi_1 \sim \psi_2$
$\to \varphi = \varphi_1 \sim \varphi_2$ $\sim \in \lbrace \land, \lor\rbrace$
$\varphi = \neg \psi$
$\to \varphi = \neg \varphi_1$


$x_i \qquad i \in\lbrace 1, \dots, k\rbrace$
Variables of $\psi$
$\Sigma = \lbrace 0, 1\rbrace$
$\psi = X_i$
$\to \varphi X^{i-1} 1$

$w = w_1, \dots, w_n$
$w\vDash \varphi$
$\iff \psi \text{ is sat with } x_i = w_i$
