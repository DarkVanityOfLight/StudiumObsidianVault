
Eine [Abbildung](Abbildungen.md) $f: M\to N$ heißt surjektiv wenn $f(M) = N$
Gilt für alle $m_1, m_2 \in M$ dass $f(m_1) = f(m_2) \implies m_1 = m_2$
so heißt die [Abbildung](Abbildungen.md)$f$ injektiv.

---

Schreiben wir $m \sim n$ für $m, n \in R$ dann bedeutet
- reflexiv, dass $m \sim m \qquad \forall m\in M$ 
- transitiv, dass $m\sim l, l\sim n \implies  m\sim n \quad \forall m,n \in M$
- symmetrisch, dass $m \sim n \implies n\sim m\quad \forall m, n \in M$

## Äquivalenzklassen
Ist $M$ eine  Menge, $\sim$ eine Äquivalenzrelation und $m\in M$, dann heißt $$[m] = \left\{n\in M : n \sim m\right\} \subset 2^M$$ die Äquivalenzklasse von $m$. Jedes $n \in [m]$ heißt Repräsentant von $[m]$

## Kanonische Abbildung
Wir schreiben $$M{\diagup\sim} = \{[m]|m\in M\} \subset 2^M$$ für die Menge der Äquivalenzklassen von $\sim$ und

$$\begin{align}
\pi :& M \to M/\sim\\
&m \mapsto [m]\\
\end{align}$$
für die kanonische Abbildung von $\sim$. Diese sind offenbar [Surjektiv](Surjektiv.md)

---

## Dreiecksungleichung

Sei $K$ ein angeordneter Körper. Es gilt
$|a+b| \leq |a| + |b|$
für alle $a,b \in K$.

$$|a-b| = |a-c + c -b| \leq |a-c| + |c-b|$$

---

Ist $K$ Archimedisch und $x\in K$ mit $-1 < x < 1$, dann gilt 
$$\lim_{n\to\infty} x^n = 0$$


---

Sei $(a_n)$ eine Folge in einem [Archimedischen Koerper](Körper.md#Archimedisch). Gibt es ein $0 < \lambda < 1$ mit $$|a_{n+1} - a_n| \leq \lambda|a_n -a_{n-1}|$$
für alle $n$, so ist $(a_n)$ eine Cauchyfolge.

---

Die harmonische Reihe
$$\sum\limits^{\infty}_{n=1} \frac{1}{n}$$
ist [bestimmt Divergent](Bestimmt%20Divergent.md) gegen $\infty$.

Für $|x| < 1$ konvergiert die geometrische [Reihe](Reihe.md) und
$$\sum^{\infty}_{n_0} x_n = {1 \over 1 -x}$$
Die Exponentialreihe
$$\sum\limits^{\infty}_{n=0} \frac{1}{n!} x^{n}$$
ist für jedes $x\in\mathbb R$ konvergent

---

## Mittelwertsatz

Sind $f, g: [r, s]\to\mathbb R$ stetig und in $]r, s[$ [differenzierbar](Differenzierbarkeit.md), und $g'(x) \not = 0$ für alle $x\in]r, s[$ dann gibt es ein $a\in]r, s[$ mit 
$$\frac{f(s)-f(r)}{g(s)-g(r)} = \frac{f'(a)}{g'(a)}$$

Ist $f: [r, s] \to\mathbb R$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und in $]r, s[$ differenzierbar mit $f'(a) = 0$ für alle $a\in]r,s[$, dann ist $f$ konstant.

## Beweis

Wir nehmen zunächst an, dass $g(x) = x$ und $f(r) = f(s)$. Ist $f$ konstant, dann ist $f'(a) = 0$ für alle $a \in ]r, s[$. Sei also $f$ nicht konstant. Da $f$ stetig ist, nimmt $f$ auf $[r, s]$ ein Minimum und ein Maximum an, und eines von beiden ist verschieden von $f(r) = f(s)$, wird also für ein $a\in]r, s[$ angenommen, nach dem Notwendigem Kriterium ist $f'(a) = 0$.
Diese Aussage angewendet auf $g$ zeight, dass $g(s) \not = g(r)$, denn sonst gäbe es ein $a\in]r, s[$ mit $g'(a) = 0$.
Wir können die Aussage also nochmals auf die Funktion 
$$F(x) = f(x) - \frac{f(s) - f(r)}{g(s)-g(r)}(g(x) -g(r))$$
anwenden, die $F(r) = F(s)$ erfüllt. Damit erhalten wir ein $a$ mit 
$0 = F'(a) = f'(a) - \frac{f(s) -f(r)}{g(s) -g(r)}g'(a)$


> Ist $f:[r, s] \to \mathbb R$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und in $]r, s[$ differenzierbar mit $f'(a) = 0$ für alle $a\in ]r, s[$, dann ist $f$ konstant


### Beweis

Für alle $x, y$ mit $r \le x < y \le s$ gibt der Mittelwertsatz, dass
$$\frac{f(y) -f(x)}{y-x} = 0$$ also $f(y) = f(x)$

## Taylorpolynom

Sei $f$ in $x_0$ mindestens k-mal [differenzierbar](Differenzierbarkeit.md) (d.h. $f'(x_{0),}..., f^{(k)}(x_0)$ existieren). Mit dem k-ten __Taylorpolynom__

$$T_{k}(x) = \sum\limits^{k}_{n=0} \frac{f^{(n)}x_{0}}{n!} (x-x_0)^n$$
ist das k-te Restglied der Taylorreihe von $f$
$$R_{k}(x) = f(x) - T_{k-1}(x)$$
Insbesondere gilt
$$T(x) = f(x) \iff \lim_{k\to\infty} R_{k(x)} = 0$$
denn $T(x) = \lim_{k\to\infty} T_{k}(x)$. Mit der folgenden Darstellung des Restglieds lässt sich oft die [Konvergenz](Konvergenz.md) der Taylorreihe beweisen
