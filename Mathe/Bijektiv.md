Wenn die [Abbildungen](Abbildungen.md) [Surjektiv](Surjektiv.md) und [Injektiv](Injektiv.md) ist, ist er Bijektiv
Ist $f: M \to N$ bijektiv dann gibt es für jedes $n \in N$ genau ein $m \in M$
mit $f(m) = n$
$\implies f^{-1}: N \to M, n \mapsto m$ falls $f(m) = n$

$f \text{bij}\iff \exists g: N \to M$ mit $g\circ f = id_M, f \circ g = id_N$
Weiter ist $g=f^{-1}$


### Beispiel
$\forall m\in M$
$f^{-1}(f(m)) = m$
$f^{-1}$ inj Sei $n_1, n_2 \in N$ $f^{-1}(n_1) = f^{-1}(n_2)$
$$\begin{align}
\exists m_1, m_2 \in M: {f(m_1) = n_1 \atop f(m_2)= n_2}
\end{align}$$

$$\begin{align}
&f^{-1} (n_1) = f^{-1}(n_2)\\
&f^{-1}(n_1) = m_1\\
&f^{-1}(n_2) = m_2
\end{align}$$
also $m_1 = m_2 \implies f(m_1) = f(m_2)$ 