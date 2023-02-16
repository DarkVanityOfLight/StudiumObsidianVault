## Aufgabe 3.1

Auf der einen Seite einer Waage befinden sich $100$ Lebkuchen und $10$ Lebkuchen auf der andere.
Die Waage stellt sich waagerecht, wenn die eine Seite höchstens $1\%$ schwerer als die andere Seite ist. Wir legen nun schrittweise jeweils auf beiden Seiten $1$ Lebkuchen hinzu.

1. Nach wievielen Schritten $n$ steht die Waage zum ersten Mal waagrecht?
2. Sei $a_{n} =100 +n$ und $b_{n}= 10 +n$ Zeigen Sie, dass $$\lim_{n\to\infty} \frac{a_{n}}{b_{n}} = 1$$
---
1. 
$$\begin{align*}
&\frac{10 + n}{1+n}\le 1.01\\
\iff & 10 +n \le 1.01 \cdot(1+n)\\
\iff & 10 +n \le 1.01 + 1.01 \cdot n\\
\iff & 10 - 0.01n \le 1.01\\
\iff & -0.01n \le -8.99\\
\iff & n \ge 899
\end{align*}$$

2. 
$$\begin{align*}
\lim_{n\to\infty} \frac{100 + n}{10+n} &= 1\\
\lim_{n\to\infty} \frac{\frac{100}{n} + \frac{n}{n}}{ \frac{10}{n} + \frac{n}{n}} &= \lim_{n\to\infty} \frac{0 + 1}{0 +1} = 1
\end{align*}$$

## Aufgabe 3.2

Für $n\in\mathbb N$ sei
$$a_{n} = \frac{3n}{2n+1}$$
1. Bestimmen Sie für $m=1$, $m=10$ und $m =100$ jeweils ein $N \in\mathbb N$ mit $$\left|a_{n} - \frac{3}{2}\right| < \frac{1}{m}$$ für alle $n\ge N$.
2. Zeigen Sie, dass $\lim_{n\to\infty} a_{n}= \frac{3}{2}$

---

1. 
Zunächst betrachten wir die Differenz $|a_n - \frac{3}{2}|$: $$\begin{align*} |a_n - \frac{3}{2}| &= \left|\frac{3n}{2n+1} - \frac{3}{2}\right| \\ &= \left|\frac{3n - 3(2n+1)}{2(2n+1)}\right| \\ &= \frac{3}{4n+2}. \end{align*}$$

Für ein gegebenes $m\in\mathbb{N}$ wollen wir ein $N\in\mathbb{N}$ finden, sodass $\frac{3}{4n+2} < \frac{1}{m}$ für alle $n\ge N$. 

$$\begin{align*}
\frac{3}{4n + 2} &< \frac{1}{m}\\
\frac{3m}{4n + 2} &< 1\\
3m &< 4n+2\\
3m -2 &< 4n\\
\frac{3m-2}{4} &< n\\
\end{align*}$$

Für $m=1$ also
$$n > \frac{(3\cdot1)-2}{4} = \frac{1}{4} \implies n = 1$$

Für $m=10$
$$n > \frac{(3\cdot10)-2}{4} = 7 \implies n = 8$$
Und für $m=100$
$$n > \frac{(3\cdot100)-2}{4} = 74 \frac{1}{2}\implies n = 75$$

2. 

$$\begin{align*}
\left|\frac{3n}{2n+1} - \frac{3}{2}\right| &< \epsilon\\
\frac{3}{4n+2} &< \epsilon\\
3 &< \epsilon \cdot (4n + 2)\\
\frac{3}{\epsilon} &< 4n+2\\
\frac{3}{\epsilon} -2 &< 4n\\
\frac{3 - 2\epsilon}{\epsilon} &< 4n\\
\frac{3 -2\epsilon}{4\epsilon} &< n
\end{align*}$$

$$

$$
$$\begin{align*}
\frac{3}{4n+2} &< \frac{3}{4\left(\frac{3-2\epsilon}{4\epsilon}\right)+2} = \frac{3}{\frac{4\cdot(3-2\epsilon)}{4\epsilon} + 2}\\
&= \frac{3}{\frac{3-2\epsilon}{\epsilon} + 2} = \frac{3}{\left(\frac{-2\epsilon}{\epsilon} + \frac{3}{\epsilon}\right)+ 2}\\
&= \frac{3}{-2 + \frac{3}{\epsilon} + 2} = \frac{3\epsilon}{3}\\
&= \epsilon \implies \frac{3}{4n +2} < \epsilon
\end{align*}$$


