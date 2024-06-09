
Es gilt:
$f^{-1}(f(m)) = m \forall m\in M$
$f(f^{-1}(n)) = n \forall n\in N$

Komposition von [Abbildungen](Abbildungen.md) #übung 

---

Zeige $g$ eindeutig durch $g \circ f = id_M, f\circ g = id_N$ bestimmt
Sei $h: N \to M$ mit $h \circ f = id_M, f\circ h = id_N$
$\implies h = h\circ id_N = h \circ f \circ g = \underbrace{h \circ f}_{id_M} \circ g = g \square$
insbesondere $g= f^{-1}$

---

$id_m: M\to M, m \mapsto m$
$f: M \to N bij \implies f^-1 \circ f = id_M, f \circ f = id_N$

---

Warteschlangen: Bei rear hinten = vorne
Invariante: Immer eingehalten,
vorne > hinten



---


To prove this, we will use the geometric sum formula. The formula states that for any complex number $z$ such that $|z| = 1$, the sum of the first $n$ powers of $z$ is given by

$$ \sum^{n-1}_{k=0} z^k = \frac{1 - z^n}{1 - z} $$

In our case, we have $z = e^{i {2\pi \over n}}$, so

$$ \begin{aligned} \sum^{n-1}_{k=0} e^{i {2\pi k \over n}} &= \frac{1 - e^{i {2\pi n \over n}}}{1 - e^{i {2\pi \over n}}} \ &= \frac{1 - e^{i {2\pi }}}{1 - e^{i {2\pi \over n}}} \ &= \frac{1 - 1}{1 - e^{i {2\pi \over n}}} \ &= 0 \end{aligned} $$

Therefore, we have proven that for all $n \in \mathbb N$,

$$ \sum^{n-1}_{k=0} e^{i {2\pi k \over n}} = 0 $$

as desired.

---

$$\begin{align}
&f(x) = \frac{1}{3} x^5 - 2x^2\\
&0 = \frac{1}{3} x^5 - 2x^2\\
&0 = x^2 \cdot (\frac{1}{3} x^3 - 2)\\
&(x_1)^2 = 0 \iff x_1 = 0\\
& \frac{1}{3} x^3 - 2= 0\\
& \frac{1}{3} x^3 =2\\
&x^3 = 6\\
&\sqrt[3]{x^3} = \sqrt[3]{6}\\
& x_2 \approx 1.8171 \quad x_3 \approx - 1.8171

\end{align}$$
---

$$\begin{align}
&f(x) = 8x^{3}- 4x^4\\
&4x^2(2x -x^2)\\
&4x^{2}= 0 \land 2x-x^2=0\\
&x_{1}= 0 \land x (2 - x) = 0\\
&x_{2}= 0 \land (2-x) = 0\\
&x_{1, 2} = 0 \land x_{3}= 2
\end{align}$$
---

$$\begin{align*}
f(x) &= 12x^{2}-96 + 128\\
a &= 12\\
b &= -96\\
c &= 128\\
x_{1,2} &= \frac{-b \pm \sqrt{b^{2}  - 4  \cdot a \cdot c}}{2 \cdot a}\\
x_{1,2}&= \frac{-(-96) \pm \sqrt{(-96)^{2}- 4 \cdot 12 \cdot 128}}{2\cdot 12}\\
x_{1,2}&= \frac{96 \pm \sqrt{(-96)^{2}- 4 \cdot 12 \cdot 128}}{2\cdot 12}\\
x_{1,2}&= \frac{96 \pm \sqrt{9216 - 4 \cdot 12 \cdot 128}}{2\cdot 12}\\
x_{1,2}&= \frac{96 \pm \sqrt{9216 - 48 \cdot 128}}{2\cdot 12}\\
x_{1,2}&= \frac{96 \pm \sqrt{9216 - 6144}}{2\cdot 12}\\
x_{1,2}&= \frac{96 \pm \sqrt{9216 - 6144}}{24}\\
x_{1,2}&= \frac{96 \pm \sqrt{3072}}{24}\\
x_{1} &= \frac{96 + \sqrt{3072}}{24} \land x_{2} = \frac{96 - \sqrt{3072}}{24}\\
x_{1}&\approx 6.3094 \land x_{2}\approx 1.6906
\end{align*}
$$
---

$$\frac{a+b}{c} = \frac{a}{c} + \frac{b}{c}$$

$$\frac{a\cdot b}{c} = \frac{a}{c} \cdot b = \frac{a}{1} \cdot \frac{b}{c}$$
$$\frac{a}{b} \cdot \frac{c}{d} = \frac{ac}{bd}$$
$$\frac{\frac{a}{b}}{c} = \frac{a}{b\cdot c}$$
$$
\frac{a}{\frac{b}{c}} = \frac{a \cdot c}{b}
$$
---

$$\sqrt[n]{x^{y}} = x^\frac{y}{n}$$

---

$$a = a + (c - c) = a + c -c$$

---

$$\lim_{n\to\infty}\frac{1}{n} = 0$$


---

$$f(x) = \frac{1}{x}$$

---

$$\frac{f(a)}{f(b)} = \frac{f'(a)}{f'(b)}$$

---

Mengen -> Abbildung -> Abbildung aus $\mathbb N$ ist eine Folge

$$\begin{align*}
a: M \to N\\
m \mapsto n
\end{align*}$$
Folge
$$a: \mathbb N \mapsto M$$
Reihe
$$M \mapsto \mathbb R$$

---

$$f(x) = \frac{x}{3}$$
$$g(x) = x \cdot 3$$

---

$$\ln(\exp(x)) = x$$

$$\ln x$$

---


Um zu zeigen, dass $U1$ ein Untervektorraum ist, müssen wir die drei Bedingungen für Untervektorräume überprüfen:

1.  $0 \in U1$: Der Nullvektor ist gegeben durch $(0,0)$. Da $0_2 = 0_1^2$, ist $(0,0)$ ein Element von $U1$.
    
2.  $U1$ ist unter Vektoraddition abgeschlossen: Seien $u = (u_1, u_2)$ und $v = (v_1, v_2)$ Elemente von $U1$. Wir müssen zeigen, dass $u + v$ ebenfalls in $U1$ liegt. Wir haben:
    

$$(u+v)_2 = u_2 + v_2 = u_1^2 + v_1^2 = (u_1 + v_1)^2$$

Also ist $u+v$ ein Element von $U1$.

3.  $U1$ ist unter skalaren Multiplikation abgeschlossen: Sei $u = (u_1, u_2)$ ein Element von $U1$ und $\lambda$ ein Skalar. Wir müssen zeigen, dass $\lambda u$ ebenfalls in $U1$ liegt. Wir haben:

$$(\lambda u)_2 = \lambda u_2 = \lambda u_1^2 = (\lambda u_1)^2$$

Also ist $\lambda u$ ein Element von $U1$.

---
Ja, man kann auch zeigen, dass $U1$ der Kern eines geeigneten linearen Operators auf $\mathbb{R}^2$ ist, um zu beweisen, dass $U1$ ein Untervektorraum von $\mathbb{R}^2$ ist.

