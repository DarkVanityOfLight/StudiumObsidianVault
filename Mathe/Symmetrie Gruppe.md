Wir beschreiben die Symmetriegruppe $Sym(D)$ des Gleichseitigen Dreiecks $D$.
Jede Symmetrie ist eine Drehung oder Spiegelung.

Jede Symmtetrie ist eindeutig druch ihre Wirkung auf den Ecken festgelegt. Durch Nummerieren der Ecken koennen wir also jedes Element als eine bijektive Abbildung $\lbrace 1, 2, 3\rbrace \to\lbrace 1, 2, 3\rbrace$ auffassen.
Genauer haben wir einen [Gruppenisomorphismus](Isomorphismen.md) auf $\varphi$.

![symmetrie](symmetrie.png)

Dieser wird induziert durch die Operation von $Sym(D)$ auf den Ecken des Dreiecks
$$Sym(D) \times \lbrace 1, 2, 3\rbrace \to \lbrace 1, 2, 3\rbrace$$
Bezeichnet etwa die Drehung um $120^{\circ}$, dann gibt die Operation die Zuordung
$$(r_{120}, 1) \mapsto 2, (r_{120}, 2) \mapsto 3, (r_{120}, 3) \mapsto 1$$
also 
$$\varphi (r_{120}) = \left(\begin{array}{}1 & 2& 3\\2 & 3& 1\end{array}\right)$$