## Aufgabe 3.3

Für $n\in\mathbb N$ definieren wir die Folgen
$$a_{n} = \sqrt{n+1000} - \sqrt{n}$$
$$b_{n}= \sqrt{n+ \frac{n}{1000}} - \sqrt{n}$$

1. Zeigen Sie: Für $1 \le n < 1000000$ gilt $a_{n} > b_{n}$, jedoch $$\begin{align*}&\lim_{n\to\infty} a_{n}= 0\\ &\lim_{n\to\infty} b_{n} = \infty\end{align*}$$
   Hinweis: $x-y = \frac{x^{2} - y^{2}}{x+y}$
2. Visualisieren Sie die beiden Folgen.

---


$$\begin{align*}
&\lim_{n\to\infty} a_{n} > \lim_{n\to\infty} b_{n}\\
&\sqrt{n + 1000} - \sqrt{n} > \sqrt{n+ \frac{n}{1000}} - \sqrt{n}\\
\iff& \sqrt{n+1000} > \sqrt{n+\frac{n}{1000}}\\
\iff& n+1000 >  n+\frac{n}{1000}\\
\iff 1000000 &> 0
\end{align*}$$

$$\begin{align*}
&\lim_{n\to\infty} a_{n}= 0\\
&\lim_{n\to\infty} \sqrt{n +1000} - \sqrt{n} = \lim_{n\to\infty} \frac{\sqrt{n+1000}^{2}- \sqrt{n}^{2}}{\sqrt{n+1000} + \sqrt{n}}\\
&= \frac{n+1000-n}{\sqrt{n+1000} + \sqrt{n}}\\
&= \underbrace{\frac{1000}{\sqrt{n + 1000} + \sqrt{n}}}_{\text{Nullfolge}} = 0
\end{align*}$$


Für $b_{n}$ gilt:

$$\lim_{n\to\infty} b_{n} = \lim_{n\to\infty} \frac{\sqrt{n}}{1000 + \sqrt{n}} = \lim_{n\to\infty} \frac{1}{\frac{1000}{\sqrt{n}} + 1} = \infty$$

Da der Nenner gegen null geht, geht der Bruch gegen unendlich, und somit ist $\lim_{n\to\infty} b_{n} = \infty$.


## Aufgabe 3.4

Sei $F_{r}\subset \mathbb Q$ die Menge der positiven Fließkommazahlen mit $r+1$ Stellen, d.h. die Menge der rationalen Zahlen
$$s_{0}.s_{1}...s_{r} \cdot 10^{k} := s_{0} \cdot 10^{k} + s_{1} \cdot 10^{k-1} + ... + s_{r}\cdot 10^{k-r}$$
mit $s_{i} \in \lbrace0, ..., 9\rbrace, s_{0} \not = 0$ und $k\in\mathbb Z$. Bei der Fließkomma-Addition berechnet der Computer
$$F_{r}\times F_{r} \to F_{r}, (a, b) \mapsto rd_{r}(a+b)$$
wobei wir für $10^{k} \le x < 10^{k+1}$ mit $rd_{r}(x) \in F_{r}$  die übliche Rundung
$$x-5\cdot10^{k-r-1} < rd_{r}(x) \le x+5 \cdot 10^{k-r-1}$$
von $x$ auf $r+1$ Fließkomma stellen bezeichnen.

1. Bestimmen Sie $rd_{2}(5.491), rd_2(5.495)$ und $rd_{2}(99.96)$
2. Zeigen Sie, dass für $$a = 1.0002 \cdot 10^{-2} \qquad b = 9.0003 \cdot 10^{-2} \qquad c = 7.0001 \cdot 10^{-2}$$
   gilt $$rd_{4}(rd_{4}(a+b) + c) \not = rd_{4}(a + rd_{4}(b+c))$$
3. Implementieren Sie die Fließkomma-Addition.


## Aufgabe 3.5

Seien $n, k \in\mathbb N_{0}$. Wir bezeichnen mit $\left(n\atop k\right)$ die Anzahl der $k$-elementigen Teilmengen einer $n$-elementigen Menge.

