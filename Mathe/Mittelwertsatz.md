
Sind $f, g: [r, s]\to\mathbb R$ stetig und in $]r, s[$ [differenzierbar](Differenzierbarkeit.md), und $g'(x) \not = 0$ für alle $x\in]r, s[$ dann gibt es ein $a\in]r, s[$ mit 
$$\frac{f(s)-f(r)}{g(s)-g(r)} = \frac{f'(a)}{g'(a)}$$

Ist $f: [r, s] \to\mathbb R$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und in $]r, s[$ differenzierbar mit $f'(a) = 0$ für alle $a\in]r,s[$, dann ist $f$ konstant.

## Beweis

Wir nehmen zunächst an, dass $g(x) = x$ und $f(r) = f(s)$. Ist $f$ konstant, dann ist $f'(a) = 0$ für alle $a \in ]r, s[$. Sei also $f$ nicht konstant. Da $f$ stetig ist, nimmt $f$ auf $[r, s]$ ein Minimum und ein Maximum an, und eines von beiden ist verschieden von $f(r) = f(s)$, wird also für ein $a\in]r, s[$ angenommen, nach dem Notwendigem Kriterium ist $f'(a) = 0$.
Diese Aussage angewendet auf $g$ zeigt, dass $g(s) \not = g(r)$, denn sonst gäbe es ein $a\in]r, s[$ mit $g'(a) = 0$.
Wir können die Aussage also nochmals auf die Funktion 
$$F(x) = f(x) - \frac{f(s) - f(r)}{g(s)-g(r)}(g(x) -g(r))$$
anwenden, die $F(r) = F(s)$ erfüllt. Damit erhalten wir ein $a$ mit 
$0 = F'(a) = f'(a) - \frac{f(s) -f(r)}{g(s) -g(r)}g'(a)$

---

> Ist $f:[r, s] \to \mathbb R$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und in $]r, s[$ differenzierbar mit $f'(a) = 0$ für alle $a\in ]r, s[$, dann ist $f$ konstant


### Beweis

Für alle $x, y$ mit $r \le x < y \le s$ gibt der Mittelwertsatz, dass
$$\frac{f(y) -f(x)}{y-x} = 0$$ also $f(y) = f(x)$

#klausur 

 