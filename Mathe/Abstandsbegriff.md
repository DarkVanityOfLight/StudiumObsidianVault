Erinnern wir uns zunächst an unseren Begriff des [Konvergenz](Konvergenz.md) einer Folge $(a_{n})$ in $\mathbb R$: Diese heißt konvergent gegen den Grenzwert $a\in\mathbb R$, wenn es zu jedem $\varepsilon \in\mathbb R$ mit $\varepsilon > 0$ ein $N\in\mathbb N$ gibt mit
$$|a_{n} - a| < \varepsilon\;\text{für alle} n\ge N$$

Die Definition hatten wir uns als Spiel vorgestellt:
1. Spieler A gibt ein beliebiges $\varepsilon >0$ vor.
2. Spieler B muss dann ein $N$ finden, sodass der Abstand von $a_N$ zu $a$ kleiner ist als $\varepsilon$, und auch alle weiteren Folgeglieder innerhalb dieses Abstands bleiben.


Die [Folge](Mathe/Folgen.md) ist [konvergent](Konvergenz.md) gegen $a$, wenn Spieler B immer gewinnt.
Können wir den Abstandsbegriff von zwei Punkten $a,b \in\mathbb R$ durch den Absolutbetrag der Differenz
$$|a-b|$$
realisiert war, auf $\mathbb R^{n}$ übertragen, dann überträgt sich auch der Konververgenzbegriff.

## Norm
Sei $X$ ein [k-Vektorraum](k-Vektorraum.md). Eine [Abbildung](Abbildungen.md)
$$\lVert - \rVert : X \to\mathbb R_{\ge0}$$
heißt Norm, wenn gilt

1. $\lVert x \rVert = 0 \iff x = 0$
2. $\lVert\lambda x\rVert = |\lambda| \cdot \lVert x \rVert$(Homogenität)
3. $\lVert x+y \rVert \le \lVert x \rVert + \lVert y\rVert$ ([Dreiecksungleichung](Dreiecksungleichung.md))

für alle $x, y\in X$ und $\lambda \in K$. Wir bezeichnen dann $(X, \lVert - \rVert)$
als einen __normierten Raum__.

---

Sei $(X, \lVert - \rVert)$ ein normierter Raum. Wir sagen, dass die [Folge](Mathe/Folgen.md) $(x_{n})$ in $X$ gegen $x\in X$ [konvergiert](Konvergenz.md), wenn
$$\lim_{n\to\infty} \lVert  x_{n}- x\rVert = 0$$
und schreiben
$$\lim_{n\to\infty} x_{n} = x$$

---

Für Grenzwertbetrachtungen spielt es keine Rolle, ob wir die Maximumsnorm oder die Euklidische Norm auf $\mathbb R^{n}$ verwenden, denn

$$\lVert x \rVert_{\infty} \le \lVert x \rVert_{2} \le \sqrt{n} \lVert x \rVert_{\infty}$$

---

Eine [Folge](Mathe/Folgen.md) $(x_{k})$ in $\mathbb R^{n}$ mit Koordinaten
$$x_{k} = \left(\begin{array}{}x_{k,1} \\ \vdots \\ x_{k,n}\end{array}\right)$$
konvergiert genau dann gegen ^aa3f99
$$
a = \left(\begin{array}{}a_{1} \\ \vdots \\ a_{n}\end{array}\right)
$$

wenn 
$$\lim_{n\to\infty} x_{k,j} = a_{j}$$
für alle $j$.

