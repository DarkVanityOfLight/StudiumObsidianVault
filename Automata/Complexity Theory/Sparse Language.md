
Call $L$ unary if $L \subseteq a^*$ for some letter $a$.


If $P \not = NP$ then there exists no unary [NP-Complete](NP-Complete.md)language.

__Proof__
Assume there exists a an NP-complete unary language $L \subseteq a^*$, then there exists a polytime reduction $f$ from SAT to $L \subseteq a^*$.
We use $L$ to proof $SAT \in P$.

Given $\varphi$, we maintain a set $S$ of formulas such that $\varphi$ is satisfiable iff $\exists \psi \in S$ such that $\psi$ is satisfiable.

- Initially $S = \lbrace \varphi\rbrace$ 
- Repeat:
	- Remove $\psi \in S$, and insert $\psi[x/0]$ and $\psi[x/1]$ into $S$ for some variable $x$ in $\varphi$
	- If there exists $\psi_1 \not = \psi_2 \in S$ such that $f(\psi_1) = f(\psi_2)$, remove $\psi_2$ from $S$
	- If there exists $\psi \in S$ such that $f(\psi) \not\in a^*$ remove $\psi$ from $S$
	- Return True if $S$ contains a true formula
- Return False


The size of $S$ is polynomial bounded in $|\varphi|$

---

We call $L \subseteq\Sigma^*$ sparse if there exists a polynomial $p(n)$ with
$$\lbrace w \in L : |w| = n\rbrace \le p(n) \qquad \forall n$$
(The growth of the language is polybound)

> Every unary language is sparse

---

If $P \not = NP$ then no sparse language is NP-complete.
