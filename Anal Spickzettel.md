
Eine [Abbildung](Abbildungen.md) $f: M\to N$ heißt surjektiv wenn $f(M) = N$
Gilt für alle $m_1, m_2 \in M$ dass $f(m_1) = f(m_2) \implies m_1 = m_2$
so heißt die [Abbildung](Abbildungen.md)$f$ injektiv.

---

Schreiben wir $m \sim n$ für $m, n \in R$ dann bedeutet
- reflexiv, dass $m \sim m \qquad \forall m\in M$ 
- transitiv, dass $m\sim l, l\sim n \implies  m\sim n \quad \forall m,n \in M$
- symmetrisch, dass $m \sim n \implies n\sim m\quad \forall m, n \in M$

## Äquivalenzklassen
Ist $M$ eine  Menge, $\sim$ eine Äquivalenzrelation und $m\in M$, dann heißt $$[m] = \left\{n\in M : n \sim m\right\} \subset 2^M$$ die Äquivalenzklasse von $m$. Jedes $n \in [m]$ heißt Repräsentant von $[m]$

## Kanonische Abbildung
Wir schreiben $$M{\diagup\sim} = \{[m]|m\in M\} \subset 2^M$$ für die Menge der Äquivalenzklassen von $\sim$ und

$$\begin{align}
\pi :& M \to M/\sim\\
&m \mapsto [m]\\
\end{align}$$
für die kanonische Abbildung von $\sim$. Diese sind offenbar [Surjektiv](Surjektiv.md)

---

## Dreiecksungleichung

Sei $K$ ein angeordneter Körper. Es gilt
$|a+b| \leq |a| + |b|$
für alle $a,b \in K$.

$$|a-b| = |a-c + c -b| \leq |a-c| + |c-b|$$

---

Ist $K$ Archimedisch und $x\in K$ mit $-1 < x < 1$, dann gilt 
$$\lim_{n\to\infty} x^n = 0$$


---

Sei $(a_n)$ eine Folge in einem [Archimedischen Koerper](Körper.md#Archimedisch). Gibt es ein $0 < \lambda < 1$ mit $$|a_{n+1} - a_n| \leq \lambda|a_n -a_{n-1}|$$
für alle $n$, so ist $(a_n)$ eine Cauchyfolge.

---

Die harmonische Reihe
$$\sum\limits^{\infty}_{n=1} \frac{1}{n}$$
ist [bestimmt Divergent](Bestimmt%20Divergent.md) gegen $\infty$.

Für $|x| < 1$ konvergiert die geometrische [Reihe](Reihe.md) und
$$\sum^{\infty}_{n_0} x_n = {1 \over 1 -x}$$
Die Exponentialreihe
$$\sum\limits^{\infty}_{n=0} \frac{1}{n!} x^{n}$$
ist für jedes $x\in\mathbb R$ konvergent

---
