
In der multivariaten Analysis betrachten wir statt Funktionen
$$f: D\to\mathbb  R$$
mit $D\subset \mathbb R$, nun Funktionen der Form
$$f: D\to\mathbb R^{m}$$
mit $D\subset\mathbb R^{n}$, d.h. wir erlauben sowohl im Quellbereich als auch im Zielbereich mehr als eine Koordinate. Interessante geometrische Objekte entstehen zum Beispiel als Raumkurven, die man als Bild einer nicht konstanten Abbildung $f$ mit $n=1$ und $m=3$ erhält.

$$\begin{align*}
f&: \mathbb R \to \mathbb R^{3}\\
f(t) &= \left(\begin{array}{}
\frac{t^{4} - 6t^{2} + 1}{(1+t^{2})^{2}}\\
\frac{-t(-2+t)}{1+t^{2}}\\
\frac{t^{2}(t^{4}-6t^{2} + 9)}{(1+t^{2})^3}
\end{array}\right)
\end{align*}$$

Die [Funktion](Mathe/Funktionen.md) $f$ ist gegeben durch ein Tupel aus $3$ [rationalen](Rationale%20Zahlen.md) Funktionen die die drei Raumkoordinaten der Punkte der Kurve beschreiben.

---

Objekte die als [Bild](Mathe/Funktionen.md#Bild) einer [Funktion](Mathe/Funktionen.md) gegeben sind (man sagt auch parametrisch) und Objekte die als Nullstellen menge einer Funktion gegeben sind also durch eine Gleichung (man sagt auch implizit).
Indem man die Nullstellen menge von Abbildungen
$$f: \mathbb R^{3} \to\mathbb R^{2}, x \mapsto (f_{1}(x), f_{2}(x))$$
also die gemeinsame Nullstellen menge von zwei Gleichungen betrachtet, erhält man wieder Kurven.

---

Anwendungen der multivarianten Analysis finden sich z.B. in der geometrischen Modellierung, bei der es um die Darstellung von geometrischen Formen mit Hilfe der Analysis geht. In der Praxis wird die geometrischen Modellierung etwa im Computer Aided Design verwendet, wo z.B. Objekte in industriellen Produktionsprozessen mit Methode der Analysis beschrieben werden, oder bei der Darstellung von Schriften auf dem Computer, die sich in der Größe skalieren lassen.
Viele Konzepte aus dem univarianten Bereich haben ein direktes Analogon,  wie etwa der Begriff der [Stetigkeit](Stetigkeit%20und%20Zwischenwertsatz.md) (sobald man sich klar gemacht hat, wie man Abstände misst).
Bei anderen Begriffen wie der [Differenzierbarkeit](Differenzierbarkeit.md) muss man etwas genauer hinschauen. Hat man dies erstmal verstanden, überträgt sich das Konzept der [Taylor Reihe](Taylor%20Reihe.md) und damit auch die grundlegende Methodik zur Untersuchung von Funktionen auf lokale Extrema. Auch das Konzept der [Umkehrfunktion](Umkehrfunktion.md) und deren [Ableitung](Ableitung.md) überträgt sich.

Wie wir sehen werden gibt es auch eine Beziehung zwischen implizit und parametrisch gegebenen [Mengen](Mengen.md), eine Idee die sich so in der univariaten Analysis nicht wiederfindet: Nullstellenmegnen von univariaten Funktionen $\not = 0$ bestehen typischerweise aus einzelnen Punkten waehrend bei der multivariaten Funktionen man eben auch ein Herz als Nullstellen menge erhalten kann. Im Satz über implizite Funktionen werden wir sehen, wann und wie sich eine implizit durch Gleichungen gegebene Menge durch eine Parametrisierung also als Bild einer [Abbildung](Abbildungen.md) beschreiben lässt.