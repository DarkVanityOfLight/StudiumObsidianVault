Mit dem [unendlichen Dezimalbruch](Unendlicher%20Dezimalbruch.md) haben wir schein eine Klasse von [Folgen](Folgen.md) $(a_n)$ kennengelernt, bei der man $a_n$ aus $a_{n-1}$ durch Addition einer Konstanten $b_n$ erhält.

Allgemein können wir [Folgen](Folgen.md) $(a_n)$  der Form $$a_n = b_1 + ... + b_n = \sum^{n}_{i=1} b_i$$
mit einer gegebenen [Folge](Folgen.md) $(b_n)$ betrachten. Solche [Folgen](Folgen.md) $(a_n)$ bezeichnet man als Reihen.
Natürlich lässt sich jede beliebige [Folge](Folgen.md) mittels einer Teleskop summe in dieser Form schreiben
$$a_n = \underbrace{a_1}_{b_1} + \underbrace{(a_2 - a_1)}_{b_2} + \underbrace{(a_3 -a_2)}_{b_3} + ... + \underbrace{(a_n - a_{n-1})}_{b_n}$$
allerdings gibt es Beispiele, bei denen diese Schreibweise eben auf natürliche Weise auftritt, etwa die [unendlicher Dezimalbrüche](Unendlicher%20Dezimalbruch.md)
$$a_n = \sum_{i = 1}^{n} 10^k s_i \cdot \left(1\over 10\right)^i$$
mit $s_i \in \{0, ..., 9\}$.
In einer unendlichen Dezimalbruchentwicklung einer [reellen Zahl](Reelle%20Zahlen.md) könnte man statt $1\over 10$ auch andere Zahlen $x$ einsetzten, d.h. Grenzwerte $\sum^{\infty}_{i=10} 10^k s_i \cdot x^i$ betrachten. Allgemeiner erhalten wir für jede gegebene Folge $(c_i)$ eine Abbildung
$$x \mapsto \sum^{\infty}_{i=0} c_i \cdot x^i$$
wobei diese für alle jene $x$ definiert ist, für die der Grenzwert existiert. 

Ein entscheidender Vorteil dieser Darstellung von Funktionen ist die leichte Implementierbarkeit grundlegender Operation im Computer, etwa der Addition, Multiplikation, Ableitung und Integration. Zum Beispiel addieren wir Funktionen in dieser Darstellung durch die Formel 
$$\sum^{\infty}_{i=0} c_i \cdot x^i + \sum^{\infty}_{i=0}d_i \cdot x^i = \sum^{\infty}_{i = 0}(c_i +d_i) \cdot x^i$$

---

Sei $(b_n)$ eine [Folge](Folgen.md) in $\mathbb R$. Die Folge $(a_k)$ mit $$a_k = \sum^{k}_{n=1} b_n$$
heißt Reihe der Partialsummen von $(b_n)$ und wird mit $\sum^{\infty}_{n=1}b_n$
bezeichnet.  Im Falle der [Konvergenz](Konvergenz.md) oder [bestimmte Divergenz](Bestimmt%20Divergent.md) von $(a_n)$ verwenden wir diese Bezeichnung auch für den Grenzwert
$$\sum^{\infty}_{n=1} b_n$$
Wie bei Listen in vielen Programmiersprachen ist es oft nützlich, die Indizierung bei $0$ zu beginnen.

## Konvergenz
Die Reihe $\sum^{\infty}_{n=1}b_n$ ist also [konvergent](Konvergenz.md) gegen $a\in \mathbb R$, wenn es zu jedem $\epsilon > 0$ ein $N$ gibt mit $$\left|\sum^{k}_{n=1} b_n -a\right| < \epsilon \forall k\geq N$$
Weglassen von endlich vielen Summanden ändert nichts an der Konvergezeigenschaft, insbesondere Weglassen der ersten $n_0$ Summanden, d.h

$$\sum^{\infty}_{n_1} b_n \text{konvergent} \iff \sum^{\infty}_{n = n_0} b_n \text{konvergent}$$
Der Grenzwert wird sich aber typischerweise um eine Konstante ändern, denn
$$\sum^{\infty}_{n=1} b_n = \sum^{n_0 - 1}_{n_1} b_n + \sum^{\infty}_{n = n_0} b_n$$