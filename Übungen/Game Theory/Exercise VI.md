## Sheet 8
### Exercise 1
$$(\mathfrak A, \overline a) \leftrightarrow_d (\mathfrak B, \overline b)$$
$d \ge \frac{}{3^r - 1}{2}$
$\implies (\mathfrak A, \overline a) \equiv_r (\mathfrak B, \overline b)$

$r = 0 \qquad d \ge 0 (\mathfrak A, \overline a) \leftrightarrow_0 (\mathfrak B, \overline b)$
$$(\mathfrak A, \overline a) \equiv_0 (B, \overline b)$$
$r \to r+1$

$$d \ge \frac{3^{r+1}-1}{2} = 3 \cdot \frac{3^r - 1}{2} +1 > \frac{3^r -1}{2} = d'$$
$$(\mathfrak A, \overline a) \leftrightarrow_d (\mathfrak B, \overline b)$$
$\implies(\mathfrak A, \overline a) \leftrightarrow (\mathfrak B, \overline b)$
$\implies (\mathfrak A, \overline a) \equiv_r (\mathfrak B, \overline b)$
$\forall c N_d^\mathfrak A (\overline a, c) \equiv N_d^\mathfrak B(\overline b, f(c))$

$r+1$ round
$S c \in A(d \in B)$
$D f(c) \in B(f^{-1}(b)\in A)$


----

$Q FO[k]$ Hanf local
$hlr(Q) \le \frac{3^k-1}{2}$

$\mathfrak A \in Q\qquad \mathfrak B \not\in Q$
$\mathfrak A \not\equiv_k \mathfrak B$

$hlr(Q) > \frac{3^k -1}{2}$
$\implies \mathfrak A \equiv_k B$ Wiederspruch

### Aufgabe 2
![[Exercise VI 2025-01-21 14.17.37.excalidraw]]
$\varphi \in FO[k]$

$\mathfrak A \vDash \varphi \qquad \mathfrak B \not\vDash \varphi$

$\varphi$ Hanf Local
$r = \frac{3^k - 1}{2}$
$\mathfrak A \leftrightarrow_r \mathfrak B$
$\exists f : A \to B$
$\forall a \in A \qquad N_r^\mathfrak A(a) \cong N_r^\mathfrak B(f(a))$

$dist a$ root/leaf $> r$

dist a root $\le r$
$f(a)$
dist a leaf $\le r$
$\implies A\leftrightarrow_r B$
$\mathfrak A \equiv_k \mathfrak B$ Wiederspruch

## Sheet 9

### Exercise 1

$\varphi \qquad w = w_1 \dots w_n$
Rewrite as boolean combination of future and past fragments.

$\psi$ future formula(Y, S) $w, 1 \vDash \varphi \iff v, 1 \vDash \varphi$
$\varphi_i = Y \varphi_i$
$w, 1 \vDash F\varphi \iff 1 > 1 \land \dots \iff  w_1 \vDash \bot$
$\psi_i = \bot$

$\varphi_i^1 P \psi_i S \varphi_i^2 \qquad w_i^1 \vDash \varphi_i$
$\iff \exists j[1, 1] w_{ij} \vDash \varphi_i^2 \forall k[1,1] w, k\vDash \varphi_i^1$
$\iff w_{i, j} \vDash \varphi_i^2$
$\psi_i = \varphi_i^2$

## Exercise 2

$$G(a \to F(b\lor c))$$

$$\varphi(x) = \forall y(x \le y \land (U_a(y) \to \exists z(y \le z \land U_b(z) \lor U_c(z)))))$$
---

$$Gd \lor (Fa \to Fb \lor (F(c \land XFc)))$$

$$\varphi(x) = \forall y(x \le y \land U_d(y)) \lor \exists z(x \le z \land U_a(z)) \to \exists w(x \le w \land U_b(w)) \lor \exists v(x \le v \land U_c(v) \land \exists u(v \le u \land \not\exists t(v < t < u) \land \exists s (u \le s \land U_c(s))))$$
