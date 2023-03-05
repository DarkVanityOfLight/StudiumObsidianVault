Sei $R$ ein kommutativer [Ring](Ring.md) mit $1$. Jede [Untergruppe](Untergruppe.md) $I\subset (R, +)$ ist ein [Normalteiler](Normalteiler.md), wir können also die Quotientengruppe $R/I$ bilden und der [surjektive](Surjektiv.md) [Gruppenhomomorphismus](Gruppenhomomorphismus.md)
$$\begin{align*}
\pi: &(R, +) &\to& (R/I, +)\\
&r &\mapsto& \overline r = r+I
\end{align*}$$

hat $Ker \pi = I$ und das neutrale Element von $R/I$ bezüglich $+$ ist $0 + I = I$.
Wollen wir auch eine Multiplikation auf $R/I$, sodass $\pi$ ein [Ringhomomorphismus](Ringhomomorphismus.md) ist, dann muss die Multiplikation von der Multiplikation in $R$ induziert sein, denn
$$\overline r_{1} \cdot \overline r_{2} = \pi(r_{1}) = \pi(r_{1} r_{2}) = \overline {r_{1}r_{2}}$$
Im Allgemeinen wird die repraesentantenweise Multiplikation jedoch nicht wohldefiniert sein. Ist $r'_{2} =r_{2} + b$ mit $b\in I$ ein anderer Repräsentant von $r_{2} + I$, dann gilt
$$r_{1} \cdot r_{2}' = r_{1}\cdot r_{2}+ r_{1}\cdot b$$
es sollte also $r_{1}\cdot b \in I$ sein für alle $r_{1}\in R$ und $b\in I$. [Untergruppen](Untergruppe.md) von $(R, +)$ mit dieser Eigenschaften nennt man Ideale.

## Ideale

Sei $R$ ein kommutativer [Ring](Ring.md) mit $1$. Ein __Ideal__ ist eine nicht leere Teilmenge $I\subset R$ mit 
$$\begin{align*}
a + b \in I\\
ra \in I
\end{align*}$$
für alle $a, b \in I$ und $r\in R$

Wir bemerken, dass mit $a\in I$ auch das additiv Inverse $-a \in I$ ist.


Sei $I\subset R$ ein Ideal. Dann trägt die Quotientengruppe $R/I$ die Struktur eines kommutativen [Rings](Ring.md) mit $1$ mit repräsentantenweiser Multiplikation
$$(r_{1} + I) \cdot (r_{2} + I) := r_{1}r_{2} + I$$
Das neutrale Element von $R/I$ bezüglich $\cdot$ ist $1+I$. Wir bezeichnen $R/I$ als __Quotientenring__ von $R$ nach $I$