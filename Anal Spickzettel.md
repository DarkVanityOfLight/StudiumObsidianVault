
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

