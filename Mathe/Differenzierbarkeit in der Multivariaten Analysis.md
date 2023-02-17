
Eine [Funktion](Mathe/Funktionen.md) $f: D\to\mathbb R$ mit $D\subset \mathbb R$ heißt differenzierbar in $a\in D$, wenn der Grenzwert 
$$f'(a) := \lim_{\begin{array}{}x\to a \\ x\not = a\end{array}} \frac{f(x) -f(a)}{x-a}$$
existiert. Äquivalent können wir dies auch schreiben als
$$f'(a) = \lim_{\begin{array}{}h\to 0 \\ h\not= 0\end{array}} \frac{f(a+h) -f(a)}{h}$$
Legen wir für eine multivariate Funktion $f:D\to\mathbb R^{m}$ mit $D\subset \mathbb R^{n}$ einen Richtungsvektor $h\in\mathbb R^{n}$ fest, erhalten wir aus der univariaten Differenzierbarkeit die Definition einer Richtungsableitung

## Richtungsableitung

Die Funktion $f: D\to\mathbb R^{m}, x\mapsto f(x)$ mit $D\subset \mathbb R^{n}$ heißt __differenzierbar in Richtung__ $h\in\mathbb R^{n}$, wenn
$$D_{h}f(a) := \lim_{\begin{array}{}t\to 0 \\ t\not = 0\end{array}} \frac{f(a+t \cdot h) - f(a)}{t}$$
und $D_{h} f(a) \in\mathbb R^{m}$ heißt die __Richtungsableitung__ von $f$ in Richtung $h$.

1. Der Limes ausdruck bedeutet insbesondere, dass es ein $\varepsilon > 0$ gibt mit $$\lbrace a+ t\cdot h| |t| < \varepsilon\rbrace\subset D$$ also ein Geraden stück durch $a$ in Richtung $h$ liegt im Definitionsbereich von $f$
2. Mittels der univariaten Differenzierbarkeit lässt sich die Differenzierbarkeit in Richtung $h$ ausdrücken als $$D_{h} f(a) = (f(a +t \cdot h))' |t=0'$$ wobei $()'$ für die Ableitung nach $t$ steht und wir jede Komponente von $f$ einzeln ableiten.

