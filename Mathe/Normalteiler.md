

Sei $H$ eine Untergruppe von $(G, \circ)$ und
$$G / H = \lbrace gH | g\in G \rbrace$$
die Menge der linken Nebenklassen
$$gH = \lbrace g\circ h\rbrace$$
von $H$, d.h. die Menge der Bahnen der Translationsoperation $G\times H \to G, (g, h) \mapsto g\circ h$ von $H$ auf $G$

---

Sei $$\varphi: G \to F$$
ein [Gruppenhomomorphismus](Gruppenhomomorphismus.md) und 
$$H = Ker(\varphi) \subset G$$
Dann gilt für $g\in G$ und $$gHg^{-1} := \lbrace g \circ h\circ g^{-1} |h\in H \rbrace$$
dass
$$gHg^{-1}= H$$

---

## Normalteiler

Sei $H\subset G$ eine [Untergruppe](Untergruppe.md). $H$ heißt Normalteiler von $G$ (in Zeichen $H \lhd G$), wenn
$$gHg^{-1} = H \quad\forall g\in G$$
(äquivalent ist $gH = Hg \quad \forall g\in G$ oder $gHg^{-1} \subset H\quad\forall g\in G$).

Allgemeiner als das obige Beispiel gilt:

Ist $\varphi: G \to F$ ein [Gruppenhomomorphismus](Gruppenhomomorphismus.md) und $M\subset F$ ein Normalteiler, dann ist $\varphi^{-1}(M) \subset G$ ein Normalteiler. Ist $\varphi$ surjektive und $N\subset G$ ein Normalteiler, dann ist $\varphi(N) \subset F$ ein Normalteiler.

## Quotientengruppe
Sei $H\subset G$ eine [Untergruppe](Untergruppe.md). Die [Menge](Mengen.md) $G\diagup H$ ist genau dann mit der von $G$ induzierten Verknüpfung
$$aH \cdot bH = (a\circ b)H$$
eine [Gruppe](Gruppe.md), wenn $H$ ein [Normalteiler](Normalteiler.md) ist. Wir bezeichnen dann $G\diagup H$ als die Quotientengruppe.

---

Jede Untergruppe $U\subset G$ vom Index $[G:U] = 2$ ist ein Normalteiler von $G$.

