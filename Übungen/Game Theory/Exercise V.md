## Aufgabe 1

$\sigma \qquad \mathfrak A \cong \mathfrak B$
$\mathfrak A \vDash \varphi \iff \mathfrak B \vDash \varphi$
$f: A\to B$ isomorphismus

> $\mathfrak A \cong_k \mathfrak B \forall \varphi \text{ quantifier rank } k$
> $\mathfrak A \vDash \varphi \iff \mathfrak B \vDash \varphi$

S picks $a\in A$
	D picks $f(a) \in B$
S picks $b\in B$
	D picks $f^{-1}(b) \in A$

$\mathfrak A \equiv_k \mathfrak B$
$\implies \mathfrak A \vDash \varphi \iff B \vDash \varphi$

---

$$\mathfrak A = \langle A, R_i^\mathfrak A, c_i^\mathfrak A\rangle$$
$|A| = n$

$$\varphi := \exists x_1, \dots, x_n \bigwedge_{i\not = j} x_i \not = x_j \land (\forall y \bigvee_{i=1}^n x_i = y) \land \bigwedge_{c_i} c_i = x_{j_{c_i}} \land \bigwedge_{R_i}(\bigwedge_{(a_{j_n, \dots, a_{j_x}}) \in R_i} R_i (x_{jn}, \dots x_{jr})) \land \bigwedge_{(a_{jn}, \dots a_{jr}) \not\in R_i} \neg R(x_{jn}, \dots, x_{jr})$$

## Aufgabe 2
