Sei $E$ eine  [Teilmenge](Teilmengen.md) einer [Gruppe](Gruppe.md) $G$. Dann ist $\langle E \rangle$ die kleinste Untergruppe von $G$. Die alle Elemente von $E$ enthält. [Äquivalent](Aussagen.md#Äquivalenz) ist $\langle E\rangle$ der Durchschnitt aller Untergruppen $U$ mit $E \subset U \subset G$(denn der Durchschnitt von [Untergruppen](Gruppe.md#Untergruppenkriterium) ist wiederum eine Untergruppe). Wir nennen $\langle E \rangle$ die von $E$ erzeugte Untergruppe von G. 

## Zyklisch
Eine Gruppe $G$ heißt __zyklisch__, wenn es ein $g\in G$ gibt mit $$G  = \langle g\rangle$$
Für $g\in G$ ist offenbar
$$\langle g\rangle = \{g^{r} | r \in \mathbb Z\}$$
mit 
$$g^{r} = \underbrace{g\circ g}_{r}$$
$g^r = (g^{-1})^{-r}$ Für $r<0$. Bei einer additiven Verknüpfung $+$ schreiben wir intuitiver $r \cdot g$ statt $g^{r}$.

### Beispiel
Die Restklasssengruppe $\mathbb Z \setminus n$ wird zyklisch von $\overline 1$ erzeugt.

Die Gruppe $(\mathbb Z, +)$ ist zyklisch von $1$ erzeugt.
Die Untergruppe $n\mathbb Z \subset (\mathbb Z, +)$ wird zyklisch erzeugt von $n$, also $n\mathbb Z = \langle n\rangle$. Für $n \not = 0$ gilt dass $n\mathbb Z \cong \mathbb Z$.

---

## Ordnung
Sei $g\in G$ ein Element einer Gruppe. Dann heißt $\text{ord}(g) = |\langle g\rangle|$ die Ordnung von $g$.

## Beispiel

Für die Drehung des Tetraeders um $120^{\circ}$ 
$$\sigma = \left(\begin{array}{} 1 & 2& 3 & 4\\1 & 3 & 4& 2\end{array}\right)$$
erhalten wir 
$$\langle \sigma \rangle = \lbrace id = \sigma^{0}, \sigma^{1}, \sigma^{2} \rbrace \cong \mathbb Z/3$$
und somit $ord(\sigma) = 3$
