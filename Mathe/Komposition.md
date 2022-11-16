Seien $f: M\to N$  und $g: N \to L$ Abbildungen, dann ist die Komposition von __g nach f__ definiert als
$$
\begin{align}
g \circ f:& M\to L\\
& m\mapsto g(f(m))
\end{align}
$$

## Beispiel
Die Komposition $g \circ f$ von
$$\begin{align}
&f: \mathbb R \to \mathbb R, x \mapsto x+1\\
&g: \mathbb R \to \mathbb R, x \mapsto x^2
\end{align}$$
gibt
$$
g \circ f: \mathbb R\to \mathbb R, x \mapsto(x+1)^2 = x^2+2x +1
$$
---
Die Komposition von [Abbildungen](Abbildungen.md) ist [assoziativ](Assoziativgesetz.md), das heißt für [Abbildungen](Abbildungen.md) 
$$
M \overset{f}{\to} N \overset{g}{\to} L \overset{h}{\to} K
$$
gilt
$$
h \circ(g\circ f) = (h \circ g)\circ f
$$
#übung

