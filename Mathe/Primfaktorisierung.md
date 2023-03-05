
## Probedivision
Sei $n \in \mathbb N$ zusammengesetzt(nicht Prim). Für den kleinsten Primteiler $p$ von $n$ gilt:
$$P \leq m := \lfloor\sqrt n\rfloor$$

Kennen wir alle Primzahlen $p \leq m$, dann testen wir $p | n$ mit [Division mit Rest](Division%20mit%20Rest.md). Damit können wir eine gegebene Zahl $n$ faktorisieren.


### Beweis
Schreibe $n = p \cdot q$ Dann gilt  $p^2 \leq p \cdot q = n$ also $p \leq \sqrt n$.
Wegen $p\in\mathbb N$ ist also $p\leq \lfloor \sqrt{n}\rfloor$.

### Beispiel
Zum Faktorisieren von $234$ mittels Probedivision testen wir zunächst, ob $n$ durch eine Primzahl $p \leq \lfloor \sqrt{234}\rfloor = 15$ teilbar ist. Wir finden $$
234 = 2 \cdot 117
$$
Ist $117$ nicht prim, so muss ein Primteiler $p\leq \lfloor\sqrt{117}\rfloor = 10$ vorkommen, wir finden $$117 = 3 \cdot 39$$
Ist $39$ nicht prim, so muss ein Primteiler $p \leq \lfloor \sqrt{39} \rfloor = 6$ vorkommen, und wir finden $$39 = 3\cdot 13$$
Schließlich ist $13$ prim, denn 13 ist durch keine Primzahl $p \leq \lfloor \sqrt{13} \rfloor =3$teilbar.
Die Probedivision erlaubt uns auch, alle Primzahlen $\leq n$ induktiv aufzuzählen, denn kennen wir schon alle Primzahlen $p\leq \lfloor \sqrt{n} \rfloor < n$, so können wir durch Faktorisieren entscheiden, ob $n$ prim ist.


## Pollard

Gelingt es uns die Faktorisierung $n= p\cdot q$ zu bestimmen, so erhalten wir $\varphi(n) = (p-1)(q-1)$. Damit können wir aus dem öffentlichen Schlüssel $e$ den privaten Schlüssel $d$ bestimmen und somit jede mit $(n, e)$ verschlüsselte Nachricht mitlesen. Für große Zahlen $n$ ist Probedivision nicht praktikabel. Es gibt wesentlich effizientere Methoden, um einen Primteiler zu finden.

Angenommen ein Primfaktor $p$ von $n$ hat die Eigenschaft, dass $p-1$ nur kleine Primpotenzfaktoren $\le B$ besitzt. Dann laesst sich ein Vielfaches $k$ von $p-1 = \varphi(p)$ bestimmen ohne $p$ zu kennen:
$$k := \prod_{\begin{array}{}q\text{ Primzahl} \\ l \text{ maximal mit } q^{l} \le B\end{array}}$$
Sei nun $1 < a < n$ beliebig gewaehlt. Teste zunaechst, ob $ggT(a, n) = 1$ (wenn nicht, haben wir einen echten Teiler gefunden). Sind $a$ und $n$ teilerfremd, erhalten wir einen Faktor von $n$ als 
$$ggT(a^{k} - 1, n) > 1$$
denn $k$ ist nach Voraussetzung ein Vielfaches von $\varphi(p)$, also $k = k' \cdot \varphi(p)$. Damit gibt der [Kleine Satz von Fermat](Kleiner%20Satz%20von%20Fermat.md)
$$a^{k}= \left(a^{\varphi(p)}\right)^{k'} \equiv 1\mod p$$
also $p|ggT(a^{k} -1, n)$. Falls wir aufgrund der Wahl von $a$ und $B$ keinen echten Teiler finden, ändern wir unsere Wahl.

In dem Algorithmus kann $a^{k}$ modulo $n$ berechnet werden, denn ist $p$ ein Teiler von $a^{k} - 1$ und $n$, dann auch von $a^{k} - 1 + s\cdot n$ für jedes $s$.