Definieren wir den linearen Operator $T: \mathbb{R}^2 \rightarrow \mathbb{R}$ durch $T(x_1, x_2) = x_2 - x_1^2$. Dann ist $U1$ der Kern von $T$, d.h. $U1 = {x \in \mathbb{R}^2 \mid T(x) = 0}$.

Um zu zeigen, dass $U1$ ein Untervektorraum ist, müssen wir die beiden Bedingungen für Kerne von linearen Operatoren überprüfen:

1.  $0 \in U1$: $T(0,0) = 0^2 - 0^2 = 0$, also ist $(0,0) \in U1$.
    
2.  $U1$ ist unter Vektoraddition abgeschlossen: Seien $u, v \in U1$, d.h. $T(u) = T(v) = 0$. Dann haben wir $T(u + v) = T(u) + T(v) = 0 + 0 = 0$, also ist $u+v \in U1$.
    

Da $U1$ der Kern eines linearen Operators ist, ist $U1$ ein Untervektorraum von $\mathbb{R}^2$

---

---
 Um zu zeigen, dass die lineare Abbildung $f: \mathbb{P}_2 \rightarrow \mathbb{P}_3$ mit $f(p(x))=p'(x)+(x+1)\cdot p(x)$ ein Vektorraumhomomorphismus ist, müssen wir zeigen, dass $f$ die folgenden beiden Bedingungen erfüllt:

1.  Additivität: $f(u+v) = f(u) + f(v)$ für alle $u, v \in \mathbb{P}_2$.
2.  Homogenität: $f(\lambda u) = \lambda f(u)$ für alle $\lambda \in \mathbb{R}$ und $u \in \mathbb{P}_2$.

Seien $p(x) = ax^2 + bx + c$ und $q(x) = dx^2 + ex + f$ beliebige Polynome aus $\mathbb{P}_2$.

Dann haben wir:

1.  Additivität:

$$\begin{align*} f(p(x) + q(x)) &= f((a+d)x^2 + (b+e)x + (c+f)) \\ &= (a+d) + (b+e)x + (c+f) + x(a+d)x^2 + (a+d)x(b+e) \\ &= (a+d)x^2 + (b+e)x + (c+f) + ap'(x) + bp(x) + dp'(x) + eq(x) \\ &= p'(x) + d(x+1)x^2 + (a+b+e)(x+1)x + (c+f) + p'(x) + e(x+1)x + f(x+1) \\ &= p'(x) + q'(x) + (x+1)(p(x) + q(x)) \\ &= f(p(x)) + f(q(x)) \end{align*}$$

Daher ist $f$ additiv.

2.  Homogenität:

$$\begin{align*} f(\lambda p(x)) &= f(\lambda ax^2 + \lambda bx + \lambda c) \\ &= \lambda a + \lambda b x + \lambda c + x\lambda ax^2 + \lambda a x \cdot \lambda b \\ &= \lambda(ax^2 + bx + c) + x\lambda^2 ax^2 + \lambda^2 ax \cdot \lambda b \\ &= \lambda p'(x) + (\lambda^2 x + \lambda) p(x) \\ &= \lambda(p'(x) + (x+1)p(x)) \\ &= \lambda f(p(x)) \end{align*}$$

Daher ist $f$ homogen.
Da $f$ sowohl additiv als auch homogen ist, ist $f$ ein Vektorraumhomomorphismus.

---

Um die Darstellungsmatrix eines Vektorraumhomomorphismus bezüglich zweier Basen in einem Polynomring zu berechnen, können Sie wie folgt vorgehen:

Angenommen, wir haben den Vektorraumhomomorphismus $f:V\rightarrow W$ zwischen zwei Vektorräumen $V$ und $W$, die beide als Polynomringe definiert sind. Wir wählen zwei Basen für $V$ und $W$, sagen wir ${v_1, v_2, \ldots, v_n}$ für $V$ und ${w_1, w_2, \ldots, w_m}$ für $W$.

Dann können wir die Darstellungsmatrix von $f$ bezüglich dieser Basen wie folgt berechnen:

1.  Schreiben Sie die Basen für $V$ und $W$ als Spalten in zwei Matrizen. Die Matrix für $V$ ist eine $n \times n$-Einheitsmatrix, die Matrix für $W$ ist eine $m \times m$-Einheitsmatrix.
    
    $$[V] = \begin{pmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{pmatrix} \qquad [W] = \begin{pmatrix} 1 & 0 & \cdots & 0 \\ 0 & 1 & \cdots & 0 \\ \vdots & \vdots & \ddots & \vdots \\ 0 & 0 & \cdots & 1 \end{pmatrix}$$
    
2.  Berechnen Sie die Koordinaten von jedem Basisvektor in $W$ unter der Abbildung $f$. Dazu wenden Sie $f$ auf jeden Basisvektor in $V$ an und schreiben das Ergebnis als Linearkombination der Basisvektoren in $W$. Schreiben Sie die Koordinaten als Spalten in einer Matrix.
    
    $$[f(v_1)]_W \quad [f(v_2)]_W \quad \cdots \quad [f(v_n)]_W$$
    
3.  Die Darstellungsmatrix von $f$ bezüglich der Basen ist dann die Matrix, die aus den Koordinaten von Schritt 2 besteht, wenn Sie die Basisvektoren von $V$ als Zeilen verwenden:
    
    $$[f]_{V,W} = \begin{pmatrix} [f(v_1)]_W \\ [f(v_2)]_W \\ \vdots \\ [f(v_n)]_W \end{pmatrix}$$
    

Die resultierende Matrix $[f]_{V,W}$ hat die Dimension $m \times n$ und zeigt, wie die Abbildung $f$ die Koordinaten eines Vektors in der Basis von $V$ auf die Koordinaten in der Basis von $W$ abbildet.

---

Gerne! Hier ist ein Beispiel, wie man die Darstellungsmatrix eines Vektorraumhomomorphismus bezüglich zweier Basen in einem Polynomring berechnet:

Sei $f:\mathbb{R}[x]_{\leq 2} \rightarrow \mathbb{R}^2$ definiert durch $f(p(x)) = \begin{pmatrix} p(1) \ p(-1) \end{pmatrix}$, das heißt $f$ ordnet jedem Polynom vom Grad höchstens 2 in $\mathbb{R}[x]$ ein Paar von Zahlen zu, nämlich den Funktionswert an der Stelle $1$ und den Funktionswert an der Stelle $-1$.

Wir wählen die Basis ${1, x, x^2}$ für $\mathbb{R}[x]_{\leq 2}$ und die Standardbasis ${(1,0), (0,1)}$ für $\mathbb{R}^2$.

1.  Schreiben Sie die Basen als Spalten in zwei Matrizen:
    
    $$[V] = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \qquad [W] = \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix}$$
    
2.  Berechnen Sie die Koordinaten von jedem Basisvektor in $W$ unter der Abbildung $f$:
    
    $$[f(1)]_W = \begin{pmatrix} 1 \\ 1 \end{pmatrix} \quad [f(x)]_W = \begin{pmatrix} 1 \\ -1 \end{pmatrix} \quad [f(x^2)]_W = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$$
    
3.  Die Darstellungsmatrix von $f$ bezüglich der Basen ist:
    
    $$[f]_{V,W} = \begin{pmatrix} 1 & 1 & 1 \\ 1 & -1 & 1 \end{pmatrix}$$
    