3. Wegen dem [konvergenzbegriff in der multivariaten Analysis](Abstandsbegriff.md#^aa3f99) ist $f = (f_{1}, ..., f_{m})$ differenzierbar in Richtung $h$, genau dann wenn jede Komponentenfunktion $f_{i}$ differenzierbar in Richtung $h$ ist für alle $i$


## Partielle Ableitung
Existiert die Richtungsableitung für den i-ten Einheitsvektor $h = e_{i}$, dann heißt $f$ __partiell differenzierbar__ nach $x_{i}$ und wir erhalten als Richtungsableitung die i-te __partielle Ableitung__

$$
\frac{\partial f}{\partial x_{i}}(a) := D_{e_{i}} f(a) = \lim_{\begin{array}{}t\to 0\\ t \not= 0\end{array}} \frac{f(a+t\cdot e_{i}) - f(a)}{t}
$$
wir leiten also $f$ nach der Variable $x_{i}$ ab, wobei wir alle anderen Koordinaten konstant auf $x_{i} = a_{j}$ fuer $j\not = i$ setzen.
Ist $f$ an jedem Punkt $a\in D$ partiell differenzierbar so heißt $f$ partiell differenzierbar und wir erhalten Funktionen $\frac{\partial f}{\partial x_{i}}$

### Beispiel

Für $f(x, y) = x^{3} y^{2}$ ist
$$\begin{align*}
\frac{\partial f}{\partial x} &= 3x^{2} y^{2}\\
\frac{\partial f}{\partial y} &= 2x^{3} y
\end{align*}$$

Zur Bestimmung der Richtungsableitung in Richtung
$$h = \left(\begin{array}{}1\\ 7\end{array}\right)$$
differenzieren wir 
$$f(x + t, y +7t)' = (x + t)^{3} (y +7t)^{2}$$
nach $t$ und erhalten
$$f(x+t, y+7t)' = 3(x+t)^{2} (y+7t)^{2} + 14(x + t)^{2} (y+7t)$$
also für $t=0$ dir Richtungsableitung in Richtung $h$ an der Stelle $(x, y)$
$$D_{h} f = 3x^{2} y^{2} + 14x^{2}+y$$

---

Kann  man aus den partiellen Ableitungen eine Richtungsableitung bezüglich einer beliebigen Richtung bestimmen? Wir werden sehen,  dass dies im allgemeinen nicht funktioniert, unter geeigneten Bedingungen aber schon.
Die Idee einer Ableitung war ja eine Approximation einer Funktion $f: D\to\mathbb R$ mit $D\subset \mathbb R$ durch die affin lineare Funktion
$$f(a) + f'(a) \cdot x$$
die sich in $x=a$ tangential an den Graphen von $f$ legt. Dies gibt uns eine andere Idee, den Begriff der Differenzierbarkeit auf den mehrdimensionalen Fall zu verallgemeinern. Zunächst bemerken wir, dass sich die Differenzierbarkeit von $f$ in $a$ auch im Sinne einer linearen Approximation äquivalent wie folgt schreiben lässt:
Es gibt eine Konstante $f'(a) \in\mathbb R$ sodass
$$\lim_{\begin{array}{}h\to 0 \\ h\not=0\end{array}} \frac{f(a+h) - f(a) -f'(a) \cdot h}{h} = 0$$
Diese Formulierung verallgemeinert sich direkt auf den mehrdimensionalen Fall, nur ist hier eben die lineare Approximation(wir betrachten nur den Teil ohne die Konstante $f(a)$) nicht eine lineare Abbildung
$$\begin{align*}
\mathbb R &\to \mathbb R\\
h &\mapsto f'(a) \cdot h
\end{align*}$$sondern eine lineare Abbildung $\mathbb R^{n} \to \mathbb R^{m}$ also ein $\mathbb R$-[[Vektorraumhomomorphismus]] und somit durch Multiplikation mit einer [[Matrix]] 
$$A\in\mathbb R^{m\times n}$$
gegeben, also
$$\begin{align*}
\mathbb R^{n} &\to\mathbb R^{m}\\
h &\mapsto A\cdot h
\end{align*}$$

## Total Differenzierbar

Die Funktion $f: D\to\mathbb R^{m}$ mit $D\subset \mathbb R^{n}$ heißt __total differenzierbar__, (oder einfach __differenzierbar__) in $a\in D$, wenn sie in einer Umgebung von $a$ definiert ist und $f$ sich linear approximieren lässt, d.h. wenn es eine Matrix $A\in\mathbb R^{m\times n}$ gibt mit
$$\lim_{\begin{array}{}h\to 0 \\ h\not = 0\end{array}} \frac{f(a+h) -f(a) - A\cdot h}{\Vert h \Vert} = 0$$
Für die Matrix $A$ schreiben wir auch
$$D f(a) := A\in \mathbb R^{m\times n}$$
Ist $f$ in jedem $a\in D$ differenzierbar, dann heißt $f$ differenzierbar.

1. In der Definition fordern wir, dass $f$ in einer Umgebung von $a$ definiert ist, d.h. dass es ein $\varepsilon > 0$ gibt mit $$B_\varepsilon (a) = \lbrace x\in\mathbb R^{n} | \Vert x - a\Vert < \varepsilon\rbrace \subset D$$ Damit stellen wir sicher, dass es aus jeder Richtung eine Folge von Punkten in $D$ gibt, die sich annähert und es damit Sinn macht, nach der entsprechenden Richtungsableitung zu fragen.
2. Nach Definition von Konvergenz einer [Folge](Mathe/Folgen.md) gilt für jede [Funktion](Mathe/Funktionen.md) $g$ und jede [Norm](Abstandsbegriff.md#Norm) $\Vert - \Vert$, dass $$\lim_{x\to a} g(x) = 0 \iff \lim_{x\to a} \Vert g(x)\Vert = 0$$ Die Funktion $f$ ist also total differenzierbar genau dann, wenn $$\lim_{\begin{array}{}h\to 0 \\ h\not = 0\end{array}} \frac{\Vert f(a+h) - f(a) -A\cdot h\Vert}{\Vert h\Vert} = 0$$
3. Nach dem [konvergenzbegriff in der multivariaten Analysis](Abstandsbegriff.md#^aa3f99) ist $f = (f_{1}, ..., f_{m}$ total differenzierbar genau dann wenn jedes $f_{i}$ total differenzierbar ist und $Df_{i}(a)$ ist die i-te Zeile von $Df(a)$

---

Was habe die Begriffe der totalen Differenzierbarkeit und der Existenz einer Richtungsableitung miteinander zu tun? Leicht zu beweisen ist:

Ist $f: D\to\mathbb R^{m}$ mit $D\subset \mathbb R^{n}$  total differenzierbar in $a\in D$, dann existieren auch alle Richtungsableitungen und

$$
D_{h} f(a) = Df(a) \cdot h
$$
für $h, a\in\mathbb R^{n}$ (im Sinne der Multiplikation Matrix mal Vektor).

---

Eine Ableitungsmatrix einer total differenzierbaren Funktion ist durch die partiellen Ableitungen bestimmt. In diesem Fall können wir $Df$ also leicht ausrechnen.

> Eine total differenzierbare Funktion ist partiell differenzierbar und $$Df(a) = \left(\frac{\partial f}{\partial x_{1}} (a) |...|\frac{\partial f}{\partial x_{n}}(a)\right)$$

---

> Jede total differenzierbare Funktion ist stetig.

> Sind $f$ und $g$ Funktionen, die total differenzierbar sind und sich zu $f\circ g$ hintereinanderschalten lassen, dann gilt die [Kettenregel](Abbleitungsregeln.md#Kettenregel)
> $$D(f\circ g)(a) = D(f)(g(a)) \cdot Dg(a)$$

---

Es reicht den Fall $f: D\to\mathbb R$ mit $D\subset \mathbb R^{m}$ und $g = (g_{1}, ..., g_{m}) : E\to D$ mit $E\subset\mathbb R^{n}$ zu betrachten. Wir bezeichnen die Koordinaten $\mathbb R^{m}$ mit $y_{j}$ und die Koordinaten in $\mathbb R^{n}$ mit $x_{i}$. Dann besagt die Kettenregel, dass

$$\frac{\partial(f\circ g)}{\partial x_{i}} (a) = \sum\limits^{m}_{j = 1} \frac{\partial f}{\partial y_{j}}(g(a)) \cdot \frac{\partial g_{j}}{\partial x_{i}} (a)$$

## Beispiel

Für die Kugelkoordinatenabbildung
$$\begin{align*}
f: \mathbb R^{3}\to\mathbb R^{3}\\
(r, \theta, \varphi) \mapsto \left(\begin{array}{} r\cdot \sin(\theta) \cdot \cos(\varphi) \\ r\cdot \sin(\theta) \cdot \sin(\varphi)\\r\cdot \cos(\theta)\end{array}\right)
\end{align*}$$
ist
$$
Df = \left(\begin{array}{}
\sin(\theta) \cdot \cos(\varphi) & r\cdot \cos(\theta) \cdot \cos(\varphi) & -r \cdot \sin(\theta) \cdot \sin(\varphi)\\
\sin(\theta) \cdot \sin(\varphi) & r\cdot \cos(\theta) \cdot \sin(\varphi) & r \cdot \sin(\theta) \cdot \cos(\varphi)\\
\cos(\theta) & -r \cdot \sin(\theta)  & 0
\end{array}\right)
$$
Erstaunlicher und mit dem [Mittelwertsatz](Mittelwertsatz.md) nicht schwer zu beweisen ist:

> Eine stetig partiell differenzierbare Funktion ist total differenzierbar.

---

Eine Funktion heißt stetig differenzierbar, wenn sie total differenzierbar ist und $Df$ stetig ist. Dies ist äquivalent dazu, dass all partiellen Ableitungen existieren und stetig sind, d.h. die Funktion stetig partiell differenzierbar ist (und $f$ in einer Umgebung jedes Punktes im Definitionsbereich definiert ist).

---

Iterativ können wir wieder höhere Ableitungen definieren: Ist $f: D \to\mathbb R^{m}$ mit $D\subset\mathbb R^{n}$ differenzierbar, dann erhalten wir eine Ableitungsfunktion $Df: D\to\mathbb R^{m\times n} \cong R^{m\cdot n}$. Ist diese differenzierbar, dann setzen wir
$$D^{k} f = D(D^{k-1} f)$$

Höhere Ableitungen der Ordnung $k$ sind also Arrays mit Einträgen in $\mathbb R$ mit $k+1$ Indizes. Ein solches Objekt bezeichnet man auch als __Multilinearform__. Sie nimmt als Argument $k$ Richtungsvektoren, die hintereinander ausgewertet werden, also
$$\begin{align*}
(D^{k} f) \cdot (v_{1}, ..., v_{k-1}) &= D((D^{k-1} f) \cdot (v_{1},... ,v_{k-1})) \cdot v_{k}\\
&= D_{vk} ... D_{v1} f
\end{align*}$$

