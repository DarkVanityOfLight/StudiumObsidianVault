

Assume a formula of the form
$$\exists^{ram} \textbf{x},\textbf{y} \exists w \varphi(x, y, w, z)$$
with free variables $z$.


## Eliminating Existential quantifiers
- Make $\varphi$ $w$-Simple(for existentially quantified $w$)
	- $r^T u + c < w$, $w < r^T u + c$, $r^Tu + w \equiv_e d$ `(r*u + w) % e == d`
- Eliminate the existential quantifiers using the fact that
  $\exists^{ram} \textbf{x}, \textbf{y} \exists w:\varphi(\textbf{x}, \textbf{y}, \textbf{w}, \textbf{z}) \iff \exists^{ram} (x, v_1, v_2) (y, w_1, w_2) \varphi(x, y, v_1 + w_2, z)$

> When each (in)equality only contains one existential quantified variable we can bulk eliminate them.

## Eliminate the Ramsey Quantifier


- Push all negations down to the atoms
- Atoms of the form $r x < sy + tz + h$ or $ux \approx vy + wz d$ $\approx \in \lbrace \equiv_e, \not\equiv_e\rbrace$
- Introduce existential $q^<$ and $q^\approx$ for each atom
- $q^< =1 \to \alpha$ $q^{\approx} = 1 \to \beta$ for the corresponding atoms $\alpha, \beta$
- Create $\varphi'$ by replacing each atom with it's corresponding $q$ 
- $\psi := \exists q^{<}, q^{\approx} \varphi' \land \bigwedge_i (q_i^{<} = 1 \to \alpha_i) \land \bigwedge_j (q^{\approx}_j = 1 \to \beta_j)$ 
- 