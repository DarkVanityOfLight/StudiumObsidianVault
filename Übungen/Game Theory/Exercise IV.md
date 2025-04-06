


## Aufgabe 1

$\varphi(x_1, \dots, x_n)$ over $\sigma$

$\sigma_n = \sigma \cup \lbrace c_1, \dots, c_n\rbrace$

$\mathfrak A\quad(a_1, \dots, a_n) \in A$
$A(a_1, \dots, a_n) = \mathfrak A'$
$c_i^{\mathfrak A'} = a_i$

$$\phi^{\mathfrak A'} = \varphi^{\mathfrak A'}(c_1^{\mathfrak A'}, \dots, c_n^{\mathfrak A'}) = \varphi^{\mathfrak A'}(a_1, \dots, a_n) = \varphi^\mathfrak A(a_1, \dots, a_n)$$

$\mathfrak A' \vDash \phi \iff A \vDash \varphi$

## Aufgabe 2

$$\sigma = \lbrace <, U_a, U_b\rbrace$$

$w_1 = aba$
$A = \lbrace 1, 2, 3\rbrace$
$< = \lbrace (i, j) | i < j\rbrace$
$U_a = \lbrace 1, 3\rbrace$
$U_b = \lbrace 2 \rbrace$

$w_2 = abbbbbaa$
$A = \lbrace 1, \dots, 8\rbrace$
$< = \lbrace (i, j) | i < j\rbrace$
$U_a = \lbrace 1, 7, 8\rbrace$
$U_b = \lbrace 2,3,4,5, 6 \rbrace$

$h: A\to B$
$h(1) = 1$
$h(2) = e \in\lbrace 2, 3, 4, 5, 6\rbrace$
$h(3) = y \in \lbrace 7, 8\rbrace$

$5\cdot 2 = 10$


## Aufgabe 3

$\sigma = \lbrace <, \min, \max\rbrace$ 
$\exists k > 0$

$\mathfrak A, \mathfrak B$

$|A| = 2^k$
$|B| = 2^{k-1}$
$$\mathfrak A \not\equiv \mathfrak B$$

$k=2 \implies |A| = 4\quad |B| = 2$
Spoiler chooses any Element not $\min$ or $\max$
Duplicator chooses $\min$
S chooses $\min$
Duplicator has no valid move

## Aufgabe 4

$$\lbrace a^nb^n | n \ge 0\rbrace \text{not expressible in FO}$$
$\iff \forall k \exists \mathfrak A \in L, B \not \in L$
$A \equiv_k B$

$k > 0$
$n = 2^k$
$a^n b^n$ und $a^n b^{n+1}$

S picks $a$
D picks $a$ with the same position
$S$ picks $b$
D picks $b$ at the same position
> Then he realized this won't work
> and suggested a proof using the knowledge that
> two linear order of size $2^k$ are equal
> For this split the word(a part is obviously equivalent) the
> second part follows from the linear order lemma


## Aufgabe 5

$\mathfrak A, \mathfrak B$ cycles of length at least $2^k$
$\mathfrak A \equiv_k \mathfrak B$

$A = \lbrace 1, \dots, n\rbrace$
$E = \lbrace (i, j) | i+1 = j\rbrace \cup \lbrace (n, 1)\rbrace$

Spoiler picks any $a \in A$ 
Duplicator picks any $b\in B$

Spoiler picks $a' \in A$
Then there are two areas
$a \to a'$ and $a' \to a$
Let $a \to a'$ be the smaller one

then $a' \to a$ has size $\ge 2^{k-1}$

D picks $b'\in B$
such that $|a \to a'| = |b \to b'|$

$\mathfrak A^{\le a' } \equiv_{k-1} \mathfrak B^{\le b'}$
$\mathfrak A^{\ge a'} \equiv_{k-1} B^{\ge b'}$
