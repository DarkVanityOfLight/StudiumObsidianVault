## Aufgabe 3.1

Auf der einen Seite einer Waage befinden sich $100$ Lebkuchen und $10$ Lebkuchen auf der andere.
Die Waage stellt sich waagerecht, wenn die eine Seite höchstens $1\%$ schwerer als die andere Seite ist. Wir legen nun schrittweise jeweils auf beiden Seiten $1$ Lebkuchen hinzu.

1. Nach wievielen Schritten $n$ steht die Waage zum ersten Mal waagrecht?
2. Sei $a_{n} =100 +n$ und $b_{n}= 10 +n$ Zeigen Sie, dass $$\lim_{n\to\infty} \frac{a_{n}}{b_{n}} = 1$$
## Aufgabe 3.2

Für $n\in\mathbb N$ sei
$$a_{n} = \frac{3n}{2n+1}$$
1. Bestimmen Sie für $m=1$, $m=10$ und $m =100$ jeweils ein $N \in\mathbb N$ mit $$\left|a_{n} - \frac{3}{2}\right| < \frac{1}{m}$$ für alle $n\ge N$.
2. Zeigen Sie, dass $\lim_{n\to\infty} a_{n}= \frac{3}{2}$

## Aufgabe 3.3

Für $n\in\mathbb N$ definieren wir die Folgen
$$a_{n} = \sqrt{n+1000} - \sqrt{n}$$
$$b_{n}= \sqrt{n+ \frac{n}{1000}} - \sqrt{n}$$

1. Zeigen Sie: Für $1 \le n < 1000000$ gilt $a_{n} > b_{n}$, jedoch $$\begin{align*}&\lim_{n\to\infty} a_{n}= 0\\ &\lim_{n\to\infty} b_{n} = \infty\end{align*}$$
   Hinweis: $x-y = \frac{x^{2} - y^{2}}{x+y}$
2. Visualisieren Sie die beiden Folgen.

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

