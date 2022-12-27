Ein Gruppenhomomorphismus $\varphi$ zwischen zwei Gruppen $G_1$ und $G_2$ ist eine Abbildung 
$$\varphi: G_1 \to G_2$$
die
$$\varphi(a\circ b) = \varphi(a) \circ \varphi (b) \quad \forall a, b \in G_1$$
erfüllt, als doe Verknüpfungsstruktur erhält.

Man beachte, dass $\circ$ auf der linken Seite die Verknüpfung in $G_1$, auf der rechten Seite die in $G_2$ bezeichnet.

## Kern
Ist $\varphi G_1 \to G_2$ ein Gruppenhomomorphismus, so gilt 
$$\varphi(e_1) = e_2$$
wobei $e_i \in G_i$ jeweils das neutrale Element bezeichnet
Der __Kern__ von $\varphi$ $$\text{Ker}\varphi = \{a \in G_1 | 
\varphi(a) = e_2\}$$
## Bild
Das Bild von $\varphi$
$$\text{Bild} \varphi = \varphi(G_1)$$

Der Kern und das Bild sind [Untergruppen](Gruppe.md#Untergruppenkriterium) von $G_1$ bzw. $G_2$.

## [Injektiv](Injektiv.md)
Ein Gruppenhomomorphismus $\varphi: G_1 \to G_2$  ist injektiv genau dann, wenn
$$\text{Ker} \varphi = \{e_1\}$$dh. der Kern nur das neutrale Element $e_1$ von $G_1$ enthält.

