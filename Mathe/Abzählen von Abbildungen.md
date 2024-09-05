
Viele dinge in der Informatik sind im Mathematischen Sinne [Abbildungen](Abbildungen.md).

Die Frage nach der maximalen Anzahl an Abbildungen können wir allgemein beantworten:

> [!SATZ]
> Sind $N$ und $M$ endliche Mengen mit $|N| = n, |M| = m$, dann gibt es genau
> $$m^n$$
> Abbildungen $N\to M$


Wir schreiben kurz $M^N$ für die [Menge](Mengen.md) aller Abbildungen $f: N\to M$.

Für $N = \lbrace x_1, ..., x_n\rbrace$ schreiben wir die Abbildungsvorschrift für $f: N\to M$ auch kurz als
$$f = \begin{pmatrix}x_1 & \dots & x_n \\ f(x_1) & \dots & f(x_n)\end{pmatrix}$$


## Injektive Abbildungen

Wieviele der oben Abgezählten Abbildungen sind [Injektiv](Injektiv.md)?
Anders formuliert auf wieviele Weisen kann man $N$ als [Teilmengen](Teilmengen.md) von $M$ auffassen?

Sind $N$ und $M$ endliche [Mengen](Mengen.md) mit $|N| = n, |M| = m$, dann gibt es

$$\prod^{n-1}_{i=0}(m-i) = m \cdot (m - 1) \cdot ... \cdot (m-n + 1)$$
injektive Abbildungen $N \to M$

## Bijektive Abbildungen

Sind $N$ und $M$ endliche Mengen mit $|N| = |M| = n$, dann gibt es 
$$n!$$
[bijektive](Bijektiv.md) Abbildungen $N\to M$.

Bijektive Abbildungen $M \to M$ bezeichnet man auch als Permutation von $M$. Die Menge der bijektiven Abbildungen 
$$S(M) = \lbrace f: M \to M\text{ bijektiv}\rbrace$$
bildet mit der [Komposition](Mathe/Komposition.md) als Verknuepfung eine [Gruppe](Gruppe.md), denn die Komposition ist [assoziativ](Assoziativgesetz.md).


## Surjektive Abbildungen

Sind $N, M$ endliche Mengen mit $|N| = n, |M| = m$, dann gibt es
$$\sum^{m}_{k=0} (-1)^k \left(m \atop k\right) (m-k)^n$$
[surjektive](Surjektiv.md) Abbildungen $N \to M$.