1. Sei $A = \lbrace1, 2, 3\rbrace$ und $B = \lbrace4,5\rbrace$. Bestimmen Sie alle $4$-elementigen Teilmengen $A\cup B$, und zeigen Sie $$\left(5\atop 4\right) = \left(3\atop 2\right) \left(2\atop 2\right) + \left(3\atop 3\right)\left(2\atop 1\right)$$
2. Zeigen Sie, dass für $n, m, l \in\mathbb N_{0}$ $$\sum\limits^{k}_{j=0} \left(n\atop j\right) \left(m \atop k-j\right) = \left(n+m \atop k\right)$$
   Hinweis: Betrachten Sie disjunkte Mengen $A$ und $B$ mit $|A| = n$ und $|B| = m$.

3. Folgern Sie, dass für alle $n, k \in\mathbb N_{0}$ gilt $$\left(n+1 \atop k+1\right) = \left(n\atop k\right) + \left(n\atop k+1\right)$$ und bestimmen Sie die Zahlen (siehe Skript Seite 98)

## Aufgabe 3.6

Sei $K$ ein angeordneter Körper und $(a_{n})$ und $(b_{n})$ konvergente Folgen in $K$ mit $\lim_{n\to\infty} a_{n} = a$ und $\lim_{n\to\infty} b_{n}= b$.
Zeigen Sie, dass die Folge $(a_{n}\cdot b_{n})$ konvergiert und
$$\lim_{n\to\infty} (a_{n}\cdot b_{n}) = a\cdot b$$

## Aufgabe 3.7

Sei $(a_n)$ eine Folge mit $a_{n} \not =0$ für alle $n$.
1. Zeigen Sie: Ist $\lim_{n\to\infty} a_{n} = \infty$ oder $\lim_{n\to\infty} a_{n} = -\infty$, dann gilt $\lim_{n\to\infty} \frac{1}{a_{n}} = 0$
2. Finden Sie eine Folge $(a_n)$, sodass $\lim_{n\to\infty} a_{n}= 0$, aber $\left(1/a_{n}\right)$ nicht bestimmt divergent gegen $\infty$ ist.

## Aufgabe 3.8

1. Schreiben Sie ein Programm, das für eine positive rationale Zahl $q\in\mathbb Q$ mittels Schulbuchdivision eine Fließkomma Darstellung mit $r+1$ Stellen bestimmt, d.h. eine Fließkommazahl $$f = s_{0}.s_{1}...s_{r}\cdot 10^{k} = s_{0} \cdot 10^{k} + s_{1} \cdot 10^{k-1} + ... + s_{r} \cdot 10^{k-r}$$ mit $s_{i} \in \lbrace0,..., 9\rbrace$, $s_{0} \not = 0, k\in\mathbb Z$ und $$q-5\cdot10^{k-r-1} < f \le q+ 5 \cdot 10^{k-r-1}$$
2. Wenden Sie Ihr Programm für $r = 100$ an auf $q = \frac{2}{7}, \frac{11}{13}, \frac{101}{103}$. Mit welcher Periode wiederholen sich die Nachkommastellen?
3. Berechnen Sie die Fließkomma Darstellung von $\sqrt{2}$ für $r = 1000$, und überprüfen Sie, dass diese Darstellung nicht periodisch ist.

## Aufgabe 3.9

Sei $K$ ein Körper und $x\in K$. Zeigen Sie, dass für alle $n\in\mathbb N_{0}$ gilt
$$(x+1)^{n} = \sum\limits^{n}_{k=0} \left(n\atop k\right) x^{k}$$

## Aufgabe 3.10

Zeigen Sie: Ist $(a_{n})$ eine Cauchyfolge, die keine Null folge ist, und $a_{n} = 0$ für alle $n$ dann gibt es ein $C > 0$ mit $|a_{n}| \ge C$.

## Aufgabe 3.11

Zeigen Sie: Ist $(a_n)$ eine Cauchyfolge, die keine Null folge ist, und $a_{n}\not= 0$ für alle $n$, dann ist $\left(1/a_{n}\right)$ eine Cauchyfolge.

Hinweis: Schreiben Sie
$$\left| \frac{1}{a_{n}} - \frac{1}{a_{m}}\right| = \frac{1}{|a_{m}|\cdot|a_{n}|} \cdot |a_{n}-a_{m}|$$
und verwenden Sie Aufgabe 3.10

## Aufgabe 3.12

