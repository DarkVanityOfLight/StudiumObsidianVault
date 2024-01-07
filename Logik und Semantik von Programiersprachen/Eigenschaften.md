Sei $\sigma$ eine [Signatur](Mathe/Signatur.md). Eine __Eigenschaft__ $P$ ist eine Teilmenge von $\sigma$-Strukturen: $P\subseteq STRUCT(\sigma)$

## Beispiele
Betrachten wir die Graphensignatur $\sigma = \lbrace E\rbrace$

- Die Menge aller endlichen [Graphen](Algorithmen%20und%20Datenstrukturen/Graph.md)(endlichkeit)
- Die Menge aller [Zusammenhaengenden Graphen](Algorithmen%20und%20Datenstrukturen/Graph.md#Zusammenhang)(Zusammenhang)
- Die Menge aller Bipartiten Graphen
- Die Menge aller Graphen mit [[Hamiltonpfad]]


## Ausdrückbarkeit der Eigenschaften

für einen [Satz](Satz.md) $\varphi$, definiere 
$$Mod(\varphi) := \lbrace \mathcal A : \mathcal A \vDash \varphi\rbrace$$


>[!DEFINITIOn]
>Eine Eigenschaft $P$ ist __elementar__, wenn $P = Mod(\varphi)$ für einen bestimmten FO-Satz $\varphi$ gilt.


Ein Alternativer Begriff zu elementar ist endlich axiomatisierbar(in FO), FO-ausdrückbar, FO-beschreibbar.

>[!DEFINITION] 
>Eine Eigenschaft $P$ ist __erweitert elementar__, wenn $P = Mod(\phi)$ für eine bestimmte Formelmenge $\phi$ gilt.

## Endlichkeit ist nicht elementar

Angenommen: Endlichkeit ist anhand von der Formel $\varphi$ beschreibbar.
Sei $\lambda_k$ ein [Satz](Satz.md), der beschreibt, dass es $\ge k$ Elemente im Universum gibt. Wir betrachten die [Theorie](Theorien%20der%20ersten%20Stufe.md)
$$T := \lbrace \varphi\rbrace \cup \lbrace \lambda_k : k \ge 1\rbrace$$
Einerseits hat $T$ entweder ein unendliches oder ein endliches Modell.

Anderseits enthält jede endliche Teilmenge von $T$ nur endlich viele Sätze der Art $\lambda_K$, d.h. sie hat ein endliches Modell.

Durch den [Kompaktheitssatz der Prädikatenlogik](Kompaktheitssatz%20der%20Prädikatenlogik.md) hat $T$ ein Modell. Dies ist ein Widerspruch!

### Intuition

$\varphi$ stellt sicher das das [Modell](Modell.md) endlich bleibt. Nun erstellen wir unsere Formel mithilfe der $\lambda_k$ Terme, diese sagen aus das es $\ge k$ Elemente gibt. Nun gibt es ein Modell für jede beliebige endliche Teilmenge.Da wir für jedes $k$, eine endliche Menge an Zahlen finden sodass es mehr als $k$ Zahlen gibt. Nach dem Kompaktheitssatz gibt es ein unendliches Modell, wenn jede endliche Teilmenge erfüllbar ist, dies ist hier der Fall. Da das Modell durch $\varphi$ aber endlich gehalten wird, gibt es einen Widerspruch, der Kompaktheitssatz sagt es gibt ein unendliches Modell, jedoch besagt $\varphi$ das dies nicht der Fall sein kann.


### Beispiel I
Graphen-Zusammenhang ist nicht elementar

Angenommen der Zusammenhang ist anhand von $\varphi$ beschreibbar.
Sei $\sigma' = \lbrace E^2, a, b\rbrace$
Sei $\lambda_k$ die folgende $\sigma'$-Formel

$$\neg (\exists x_1, \dots, x_k(E(a, x_1), \land E(x_1, x_2) \land \dots \land E(x_{k-1}, x_k) \land E(x_k, b)))$$
Wir definieren die Theorie
$$T := \lbrace \varphi \rbrace \cup \lbrace \lambda_k : k \ge 1\rbrace \cup \lbrace a \not = b, \neg E(a, b)\rbrace$$

Einerseits ergibt sich durch Kompaktheit ein Modell für $T$.
Anderseits kann $T$ kein Model besitzen, weil $\varphi$ die Existenz eines endlichen Pfad von $a$ zu $b$ auferlegt.