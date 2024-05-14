
Sei $\mathcal Z_< = (\mathbb Z; <, 0, s, p)$, mit
$s: \mathbb Z \to \mathbb Z$ als Nachfolgefunktion, d.h. $s : i \mapsto i+1$ und
$p: \mathbb Z\to\mathbb Z$ als die Vorgängerfunktion, d.h. $p:i\mapsto i+1$

>[!THEOREM]
>$\mathcal Z_<$ hat [Quantorenelemination](Quantorenelemination.md). Daher sind $\mathcal Z_<$ und $(\mathbb Z; <, 0)$ [Vollständig](Theorien%20der%20ersten%20Stufe.md#Vollständig) und [Entscheidbar](Entscheidbar.md).


## Vorbereitung

Wir definieren folgende Notation für jedes $k \in \mathbb N$
$$s^k(x) := s(\dots (x(x)) \dots)$$
$$p^k(x) := p(\dots(p(x)) \dots)$$

Außerdem definieren wir folgende Notation für jedes $k\in\mathbb Z\setminus \mathbb N$
$$s^k(x) := p^{-k}(x)$$


## QE-Methode 

Man zeigt, wie $x$ in $\exists x\varphi$ eliminierbar ist, wobei
$$\varphi = \bigwedge^{n}_{i=1} s^{k_i}(x) \sim_i s^{k'_i}(x_i) \text{ mit } \sim_i \in \lbrace <, >, =\rbrace$$

Es lässt sich annehmen, dass jedes Konjunkt die folgende Form hat
$$x \sim s^k(y)$$
für bestimmte $\sim, k$.

### Fall 1
Ein Konjunkt ist $x\sim s^k(x)$. Ersetze ihn entsprechend durch $\top$ oder $\bot$.

1. Ersetze $x \sim s^k(x)$ durch $\top$ genau dann wenn $x \sim x+k$, sonst $\bot$
2. Wenn wir durch $\bot$ ersetzen, ersetze $\exists\varphi$ durch $\bot$
3. Sonst gehe zu Fall 2

### Fall 2
Ein Konjunkt ist $x = s^k(y)$, wobei sich $y$ und $x$ auf verschiedene Variablen beziehen. Dann:
$$\mathcal Z_< \vDash \exists x\varphi \leftrightarrow \varphi[s^k(y)/x]$$

### Fall 3
Trenne die Ober-/Untergrenzen von $x$. Dann:
$$\mathcal Z_< \vDash \exists x \left( \bigwedge^r_{i=1} s^{k_i}(y_i) < x \land \bigwedge^s_{j=1} x < s^{k'_j}(z_j)\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} s^{k_i+1}(y_i) < s^{k'_j}(z_j)$$


---

Aus dem QE Algorithmus folgt:

>[!THEOREM]
>$Th(\mathcal Z_<)$ und $Th(\mathbb Z; <, 0)$ sind vollständig und entscheidbar.

