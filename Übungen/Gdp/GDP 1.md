## Aufgabe 3
a)
$$\overline{one \Downarrow 1}$$ 
$$\overline{two \Downarrow 2}$$
$$\overline{nil \Downarrow 0}$$
$$e_1 \Downarrow n_1 \qquad e_2 \Downarrow n_2 \over
cons(e_1, e_2) \Downarrow n_1 + 2\cdot n_2$$

b)
Da wir zu Beginn nicht wissen, wie viele Stellen die Zahl haben wird, kenne wir den Wert des Größten Exponenten nicht.

c)
$$\begin{align}
a \in \text{Aussage} ::= &ds\Downarrow \mathbb N \\\
&|d\Downarrow\mathbb N\\
&|len(ds) \sim \mathbb N
\end{align}$$

$$\over len(nil) \sim 0$$ 
$$len(ds) \sim n \over len\, cons(d, ds) \sim n+1$$

$$
len(ds) \sim n \qquad d\Downarrow n_1 \qquad ds\Downarrow n_2 \over cons(d, ds) \Downarrow2^n \cdot n_1 + n_2
$$


## Aufgabe 4

$\phi_1, \phi_1 = \{Flecki \mapsto Heu, Fred \mapsto Heu, Hoppel \mapsto Drops\}$
$\phi_2, \phi_2 = \{Blacki \mapsto Salat, Flecki \mapsto Moehren, Max \mapsto Gras, Moritz \mapsto Heu\}$

---
$\phi_1, \phi_2 = \{Flecki \mapsto Moehren, Fred \mapsto Heu, Hoppel \mapsto Drops, Blacki \mapsto Salat, Max\mapsto Gras, Moritz \mapsto Heu\}$
 $\phi_2, \phi_1 = \{Flecki \mapsto Heu, Fred \mapsto Heu, Hoppel \mapsto Drops, Blacki \mapsto Salat, Max\mapsto Gras, Moritz \mapsto Heu\}$
 ---
$$\begin{align}
\phi_1, \{Hoppel \mapsto Sticks\}, \phi_2 =& \{Flecki \mapsto Moehren, Fred \mapsto Heu,\\
&Hoppel \mapsto Sticks, Blacki \mapsto Salat,\\
&Max\mapsto Gras, Moritz \mapsto Heu\}
\end{align}$$

---

$\phi_1 - \{Max,Moritz\} = \{Flecki \mapsto Heu, Fred \mapsto Heu, Hoppel \mapsto Drops\}$
$\phi_2 - \{Max, Moritz\} = \{Blacki \mapsto Salat, Flecki \mapsto Moehren\}$

---

$(\phi_1, \phi_2) - \{Max, Moritz\} = \{Flecki \mapsto Moehren, Fred \mapsto Heu, Hoppel \mapsto Drops, Blacki \mapsto Salat\}$
$\phi_1, (\phi_2 - \{Max, Moritz\}) = \{Flecki \mapsto Moehren, Fred \mapsto Heu, Hoppel \mapsto Drops, Blacki \mapsto Salat\}$

---

$(\phi_1, \phi_2) - \{Fred, Moritz\} = \{Flecki \mapsto Moehren, Hoppel \mapsto Drops, Blacki \mapsto Salat, Max\mapsto Gras\}$
$\phi_1, (\phi_2 - \{Fred, Moritz\}) = \{Blacki \mapsto Salat, Flecki \mapsto Moehren, Max\mapsto Gras, Fred \mapsto Heu, Hoppel \mapsto Drops\}$

---





