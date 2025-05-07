

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
- Build $\gamma_i = (p_{2i-1} \le \omega \to (r^T_i x_0 \le p_{2i-1} \land r_{i}^T x \le 0) \land (p_{2i} \le \omega \to (p_{2i} \le s_{i}^T x_0 + t_i^T z+ h_i \land s_i^T x \ge 0)) \land (p_{2i} = \omega \to s_i^T x > 0)$ 
- $\delta_j = u_j^t x_0 \approx_{e_j}^j v_j^T (x_0 + x) + w_j^T z + d_j \land u_j^T x \equiv_{e_j} 0 \land v_j^T x \equiv_{e_j} 0$  
- $\theta = \bigwedge^n_{i=1} (p_{2i -1} \le \omega \land p_{2i-1} \le p_{2i} \lor p_{2i} = \omega)$(admissible) 