Das bedeutet, dass die Abbildung $f$ einen Vektor $p(x) = ax^2 + bx + c$ als $\begin{pmatrix} a + b + c \ a - b + c \end{pmatrix}$ in der Standardbasis von $\mathbb{R}^2$ darstellt.

---

Der Prozess, um die Darstellungsmatrix eines Vektorraumhomomorphismus von einer Polynombasis zu einer anderen zu berechnen, ist sehr ähnlich zu dem Verfahren, das ich in meinem vorherigen Beispiel erklärt habe. Der einzige Unterschied besteht darin, dass die Basen nun aus verschiedenen Polynomen bestehen können.

Hier ist ein Beispiel, um zu veranschaulichen, wie dies funktioniert:

Sei $f:\mathbb{R}_2[x] \rightarrow \mathbb{R}_2[x]$ definiert durch $f(p(x)) = (x+1)p(x)$, das heißt $f$ multipliziert jedes Polynom vom Grad höchstens 2 in $\mathbb{R}_2[x]$ mit dem Polynom $(x+1)$.

Wir wählen die Basis ${1, x, x^2}$ für $\mathbb{R}_2[x]$ und die Basis ${1, (x+1), (x+1)^2}$ für $\mathbb{R}_2[x]$.

1.  Schreiben Sie die Basen als Spalten in zwei Matrizen:
    
    $$[V] = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix} \qquad [W] = \begin{pmatrix} 1 & 1 & 1 \\ 0 & 1 & 2 \\ 0 & 0 & 1 \end{pmatrix}$$
    
2.  Berechnen Sie die Koordinaten von jedem Basisvektor in $W$ unter der Abbildung $f$:
    
    $$[f(1)]_W = \begin{pmatrix} 1 \ 0 \ 0 \end{pmatrix} \quad [f(x)]_W = \begin{pmatrix} 1 \ 1 \ 0 \end{pmatrix} \quad [f(x^2)]_W = \begin{pmatrix} 1 \ 2 \ 1 \end{pmatrix}$$
    
3.  Die Darstellungsmatrix von $f$ bezüglich der Basen ist:
    
    $$[f]_{V,W} = \begin{pmatrix} 1 & 1 & 1 \ 0 & 1 & 2 \ 0 & 0 & 1 \end{pmatrix}$$
    

Das bedeutet, dass die Abbildung $f$ einen Vektor $p(x) = ax^2 + bx + c$ als $(a + b + c) + (a + 2b + c)(x+1) + a(x+1)^2$ in der Basis ${1, (x+1), (x+1)^2}$ darstellt.

---

Um eine Basis als Spalten einer Matrix zu schreiben, ordnen Sie einfach die Elemente der Basis nacheinander in Spalten an. Jedes Element der Basis wird als Spalte in der Matrix dargestellt.

Hier ist ein Beispiel:

Betrachten wir den Vektorraum $\mathbb{R}^3$ mit der Basis $B = {(1,0,0),(0,1,0),(0,0,1)}$.

Um diese Basis als Spalten einer Matrix darzustellen, schreiben wir jedes Basisvektor als Spalte der Matrix:

$$[B] = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

Hier haben wir einfach die Basisvektoren $(1,0,0)$, $(0,1,0)$ und $(0,0,1)$ als die Spalten der Matrix angeordnet.

Beachten Sie, dass die Reihenfolge, in der die Basisvektoren angeordnet sind, wichtig ist. Wenn wir die Reihenfolge ändern würden, würden wir eine andere Darstellungsmatrix erhalten.

---

Bei der Darstellung von Polynomen als Spalten einer Matrix müssen wir die Koeffizienten der Polynome in den Spalten der Matrix ordnen.

Hier ist ein Beispiel:

Betrachten wir den Vektorraum $\mathbb{R}_2[x]$ mit der Basis $B = {1, x, x^2}$.

Um diese Basis als Spalten einer Matrix darzustellen, schreiben wir jeden Basisvektor als Spalte der Matrix:

$$[B] = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

Beachten Sie, dass jeder Basisvektor ein Polynom vom Grad höchstens 2 ist. Um jedoch eine Darstellungsmatrix für eine lineare Abbildung von $\mathbb{R}_2[x]$ zu berechnen, müssen wir die Koeffizienten der Polynome in der richtigen Reihenfolge ordnen.

Hier ist ein Beispiel, um dies zu veranschaulichen:

Betrachten wir die lineare Abbildung $f:\mathbb{R}_2[x] \rightarrow \mathbb{R}_2[x]$ definiert durch $f(p(x)) = (x+1)p(x)$.

Wir möchten die Darstellungsmatrix von $f$ in Bezug auf die Basen $B = {1, x, x^2}$ und $B' = {1, (x+1), (x+1)^2}$ berechnen.

Um die Basis $B'$ als Spalten einer Matrix darzustellen, schreiben wir jeden Basisvektor als Spalte der Matrix und ordnen die Koeffizienten in der richtigen Reihenfolge an:

