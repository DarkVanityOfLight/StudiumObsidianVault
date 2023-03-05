[Gruppen](Gruppe.md) werden in der Mathematik betrachtet, da sie als [Mengen](Mengen.md)  von Symmetrien von Objekten auftauchen. Um Symmetriegruppen einzuführen, verwenden wir die Notation einer Operation.

Sei $(G, \circ)$ eine [Gruppe](Gruppe.md) und $M$ eine [Menge](Mengen.md). Eine __Operation__ von $G$ auf $M$ (von links) ist eine Abbildung
$$\begin{align}
\cdot :& G \times M \to M\\
& (g, m) \mapsto g \cdot m
\end{align}$$
die folgenden Bedingung erfüllt: 
1) $e\cdot m = m$ für alle $m\in M$.
2) $(a\circ b)\cdot m =  a \cdot (b\cdot m)$ für alle $a, b \in G$ und $m\in M$.

Analog kann man auch Operationen von rechts
$$\begin{align}
\cdot :& M \times G \to M\\
& (m, g) \mapsto m\cdot g
\end{align}$$
betrachten mit $m\cdot e$ und $(m \cdot a)\cdot b = m \cdot (a\cdot b)$. Es scheint erst einmal überflüssig beide Notationen zu haben, jedoch gibt es Situationen, bei der es zwei unterschiedliche kanonsiche Definition für eine Operation gibt. Ein Beispiel ist die Operation einer [Untergruppe](Gruppe.md#Untergruppenkriterium) $H \subset G$ von auf $G$ durch $H \times G \to G$, $(h, g) \mapsto h \circ g$ von links und $G \times H, (g, h) \mapsto g \circ h$ von rechts.

---

Anders formuliert ist eine Operation von $G$ auf $M$ ein [Gruppenhomomorphismus](Gruppenhomomorphismus.md) 
$$\begin{align}
\varphi:& G \to S(M)\\
&g \mapsto \varphi(g) := \left(\begin{array}{cc} M \to M \\ m \mapsto g \cdot m\end{array}\right)
\end{align}$$
von $G$ in die Gruppe der Selbstabbildung von $M$.
