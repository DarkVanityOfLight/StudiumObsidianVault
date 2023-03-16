
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