$$[B'] = \begin{pmatrix} 1 & 1 & 1 \ 0 & 1 & 2 \ 0 & 0 & 1 \end{pmatrix}$$

In diesem Beispiel haben wir das Polynom $(x+1)^2$ als dritte Spalte der Matrix geschrieben und die Koeffizienten in der Reihenfolge $1, 2, 1$ angeordnet, um sicherzustellen, dass die Matrix die richtigen Informationen enthält, um die Polynome in Bezug auf die Basis $B'$ darzustellen.

Beachten Sie, dass die Reihenfolge, in der die Koeffizienten angeordnet sind, auch wichtig ist. Wenn wir die Reihenfolge der Koeffizienten ändern, würde die Darstellungsmatrix eine andere Bedeutung haben.

--- 

Um die darstellende Matrix $M^{\omega}_{\delta}$ des linearen Abbildung $d/dx: \mathbb{R}[x]_{\leq 3} \to \mathbb{R}[x]_{\leq 2}$ zu finden, müssen wir die Bilder von den Vektoren in der Basis $\delta$ unter der linearen Abbildung bestimmen und diese als Linearkombinationen der Basisvektoren $\omega$ darstellen.

Zunächst betrachten wir die Bilder von $1$, $x$, $x^2$ und $x^3$ unter $d/dx$:

$$\frac{d}{dx}(1) = 0,$$ $$\frac{d}{dx}(x) = 1,$$ $$\frac{d}{dx}(x^2) = 2x,$$ $$\frac{d}{dx}(x^3) = 3x^2.$$

Dann können wir die Bilder von $\delta$ als Linearkombinationen von $\omega$ darstellen, d.h.

$$\begin{aligned} \frac{d}{dx}(1) &= 0\cdot 1 + 0\cdot x + 0\cdot x^2 + 0\cdot x^3 \\ &= 0\cdot \omega_1 + 0\cdot \omega_2 + 0\cdot \omega_3 + 0\cdot \omega_4, \end{aligned}$$

Die darstellende Matrix $M^{\omega}_{\delta}$ der linearen Abbildung $d/dx: \mathbb{R}[x]_{\leq 3} \to \mathbb{R}[x]_{\leq 2}$ bezüglich der Basen $\delta = {1, x, x^2}$ und $\omega = {1, x, x^2, x^3}$ kann nun als die Matrix der Koeffizienten der Linearkombinationen geschrieben werden, die wir oben erhalten haben:

$$M^{\omega}_{\delta} = \begin{bmatrix} 0 & 1 & 0 & 0 \\ 0 & 0 & 2 & 0 \\ 0 & 0 & 0 & 3 \end{bmatrix}.$$

Jeder Eintrag in der $i$-ten Zeile und $j$-ten Spalte dieser Matrix entspricht dem Koeffizienten von $\omega_i$ in der Linearkombination des Bildes von $\delta_j$ unter der linearen Abbildung $d/dx$.

Die Linearkombinationen, die wir oben erhalten haben, basieren auf der Definition der darstellenden Matrix $M^{\omega}_{\delta}$ einer linearen Abbildung zwischen endlichdimensionalen Vektorräumen bezüglich gegebener Basen.

Sei $T: V \to W$ eine lineare Abbildung zwischen endlichdimensionalen Vektorräumen $V$ und $W$ mit Basen $\alpha = {v_1, \dots, v_n}$ und $\beta = {w_1, \dots, w_m}$, dann kann man $T$ durch eine $m \times n$-Matrix darstellen, deren Einträge die Koeffizienten der Linearkombinationen der Bilder von Basisvektoren von $V$ sind, ausgedrückt als Linearkombinationen der Basisvektoren von $W$.

Konkret bedeutet das, dass die darstellende Matrix $M^{\beta}_{\alpha}$ von $T$ durch

$$T(v_j) = \sum_{i=1}^{m}M^{\beta}_{\alpha}(i,j)w_i$$

gegeben ist, wobei $M^{\beta}_{\alpha}(i,j)$ der Koeffizient von $w_i$ in der Darstellung von $T(v_j)$ als Linearkombination von $w_1, \dots, w_m$ ist.

In unserem Beispiel war die lineare Abbildung $T: \mathbb{R}[x]_{\leq 3} \to \mathbb{R}[x]_{\leq 2}$ gegeben durch $T(p(x)) = p'(x)$, und die Basen von $\mathbb{R}[x]_{\leq 3}$ und $\mathbb{R}[x]_{\leq 2}$ waren $\omega = {1, x, x^2, x^3}$ und $\delta = {1, x, x^2}$. Die Koeffizienten der Linearkombinationen, die wir oben erhalten haben, entsprechen den Einträgen der darstellenden Matrix $M^{\omega}_{\delta}$ von $T$.



---

Wir wollen zeigen, dass $T(n) \in O(n)$
$$\begin{align*}
\text{Versuch 1}: T(n) &\le n\\
\end{align*}$$
Induktionsanfang
$$T(1) = O \le 1$$
Induktionsschritt:
$$\begin{align*}
T(n) &=  T\left(\lfloor \frac{n}{2} \rfloor\right)+ T\left(\lceil\frac{n}{2}\rceil\right) + 1\\
&\le  \frac{n}{2} + \frac{n}{2} + 1\\
&= n+1 > n :(
\end{align*}$$

Versuch 2:
$$T(n) \le n-1$$
Induktionsanfang:
$$T(1) = O \le 0$$
Induktionsschirtt:

Die Gruppe $G$ ist nicht abelsch, da Drehungen und Spiegelungen nicht miteinander vertauschen. Daher ist es möglich, dass $U$ kein Normalteiler von $G$ ist. Wenn $U$ normal wäre, würde für jedes $g \in G$ und jedes $u \in U$ das Produkt $gug^{-1}$ auch in $U$ liegen. Wir müssen nur ein Gegenbeispiel finden, um zu zeigen, dass dies nicht der Fall ist.

Betrachten wir die Drehung um $90^\circ$ im Uhrzeigersinn, die in $G$ enthalten ist. Wenn $U$ normal wäre, müsste das Produkt dieser Drehung mit der Horizontalen Spiegelung in $U$ liegen. Wir berechnen:

$(90^\circ \text{ Drehung im Uhrzeigersinn})\cdot (\text{Horizontal Spiegelung})\cdot(270^\circ \text{ Drehung im Uhrzeigersinn}) = (\text{Vertikale Spiegelung}) \notin U$

Daher ist $U$ kein Normalteiler von $G$.

---

Die Symmetriegruppe $G$ des Quadrats besteht aus insgesamt 8 Elementen, die die verschiedenen Spiegelungen, Drehungen und Identitäten des Quadrats darstellen. Diese Elemente können wir als $G = {e, r, r^2, r^3, f, fr, fr^2, fr^3}$ notieren, wobei $e$ das neutrale Element (die Identität), $r$ eine Vierteldrehung im Uhrzeigersinn um den Mittelpunkt, und $f$ die Spiegelung an der Horizontalen durch die Mitte des Quadrats darstellen.

Die Untergruppe $U$ des Rechtecks besteht aus 4 Elementen, die die Identität, die horizontale Spiegelung, die vertikale Spiegelung und die Drehung um 180 Grad darstellen. Wir können diese als $U = {e, h, v, r^2}$ notieren.

Um zu zeigen, dass $U$ ein Normalteiler von $G$ ist, müssen wir zeigen, dass $gug^{-1} \in U$ für alle $g \in G$ und $u \in U$ gilt.

Wir prüfen nun alle Elemente von $G$ mit allen Elementen von $U$:

$eue^{-1} = u$ für alle $u \in U$, da $e$ das neutrale Element ist.

$rur^{-1} = u$ für alle $u \in U$, da $r$ eine Vierteldrehung ist, die die horizontale und vertikale Achsen des Rechtecks austauscht und somit die Spiegelungen erhält.

$r^2ur^{-2} = u$ für alle $u \in U$, da $r^2$ eine Halbdrehung um 180 Grad darstellt, die das Rechteck unverändert lässt und somit die Identitäts- und Drehungselemente erhält.

$fruf^{-1} = v$ für $u = e$ oder $u = r^2$, da $f$ eine Spiegelung an der horizontalen Achse durch die Mitte des Quadrats ist und somit die Spiegelungselemente erhält.

$frhf^{-1} = h$ für $u = e$ oder $u = r^2$, da $h$ die Spiegelung an der vertikalen Achse durch die Mitte des Rechtecks ist und somit die Spiegelungselemente erhält.

$frv f^{-1} = v$ für $u = h$ oder $u = v$, da $v$ die Spiegelung an der horizontalen Achse durch die Mitte des Rechtecks ist und somit die Spiegelungselemente erhält.

$fr^2uf^{-2} = u$ für alle $u \in U$, da $fr^2f^{-1} = r^2$ und $r^2ur^{-2} = u$ für alle $u \in U$ gilt.

Da für alle Elemente von $G$ und $U$ das entsprechende $gug^{-1}$-Element in $U$ enthalten ist, ist $U$ ein Normalteiler von $G$.

---

Zunächst betrachten wir die Elemente von G und U. G enthält insgesamt 8 Elemente, nämlich die Identität, die Drehungen um 90, 180 und 270 Grad im Uhrzeigersinn, sowie die Spiegelungen an den Achsen durch die Mitte der Seiten und der Diagonalen des Quadrats. U besteht aus 4 Elementen, nämlich der Identität, der Drehung um 180 Grad und den Spiegelungen an den Achsen durch die Mitte der Seiten des Rechtecks.

Wir wollen nun zeigen, dass U ein Normalteiler von G ist. Dazu betrachten wir die Linksnebenklassen von U in G, d.h. die Mengen $gU$ für alle $g \in G$. Zunächst ist klar, dass die Menge $eU = U$ die Identität enthält und somit das neutrale Element von G. Weiterhin können wir beobachten, dass sich alle Elemente von G durch Anwenden einer der 4 Elemente von U auf ein Element in U abbilden lassen. Zum Beispiel gilt für die Drehung um 90 Grad im Uhrzeigersinn, dass $D_{90} \in U$ und für alle $g \in G$ gilt $gD_{90} \in U$, da $g$ entweder eine Drehung oder eine Spiegelung ist, die sich durch Anwenden von Drehungen und Spiegelungen aus $D_{90}$ ergeben.

Da jeder Nebenklasse von U ein Element von U angehört und alle Elemente von G sich durch Anwenden von Elementen aus U auf ein Element aus U abbilden lassen, ist jede Nebenklasse von U eine Teilmenge von G. Wir müssen also noch zeigen, dass alle Nebenklassen von U gleich sind, d.h. dass für alle $g_1,g_2 \in G$ gilt $g_1U = g_2U$. Hierzu betrachten wir die Rechtsnebenklassen von U in G, d.h. die Mengen $Ug$ für alle $g \in G$. Diese Rechtsnebenklassen sind aufgrund der Assoziativität der Gruppenoperation genau die Linksnebenklassen von U in G, d.h. $Ug = gU$ für alle $g \in G$. Daher sind alle Nebenklassen von U in G gleich und U ist ein Normalteiler von G.

Zusammenfassend haben wir gezeigt, dass jede Nebenklasse von U eine Teilmenge von G ist und dass alle Nebenklassen von U gleich sind. Daher ist U ein Normalteiler von G.

---

1.  Das Nullvektor $(0,0)$ ist in $U_2$: $$0+0=0$$ Daher ist $(0,0)$ in $U_2$.
2.  $U_2$ ist unter Addition abgeschlossen: Wenn $(x_1,y_1),(x_2,y_2) \in U_2$, dann gilt $x_1+y_1=0$ und $x_2+y_2=0$. Dann ist $$(x_1,y_1) + (x_2,y_2) = (x_1+x_2, y_1+y_2)$$ und da $x_1+y_1=0$ und $x_2+y_2=0$, folgt $x_1+x_2 + y_1+y_2 = 0$, was bedeutet, dass $(x_1+x_2, y_1+y_2) \in U_2$.
3.  $U_2$ ist unter Skalarmultiplikation abgeschlossen: Wenn $(x,y) \in U_2$ und $c$ ein Skalar ist, dann ist $(c\cdot x, c\cdot y) \in U_2$, da $$c\cdot x + c\cdot y = c\cdot(x+y) = c\cdot 0 = 0.$$
---
Ja, $U_2$ ist ein Untervektorraum von $\mathbb{R}^2$.

Um zu zeigen, dass $U_2$ ein Untervektorraum ist, müssen wir die folgenden Bedingungen nachweisen:

1.  Das Nullvektor $(0,0)$ ist in $U_2$: $0\cdot 0 = 0$, daher ist $(0,0)$ in $U_2$.
 
2.  Wenn $(x_1, y_1), (x_2, y_2) \in U_2$, dann gilt entweder $x_1=0$ oder $y_1=0$ oder beides sowie $x_2=0$ oder $y_2=0$ oder beides. Daher ist entweder $(x_1+x_2, y_1+y_2) = (x_1, y_2)$ oder $(x_1+x_2, y_1+y_2) = (x_2, y_1)$ oder beide, und in beiden Fällen ist entweder $x_1+x_2=0$ oder $y_1+y_2=0$ oder beides. Das bedeutet, dass $(x_1+x_2, y_1+y_2) \in U_2$, da $0 \cdot (x_1+x_2) \cdot (y_1+y_2) = 0$.
 
3.  $U_2$ ist unter Skalarmultiplikation abgeschlossen: Wenn $(x,y) \in U_2$ und $c$ ein Skalar ist, dann ist $(c\cdot x, c\cdot y) \in U_2$, da entweder $x=0$ oder $y=0$ oder beides, und daher ist $c\cdot x \cdot c\cdot y = c^2 \cdot (x\cdot y) = 0$.


Da $U_2$ alle Bedingungen eines Untervektorraums erfüllt, ist es ein Untervektorraum von $\mathbb{R}^2$.

---

1.  Das Nullvektor $(0,0)$ ist in $U_2$: Da $0+0=0-0=0$, ist $(0,0)$ in $U_2$.
    
2.  $U_2$ ist unter Addition abgeschlossen: Wenn $(x_1,y_1),(x_2,y_2) \in U_2$, dann gilt $x_1+y_1 = x_1-y_1 = x_2+y_2 = x_2-y_2 = 0$. Dann ist $(x_1+x_2, y_1+y_2) = ((x_1+y_1) + (x_2+y_2), (x_1-y_1) + (x_2-y_2)) = (0+0,0+0) = (0,0)$, das auch in $U_2$ liegt.
    
3.  $U_2$ ist unter Skalarmultiplikation abgeschlossen: Wenn $(x,y) \in U_2$ und $c$ ein Skalar ist, dann gilt $x+y=x-y=0$. Dann ist $(c\cdot x, c\cdot y) = (c(x+y), c(x-y)) = (c\cdot 0, c\cdot 0) = (0,0)$, das auch in $U_2$ liegt.

---

$$A = \begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & -1 & 1 & -1 \end{pmatrix}$$

Um die Basis von $V$ zu bestimmen, müssen wir den Kern oder die Nullraum von $A$ finden, dh die Menge aller Lösungen des homogenen linearen Gleichungssystems $Ax = 0$. Wir können dies tun, indem wir die Zeilenstufenform von $A$ finden und dann die freien Variablen bestimmen.

Führen wir nun die Elimination durch:

$$\begin{pmatrix} 1 & 1 & 1 & 1 \\ 1 & -1 & 1 & -1 \end{pmatrix} \rightarrow \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & -2 & 0 & -2 \end{pmatrix} \rightarrow \begin{pmatrix} 1 & 1 & 1 & 1 \\ 0 & 1 & 0 & 1 \end{pmatrix} \rightarrow \begin{pmatrix} 1 & 0 & 1 & 0 \\ 0 & 1 & 0 & 1 \end{pmatrix}$$

Also haben wir $x_1 = -x_3$ und $x_2 = -x_4$. Die freien Variablen sind also $x_3$ und $x_4$. Eine Basis für den Kern von $A$ besteht aus den Lösungen des homogenen Systems, wobei jede freie Variable einmalig auf $1$ und alle anderen frei Variablen auf $0$ gesetzt werden. Wir haben also:

$$\begin{pmatrix} 1 \\ 0 \\ -1 \\ 0 \end{pmatrix}, \begin{pmatrix} 0 \\ 1 \\ 0 \\ -1 \end{pmatrix}$$

Diese beiden Vektoren bilden eine Basis für den Kern von $A$, was gleichbedeutend damit ist, dass sie eine Basis für $V$ bilden, da sie linear unabhängig sind und den gesamten Raum aufspannen.


$$(\forall n,m \in\mathbb N : n, m \not \equiv 0 \mod 2) : n + m \equiv 0\mod 2 $$

$$\forall n,m \in$$
---

$$F = \frac{1}{3} x^3$$
$$\int^{1}_{-1} x^{2}dx = \frac{2}{3}$$


$$F = x-(\frac{x^{3}}{3})$$
$$\int^{1}_{-1}(1-x^{2})dx = \frac{4}{3}$$

$$\int^{1}_{-1}(1-x^{2})dx = \frac{4}{3}$$

---

### Original
Knoten A:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 6 |
| B   | 1 | 0 | 2 | 5 |

Knoten B:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 6 |
| B   | 1 | 0 | 2 | 5 |
| C   | 3 | 2 | 0 | 3 |

Knoten C:

|     | A | B | C | D |
|-----|---|---|---|---|
| B   | 1 | 0 | 2 | 5 |
| C   | 3 | 2 | 0 | 3 |
| D   | 6 | 5 | 3 | 0 |

Knoten D:

|     | A | B | C | D |
|-----|---|---|---|---|
| C   | 3 | 2 | 0 | 3 |
| D   | 6 | 5 | 3 | 0 |

### Erste Iteration:
Knoten A:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 6 |
| B   | 1 | 0 | 2 | 5 |

Knoten B:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 6 |
| B   | 1 | 0 | 2 | 5 |
| C   | 3 | 2 | 0 | 3 |

Knoten C:

|     | A | B | C | D |
|-----|---|---|---|---|
| B   | 1 | 0 | 2 | 5 |
| C   | 3 | 2 | 0 | 7 |
| D   | 6 | 5 | 3 | 0 |

Knoten D:

|     | A | B | C | D |
|-----|---|---|---|---|
| C   | 3 | 2 | 0 | 3 |
| D   | 18 | 17 | 15 | 0 |

#### Zweite Iteration:

Knoten A:

|     | A   | B   | C   | D   |
| --- | --- | --- | --- | --- |
| A   | 0   | 1   | 3   | 6   |
| B   | 1   | 0   | 2   | 5   |
|     |     |     |     |     |

Knoten B:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 6 |
| B   | 1 | 0 | 2 | 7 |
| C   | 3 | 2 | 0 | 7 |

Knoten C:

|     | A | B | C | D |
|-----|---|---|---|---|
| B   | 1 | 0 | 2 | 5 |
| C   | 3 | 2 | 0 | 7 |
| D   | 18 | 17 | 15 | 0 |

Knoten D:

|     | A | B | C | D |
|-----|---|---|---|---|
| C   | 3 | 2 | 0 | 7 |
| D   | 18 | 17 | 15 | 0 |

#### Dritte Iteration:

Knoten A:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0 | 1 | 3 | 8 |
| B   | 1 | 0 | 2 | 7 |

Knoten B:

|     | A | B | C | D |
|-----|---|---|---|---|
| A   | 0  | 1 | 3 | 8 |
| B   | 1 | 0 | 2 | 7 |
| C   | 3 | 2 | 0 | 7 |

Knoten C:

|     | A | B | C | D |
|-----|---|---|---|---|
| B   | 1 | 0 | 2 | 7 |
| C   | 3 | 2 | 0 | 9 |
| D   | 18 | 17 | 15 | 0 |

Knoten D:

|     | A | B | C | D |
|-----|---|---|---|---|
| C   | 3 | 2 | 0 | 7 |
| D   | 18 | 17 | 15 | 0 |



## Poisoned Reverse

Knoten A:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | 3 | 6 |
| B | 1 | 0 | 2 | 5 |

Knoten B:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | - | - |
| B | 1 | 0 | 2 | 5 |
| C | - | 2 | 0 | 3 |

Knoten C:

|   | A | B | C | D |
|---|---|---|---|---|
| B | 1 | 0 | 2 | - |
| C | 3 | 2 | 0 | 3 |
| D | - | - | 3 | 0 |

Knoten D:

|   | A | B | C | D |
|---|---|---|---|---|
| C | 3 | 2 | 0 | 3 |
| D | 6 | 5 | 3 | 0 |

### Erste Iteration

Knoten A:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | 3 | 6 |
| B | 1 | 0 | 2 | 5 |

Knoten B:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | - | - |
| B | 1 | 0 | 2 | 5 |
| C | - | 2 | 0 | 3 |

Knoten C:

|   | A | B | C | D |
|---|---|---|---|---|
| B | 1 | 0 | 2 | - |
| C | 3 | 2 | 0 | 15 |
| D | - | - | 3 | 0 |

Knoten D:

|   | A | B | C | D |
|---|---|---|---|---|
| C | 3 | 2 | 0 | 3 |
| D | 18 | 17 | 15 | 0 |


### Zweite Iteration

Knoten A:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | 3 | 6 |
| B | 1 | 0 | 2 | 5 |

Knoten B:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | - | - |
| B | 1 | 0 | 2 | 17 |
| C | - | 2 | 0 | 15 |

Knoten C:

|   | A | B | C | D |
|---|---|---|---|---|
| B | 1 | 0 | 2 | - |
| C | 3 | 2 | 0 | 15 |
| D | - | - | 15 | 0 |

Knoten D:

|   | A | B | C | D |
|---|---|---|---|---|
| C | 3 | 2 | 0 | 15 |
| D | 18 | 17 | 15 | 0 |


### Dritte Iteration

Knoten A:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | 3 | 18 |
| B | 1 | 0 | 2 | 17 |

Knoten B:

|   | A | B | C | D |
|---|---|---|---|---|
| A | 0 | 1 | - | - |
| B | 1 | 0 | 2 | 17 |
| C | - | 2 | 0 | 15 |

Knoten C:

|   | A | B | C | D |
|---|---|---|---|---|
| B | 1 | 0 | 2 | - |
| C | 3 | 2 | 0 | 15 |
| D | - | - | 15 | 0 |

Knoten D:

|   | A | B | C | D |
|---|---|---|---|---|
| C | 3 | 2 | 0 | 15 |
| D | 18 | 17 | 15 | 0 |

---


| Step | N'      | D(A),p(A) | D(C),p(C) | D(D),p(D) | D(E),p(E) | D(F),p(F) |
|------|---------|-----------|-----------|-----------|-----------|-----------|
| 0    | B       |    4,B    |    1,B    |   inf     |    inf    |    11,B   |
| 1    | BC      |    3,C    |    -      |   4,C     |    inf    |    11,B   |
| 2    | BCA     |    -      |    -      |   4,C     |    inf    |    11,B   |
| 3    | BCAD    |    -      |    -      |   -       |    7,D    |    10,D   |
| 4    | BCADE   |    -      |    -      |   -       |    -      |    9,E    |
| 5    | BCADEF  |    -      |    -      |   -       |    -      |     -     |


$$\lim_{x\to\infty} \frac{\sin\left(\frac{1}{x+1}\right)}{\sin\left(\frac{1}{x+2}\right)} = 1$$

---

$[1] [3]$

sm = $\alpha(1) + \alpha(3)$
sm = $1 + 3 - 4$
sm = $1 - 1 = 0$

$[\gamma(0/B), 0]$
$[0, 0]$

$[1][2]$

$sm = \alpha(1) + \alpha(2)$
$sm = 1 + 2 - 4$
$sm = -1$

$[\gamma(-1/B), 3]$
$[\gamma(-1/4), 3]$
$[\gamma(0), 3]$
$[3, 3]$



$[021] + [320]$

$i=0$
$sm = 1 + 0 + 0$
$c[1] = 0$
$s[0] = 1$

$i=1$
$sm = 2 + 2 + 0 = 4$
$c[2] = 1$
$s[1] = 0$

$sm = \alpha(0) + \alpha(3) + 1$
$sm = 0 + 3 - 4 + 1= 0$
$s[2] = 0$
$s[3] = \gamma(0/4) = 4$

---


$$\begin{align}
(a \oplus 1) \land b \land (c\oplus 1) \oplus a \land (b\oplus 1) \land c \oplus a\land b\land(c \oplus 1)\\

(((a \oplus 1) \land b) \land (c\oplus 1)) \oplus ((a \land (b\oplus 1)) \land c) \oplus ((a\land b)\land(c \oplus 1))\\


\end{align}$$


---



$$
a \lor b \implies a \land b
$$

---
## ROSY Fragen

- Pseudo befehle wo in der Pipeline?
- 2 ID IF -> no wait at branch

---

As the number of points increases, the columns of the Vandermonde matrix become more and more similar and thus less and less linear independent; for 10 points, the condition number is already $\approx 10^8$. In a sense, the system becomes more and more difficult to solve, leading to increasing problems in the application of numerical techniques. (This is quite typical behavior for many important numerical problems / techniques.)

To remedy this, let's apply the LU decomposition with partial pivoting to solve this system. The purpose of the pivoting is to increase the numerical stability of the algorithm.

Here is a slightly simpler algorithm for the LU decomposition than the one discussed in the lecture. It decomposes $PA = LU$ and does not detect singular $A$, but is easier to implement:

- - -
    
Input $A \in \mathbb{R}^{n \times n}$; Output $P,L,U$ such that $PA = LU$.

Let $U = I_n, L = I_n, P = I_n$ with $I_n$ being the identity matrix of dimension $n \times n$.

For $k = 1, \ldots, n$:
- find $k \leq i \leq n$ to maximize $|A_{ik}|$
- exchange rows $k$ and $i$ of $P$

Let $A' = P \cdot A$.

For $j = 1, \ldots, n$:
- For $i = 1, \ldots, j$: $U_{ij} = A'_{ij} - \sum\limits_{k=1}^{i-1}{U_{kj}L_{ik}}$
- For $i = j, \ldots, n$: $L_{ij} = \frac{1}{U_{jj}} \left(A'_{ij} - \sum\limits_{k=1}^{j-1}{U_{kj}L_{ik}}\right)$



$1 * 4 + 3 = 7$
$5*4 + 6 = 26$
$4*4 + 4 = 20$
$3*4 + 4 = 16$
$2*4 + 7 = 15$
$3*4 + 6 = 18$
$3*4 + 2 = 14$
$7*4 + 2 = 30$
$8*4 + 10 = 42$
$0*4 + 1 = 1$

---

$$\begin{align}
III:& -4 = 1+3s - 1t|-1\\
\iff& -5 = 3s -t|+t\\
\iff&-5+t = 3s|:3\\
\iff&\frac{-5 + t}{3} = s\\
\iff&s = \frac{-5 + t}{3}
\end{align}$$


$$\begin{align}
III:& -4 = 1+3s - 1t|-1\\
\iff& -5 = 3s - 1t|-3s\\
\iff& -5 -3s = -1t|:-1\\
\iff& 5 + 3s = t\\
\iff& t = 5+3s
\end{align}$$

$$\begin{align}
II:& 1 = -2 -1s + 2t| +2\\
\iff& 3 = -1s + 2t | t = 5 +3s\\
\iff& 3 = -1s + 2(5 + 3s)\\
\iff& 3 = -1s + 10 + 6s|-10\\
\iff& -7 = -1s + 6s\\
\iff& -7 = 5s|:5\\
\iff& -\frac{7}{5} = s\\
\iff&s = -\frac{7}{5}
\end{align}$$

---

$$\begin{align}
\left(\begin{matrix}3\\1\\-4\end{matrix}\right) = \left(\begin{matrix}2\\-2\\1\end{matrix}\right) + s \cdot \left(\begin{matrix}1\\-1\\3\end{matrix}\right) + t\cdot \left(\begin{matrix}-4\\2\\-1\end{matrix}\right)
\end{align}$$


$$\begin{align}
\left(\begin{matrix}3\\1\\-4\end{matrix}\right) - \left(\begin{matrix}2\\-2\\1\end{matrix}\right) =  s \cdot \left(\begin{matrix}1\\-1\\3\end{matrix}\right) + t\cdot \left(\begin{matrix}-4\\2\\-1\end{matrix}\right)
\end{align}$$

$$\begin{align}
\left(\begin{matrix}1\\3\\-5\end{matrix}\right)  =  s \cdot \left(\begin{matrix}1\\-1\\3\end{matrix}\right) + t\cdot \left(\begin{matrix}-4\\2\\-1\end{matrix}\right)
\end{align}$$


$$\begin{align}
s \cdot \left(\begin{matrix}1\\-1\\3\end{matrix}\right) + t\cdot \left(\begin{matrix}-4\\2\\-1\end{matrix}\right) = \left(\begin{matrix}1\\3\\-5\end{matrix}\right)
\end{align}$$



$$\left[\begin{array}{cc|c}
1 & 4 & 1 \\
-1 & 2 & 3\\
3 & -1 & -5
\end{array}\right]$$


$$\begin{align}
1s -4t = 1 |\cdot -1\\
-1s + 2t = 3 | \cdot -1\\
3s - 1t = -5| \cdot -1\\
\end{align}$$

$$\begin{align}
-1s +4t = -1\\
1s - 2t = -3\\
-3s + 1t = 5\\
\end{align}$$


$$\begin{align}
1s -4t = 1\\
-1s + 2t = 3\\
3s - 1t = -5
\end{align}$$

---


$$\left[\begin{array}{cc|c}
-3 & 0 & 1\\
3 & 0 & -1\\
2 & 4 & 4
\end{array}\right]$$

$III - II \cdot \frac{2}{3}$ 

$$\left[\begin{array}{cc|c}
-3 & 0 & 1\\
3 & 0 & -1\\
2 & 4 & 4
\end{array}\right]$$

---

$$\begin{align}
-3t + 0s = 1\\
3t + 0s = -1\\
2t + 4s = 4
\end{align}$$

$$\begin{align}
-3t + 0s = 1 | : -3\\
3t + 0s = -1\\
2t + 4s = 4
\end{align}$$
$$\begin{align}
&1t = -\frac{1}{3}\\
&3t= -1\\
&2t + 4s = 4| t = - \frac{1}{3}
\end{align}$$

$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
2\cdot -\frac{1}{3} + 4s = 4 
\end{align}$$
$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
-\frac{2}{3} + 4s = 4 | + \frac{2}{3}
\end{align}$$
$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
4s = 4 +\frac{2}{3}
\end{align}$$

$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
4s = 4 + \frac{2}{3}|:4
\end{align}$$

$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
s = 3\frac{1}{3}|:4
\end{align}$$
$$\begin{align}
1t = -\frac{1}{3}\\
3t= -1\\
s = \frac{5}{6}
\end{align}$$

---

$$f = \frac{n}{3}$$


$$\begin{align}
(\frac{n}{3}+1)\cdot n+1\\
(\frac{n}{3})^2 + 1 + 1\\
\frac{n^2}{9} + 2\\
\end{align}$$


---
Folie 148/152 Vorlesung Introduction to compilers
#klausur_rosy 

---

**Gauss-Seidel Update:**
The Gauss-Seidel iteration for solving $Ax = b$ can be expressed as:

$$ \mathbf{x}^{(k+1)}_{GS} = -(D+L)^{-1}U\mathbf{x}^{(k)} + (D+L)^{-1}\mathbf{b}$$

Here, $D$ is the diagonal matrix of $A$, $L$ is the strictly lower triangular part of $A$, and $U$ is the strictly upper triangular part of $A$

2. **Splitting the Matrix:**
   We can express $A$ as the sum of lower triangular ($L$), diagonal ($D$), and upper triangular ($U$) parts:
   $$A = D + L + U$$
   Rewrite the Gauss-Seidel update using this decomposition:
   $$\mathbf{x}^{(k+1)}_{GS} = -(D+L)^{-1}U\mathbf{x}^{(k)} + (D+L)^{-1}\mathbf{b}$$

3. **SOR Update:**
   Now, for the Successive Over-Relaxation method, we introduce an over-relaxation parameter $ \omega $:
   $$\mathbf{x}^{(k+1)} = (1-\omega)\mathbf{x}^{(k)} + \omega \mathbf{x}^{(k+1)}_{GS}$$
   Substitute the expression for $\mathbf{x}^{(k+1)}_{GS}$ from the Gauss-Seidel update:
   $$\mathbf{x}^{(k+1)} = (1-\omega)\mathbf{x}^{(k)} - \omega(D+L)^{-1}U\mathbf{x}^{(k)} + \omega(D+L)^{-1}\mathbf{b}$$

4. **Rearrange Terms:**
   Factor out $(D+L)^{-1}$ from the second term:
   $$\mathbf{x}^{(k+1)} = (1-\omega)\mathbf{x}^{(k)} + \omega(D+L)^{-1}(\mathbf{b} - U\mathbf{x}^{(k)})$$

   Now, the term $(D+L)^{-1}$ is common in both terms.

5. **Matrix Representation:**
   Let $M = (D+\omega L)$, then:
   $$\mathbf{x}^{(k+1)} = (1-\omega)\mathbf{x}^{(k)} + \omega M^{-1}(\mathbf{b} - U\mathbf{x}^{(k)})$$

   This is the form used in the code: $\mathbf{x}^{(k+1)} = (1-\omega)\mathbf{x}^{(k)} + \omega M^{-1}(\mathbf{b} - U\mathbf{x}^{(k)})$, where $M = D+\omega L$.

---

$$\begin{align}
\exists x((x < r \land x = y) \lor (x > r \land x = y))\\
((y < r) \lor (y > r))
\end{align}$$



---

$$\begin{align}
\left( \lbrace q_0 \dots q_{11}\rbrace, \lbrace1, \dots, 12\rbrace, \delta, q_0, \lbrace q_0\rbrace\right)
\end{align}$$


---


$$
a\cdot \left(\begin{array}{1}2 \\ -3 \\ -3\end{array}\right) + b \cdot \left(\begin{array}{1} 2 \\ 3 \\ -1 \end{array}\right) = 0
$$
---

$$\begin{align}
&S \to \text{axiom } F\text{\\n}S | \text{mp } F F F\text{\\n}S | \epsilon\\
&F \to V|(F\_\implies\_F) |\neg F | \top | \bot\\
&V \to \lbrace \text{a,...,z}\rbrace V | \lbrace\text{a,...z}\rbrace
\end{align}$$
---

$$
A \implies A
$$
---

$$\begin{align}
((P \lor Q) \implies P) \lor (Q\land R)\\
(\neg (P \lor Q) \lor P) \lor (Q \land R)\\
((\neg P \land \neg Q) \lor P) \lor (Q\land R)
\end{align}$$

---

$$\begin{align}
&(a\lor b\lor c\lor d)\\
&(a\lor b\lor c \lor j_0) \land(\neg j_0 \lor d)
\end{align}$$


$$\begin{align}
a \leftrightarrow a\land b
\end{align}$$


---

$$\begin{align}
\frac{n^\alpha}{c^n}\\
\frac{e^{\alpha \cdot \ln n}}{e^{n \cdot \ln c}}\\
\frac{\alpha\cdot n^{\alpha-1}}{c^n \cdot \ln c}

\end{align}$$---

12/13 August

$$
\begin{align}
x < 3 \lor x < 5
\end{align}$$

---

$$\begin{align}
&Inf(ab) = Inf(a) | Inf(b) | Inf(a) \cdot Inf(b)\\
&Inf(ab) = \varepsilon | a | b | a \cdot b\\
&Inf(a | b) = a | b\\
&Inf(a^*) = a^*
\end{align}$$

$$\begin{align}
&aabb^*\\
&Inf(aabb^*) = Inf(aabb)^*\\
&Inf(aabb) = Inf(aa) | Inf(bb) | Inf(aa) \cdot Inf(bb)\\
&Inf(aa)  = Inf(a) | Inf(a) \cdot Inf(a)\\
&Inf(bb) = Inf(b) | Inf(b) \cdot Inf(b)\\
&Inf(a) = a | \varepsilon\\
&Inf(b) = b | \varepsilon\\
&Inf(aa) = a | \varepsilon | (a|\varepsilon) \cdot (a| \varepsilon)\\
&Inf(bb) = b | \varepsilon | (b|\varepsilon) \cdot (b| \varepsilon)\\
&Inf(aabb) = (a | \varepsilon | (a|\varepsilon) \cdot (a| \varepsilon)) | (b | \varepsilon | (b|\varepsilon) \cdot (b| \varepsilon)) |
\end{align}$$


---

$$\begin{align}
1 + 1\mathbb N\\
a + b \cdot n = 2x\\
n = \frac{2x}{a + b}
\end{align}$$

$$\begin{align}
(x \implies y)\\
(\neg x\lor y)
\end{align}$$
$$(x \implies (y \implies 0)) \implies 0$$


---

$$\begin{align}
&y = \frac{1}{2} (-s_1 + s_3 - 2x)\\
&s_1 = -2x - 2y + s_3\\
&s_3 = s_1 + 2x + 2y
\end{align}$$

---

$$\neg((\neg a \land b)\lor (b\land \neg d))$$

