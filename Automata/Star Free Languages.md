A star free language $L \subset \Sigma^*$ is defined as the following
- $\emptyset$
- $\{\epsilon\}$
- $\{a\} a\in\Sigma$
- $\overline L$
- $L \cup L'$
- $L.L'$



> A language is FO-Definable iff it is star free

We only show the direction from star free to FO.

Clearly $\emptyset, \{\epsilon\}, \{a\}$ are expressible in FO. Same with complement and union. It remains concatenation. For that define
$$ \phi_{L.L'} := \exists x.(\phi_L^\le(x) \land \phi_{L'}^{\gt}(x))$$
Where $\phi^\le(x)$  is obtained by replacing each $\exists y. \psi(y)$ by $\exists y. y \le x \land \psi(y)$ and $\forall y. \psi(y)$ with $\forall y. x \le y \to \psi(y)$(similar $\phi^>$).

This does not work if $\epsilon \in L$, we then rewrite as
$$ (L\setminus \epsilon). L' \cup L'$$
