Sei 
$$A = \lbrace \alpha, \beta, \gamma \rbrace$$
eine endliche Menge. Ein __Wort__ über dem Alphabet $A$ ist eine endliche [Folge](Mathe/Folgen.md)
$$w = b_{1} b_{2}...b_{n}$$
mit $b_{i} \in A$. Gegeben ein weiteres Wort $v = a_{1} ... a_{m}$, definiert man die Verknüpfung "Hintereinander schreiben" durch
$$w \circ v = b_{1} ... b_{n} a_{1}...a_{m}$$
Die Menge 
$$G = \lbrace w | w \text{ ein Wort ueber A } \rbrace$$
zusammen mit $\circ$ bildet eine [Halbgruppe](Gruppe.md#Halbgruppe).
Erlauben wir in $G$ auch das leere Wort $e$, dann wir $(G, \circ)$ zu einem  [Monoid](Gruppe.md#Monoid)

Fügen wir zusätzlich Buchstaben $\alpha^{-1}, \beta^{-1},...$ mit der Rechenregel
$$\alpha \alpha^{-1} = \alpha^{-1} \alpha = e$$
hinzu, dann erhalten wir die __freie Gruppe__ erzeugt von $A$.
