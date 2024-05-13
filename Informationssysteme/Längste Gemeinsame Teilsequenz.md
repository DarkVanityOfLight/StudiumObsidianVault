
Eine Teilsequenz ist eine Sequenz, die von einer anderen Sequenz durch weglassen von Zeichen aber unter Beibehaltung der Reihenfolge der Zeichen entsteht.
Eine gemeinsame Teilsequenz zweier Strings $x$ und $y$ ist ein String $s$ sodass alle Zeichen von $s$ in $x$ und $y$ in der gleichen Reihenfolge auftreten (aber eben nicht notwendigerweise zusammenhängend)

## Längste-Gemeinsame-Teilsequenz-Distanz
$$d(x, y) = \max(|x|, |y|) - \max_{s\in S(x, y)}|s|$$
wobei $S(x, y)$ die Menge aller gemeinsamen Teilsequenzen von $x$ und $y$ ist.

