
Die [Exponentialfunktion](Exponentialfunktion.md) und der [Logarithmus](Logarithmusfunktion.md) spielen eine wichtige Rolle bei der Klassifizierung der Laufzeit von Algorithmen. Als __Laufzeit__ eines Algorithmus bezeichnen wir die Anzahl der Operationen, die vom Prozessor in einem Taktzyklus abgehandelt werden z.B. Addition, Multiplikation und [Division mit Rest](Division%20mit%20Rest.md). Diese wird typischerweise als Funktion in der Bitgröße des Inputs angegeben.

## Beispiel
Wie gross ist der Rechenaufwand für die Schulbuchmultiplikation von zwei Binärzahlen, $a, b$ der Bitlänge $n$ und wie verhält sich dieser für große $n$? Zur Multiplikation der $n=4$ Bitzahlen $a=(0,1, 0, 1) = 5$ und $b = (0,1,1,1) = 7$ berechnen wir also $a\cdot b = (0,1,0,0,0, 1, 1) = 35$. Die Rechnung benötigt allgemein maximal
$$l_{n} := 2n(n-1)$$
Bitadditionen. Induktiv addieren wir in jedem Schritt eine Zeile zu der Summe der darunterliegenden Zeilen. In jedem der $n-1$ Schritte benötigen wir maximal $n$ Additionen für die $n$ Stellen der zu addierenden Zeile(man beachte, dass auch die erste Stelle eine Addition hervorrufen kann, wenn darunter ein Übertrag steht), und maximal $n$ Additionen für den Übertrag, beginnend an der zweiten Stelle der zu addierenden Zeile.

Es gibt wesentlich schnellere Multiplikationsverfahren (z.B. den Karatsuba Algorithmus oder den Schoenhage-Strassen-Algorithmus). Was heißt aber schneller?

---

Die Laufzeit $l_{n}$ eines Algorithmus lässt sich oft nicht exakt bestimmen, sondern nur nach oben abschätzen. Um die Laufzeit grob einzuteilen können wir das Verhalten für große $n$ betrachten. Die folgende Definition erlaubt es uns, für eine gegebene Funktion $g: ]0, \infty[\to\mathbb R$ eine obere Schranke für das Wachstum von $g(x)$ für $x\to\infty$ anzugeben:

Für $f: ]0,\infty[\to\mathbb R$ sei
$$O(f) = \lbrace g: ]0, \infty[\to\mathbb R |\exists c, x_{0} \in\mathbb R\;\text{mit}\; |g(x)| \le c \cdot |f(x)| \forall x \ge x_0\rbrace$$
Statt $g\in O(f)$ schreibt man in der __Landau-Notation__ auch $g = O(f)$.

## Beispiel

$2x^{4} + 5x^{3} - 2 \in O(x^{4})$ denn $|2x^{4} + 5x^{3}-2 |\le 9\cdot |x^{4}|$ für $x\ge 1$

---
Insbesondere wenn
$$
\lim_{x\to\infty} \frac{g(x)}{f(x)}
$$
existiert und endlich ist, dann gilt $g\in O(f)$

## Beipiel

Die Schulbuchmultiplikation hat Laufzeit in $O(n^{2})$ denn
$$\lim_{n\to\infty} \frac{2n(n-1)}{n^{2}} = \lim_{n\to\infty}\left(2\frac{2}{n}\right)= 2 <\infty$$
