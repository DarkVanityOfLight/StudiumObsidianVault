Seien $R$ und $S$ [Ringe](Ring.md). Ein __Ringhomomorphismus__ 
$$\varphi: R\to S$$
ist eine [Abbildung](Abbildungen.md), die
$$\varphi(a+b) = \varphi(a) + \varphi(b)$$
und
$$\varphi(a\cdot b) = \varphi(a) \cdot \varphi(b)$$
für alle $a, b \in R$ erfüllt (insbesondere ist $\varphi: (R,+) \to (S, +)$, ein [Gruppenhomomorphismus](Gruppenhomomorphismus.md)). Sind $R$ und $S$ Ringe mit $1$ so verlangen wir in der Regel außerdem
$$\varphi(1_{R}) = 1_{S}$$
Die Begriffe Mono-, Epi- und Isomorphismus werden analog wie bei Gruppen verwendet.

---

Das Bild von $\varphi(R) \subset S$ ist ein Unterring, ebenso der Kern

$$Ker\;\varphi = \lbrace r\in R | \varphi(r) = 0\rbrace \subset R$$

Für einen Ring $R$ mit $1$ ist $Ker\;\varphi$ ein Ring mit $1$ nur in dem Spezialfall der Nullabbildung