In einem abgeschlossenen Gebiet wir ein Kaninchen paar ausgesetzt. Jedes Kaninchen paar, das mindestens $2$ Monate alt ist, zeugt jeden Monat ein neues Kaninchen paar. Sei $f_{n}$ die Anzahl der Kaninchen paare in der Population im $n-$ten Monat unter der Annahme, dass es keine Todesfälle gibt.

1. Stellen Sie eine Rekursionsgleichung für $f_{n}$ auf, und berechnen Sie $f_{0}, ..., f_{10}$. Finden Sie den Namen der Folge in der OEIS heraus.
2. Bestimmen Sie die asymptotische Wachstumsrate der Population, d.h. $\lim_{n\to\infty} \frac{f_{n+1}}{f_{n}}$.

## Aufgabe 3.13

Sei $(a_n)$ ein unendlicher Dezimalbruch, also eine Folge der Form 
$$a_{n}= \sum\limits^{n}_{i=0} s_{i} \times 10^{k-i}$$
mit festem $k\in\mathbb Z$ und einer festgelegten Folge $(s_{n})_{n \in \mathbb  N_{0}}$ von Dezimalstellen $s_{i} \in \lbrace0,...,9\rbrace$. Zeigen Sie, dass $(a_{n})$ eine Cauchyfolge ist.

## Aufgabe 3.14

1. Zeigen Sie, dass die Folge $(a_{n})$, definiert durch $a_{1} = 1$ und
$$a_{n+1} = \sqrt{1+a_{n}}$$
konvergiert.
2. Berechnen Sie den Grenzwert $a = \lim_{n\to\infty} a_{n}$
3. Zeigen Sie, dass für die Länge $d$ einer Diagonale und die Länge $s$ einer Seite des regelmäßigen Fünfecks gilt
   $$\frac{d}{s} = a$$

## Aufgabe 3.15
Sei $d\in\mathbb R$ mit $d > 0$ und $(c_{n})$ die Folge definiert durch $c_{1} = 1$ und 
$$c_{n+1} = \frac{1}{2} \cdot\left(c_{n} + \frac{d}{c_{n}}\right)$$
1. Zeigen Sie mit vollständiger Induktion, dass $(c_{n})$ von unten beschränkt ist durch $\sqrt{d}$ und monoton fallend ist.
2. Zeigen Sie, das $\lim_{n\to\infty} c_{n} = \sqrt{d}$ 
3. Implementieren Sie die Berechnung von $\sqrt{2}$ mittels der Folge $(c_{n})$. Vergleichen Sie die Konvergenz Geschwindigkeit anhand der Anzahl der korrekten Nachkommastellen der ersten $10$ Folgeglieder.

## Aufgabe 3.16

Es sei $a_{1} = 2$ und
$$a_{n+1} = \frac{2}{3} a_{n} + \frac{1}{3} \frac{2}{a_{n}^{2}}$$
für $n \ge 1$.

1. Bestimmen Sie $a_{2}, ..., a_{10}$ bis auf $10$ Fließkomma stellen.
2. Zeigen Sie, dass die Folge $(a_{n})$ konvergiert, und bestimmen Sie den Grenzwert.

## Aufgabe 3.17 

1. Zeigen Sie: Die unendliche Dezimalbruch Darstellung einer reellen Zahl ist eindeutig, wenn wir Darstellungen mit Periode $9$ ausschließen (d.h. wenn wir z.B. nicht die Darstellung $0.0999...$ sondern $0.1000...$ verwenden).
2. Zeigen Sie, dass es zu jeder Folge $(a_{n})_{n\in\mathbb N}$ von reellen Zahlen mit $0 \le a_{n} < 1$ eine reelle Zahl $b\in\mathbb R, 0 \le b < 1$ gibt mit $$a_{n} \not = b \text{ für alle }n\in\mathbb N$$
3. Folgern Sie, dass $\mathbb R$ Überabzählbar ist.

## Aufgabe 3.18

1. Der Erfinder des Schachspiels soll sich eine Belohnung wählen. Er verlangt, dass man ihm auf das erste Feld des Schachbretts ein Weizenkorn, auf das zweite $2$, auf das dritte $4$, auf das vierte $8$ Körner, usw. legen soll. Wie viele Weizenkörner hätte er erhalten?
2. Sei $K$ ein Körper und $1 \not = \lambda \in K$. Zeigen Sie mit vollständiger Induktion, dass $$\sum\limits^{n}_{k=0} \lambda^{k} = \frac{1-\lambda^{n+1}}{1 - \lambda}$$
