> Kris Grohe, Kilian Lichtner


## Aufgabe 1

$$\left(n \atop k \right) = \left( n\atop n -k\right)$$
$$(n+1)\left(n \atop k\right) = (k+1)\left(n+1 \atop k+1\right)$$
$$\sum^k_{j=0} \left(n \atop j\right) \left(m\atop k-j\right) = \left(n+m\atop k\right)$$
$$\left(n\atop k\right) = \frac{n!}{k!(n-k)!}$$
$$\left(n+1 \atop k+1\right) = \left(n\atop k\right) + \left(n\atop k+1\right)$$
$$\sum^n_{k=0} (-1)^k \left(n\atop k\right) = 0$$

$$|M_1 \cup \dots\cup M_n| = \sum^n_{k=1} (-1)^{k-1} \sum_{|T| = k} |M_T|$$
$$c_n = \frac{1}{n+1}\left( 2n \atop n\right)$$

$$\begin{align}
&B_n = \sum^n_{m=0} S(n , m)\\
\lor& B_0 = 0; B_{n+1} = \sum^n_{k=0} \left(n\atop k\right) B_k
\end{align}$$

$$\begin{align}
&S(n, m) = 0;S(n+1, m+1) = \sum^n_{k=m} \left(n \atop k\right) S(k, m)\\
\lor& S(n+1, m+1) = S(n, m) + (m+1) \cdot S(n, m+1)\\
\lor& S(n, m) = \frac{1}{m!} \sum^m_{k=0} (-1)^k \left(m \atop k\right) (m-k)^n
\end{align}$$

Es gibt 
$$\sum^m_{k=0} (-1)^k \left(m\atop k\right) (m-k)^n$$
geordnete Partitionen einer $n$ elementigen Menge in $m$ nichtleere Teilemengen.

Es gibt genau 
$$\left(n-1 \atop m-1\right)$$ geordnete Partitionen von $n$ in $m$ Zahlen.

## Aufgabe 2

_a)_

Basisfall: Wenn $m = 1$ dann gibt es exakt eine Partition von $n$, nämlich $(n)$

Rekrusionsfall:
Für $m>1$, iteriere über alle möglichen Werte des ersten Summanden $i$ von $1$ bis $n-m+2$, und bestimme rekursiv die Partitionen $p$ des verbleibenden Werts $n-\text{i}$ in $m-1$ geordnete positive Summanden, an alle Partitionen mit $i > p[0]$ hänge $i$ vorne an.

_b)_

$\text{partition}\;5\;1$
$$[[5]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;6\;2$
$$[[1, 5], [2, 4], [3, 3]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;5\;2$
$$[[1, 4], [2, 3]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;4\;2$
$$[[1, 3], [2, 2]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;3\;2$
$$[[1, 2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;2\;2$
$$[[1, 1]]$$

---

$\text{partition}\;7\;3$
$$[[1, 1, 5], [1, 2, 4], [1, 3, 3], [2, 2, 3]]$$


## Aufgabe 3
_a)_

Basisfall: Wenn $m = 1$ dann gibt es exakt eine Partition von $n$, nämlich $(n)$

Rekrusionsfall:
Für $m>1$, iteriere über alle möglichen Werte des ersten Summanden $i$ von $0$ bis $n$, und bestimme rekursiv die Partitionen $p$ des verbleibenden Werts $n-\text{i}$ in $m-1$ geordnete positive Summanden, an alle Partitionen mit $i > p[0]$ hänge $i$ vorne an.

_b)_

---

$\text{partition}\;7\;1$
$$[[7]]$$

---

$\text{partition}\;6\;1$
$$[[6]]$$

---

$\text{partition}\;5\;1$
$$[[5]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;7\;2$
$$[[0, 7], [1, 6], [2, 5], [3, 4]]$$

---

$\text{partition}\;6\;1$
$$[[6]]$$

---

$\text{partition}\;5\;1$
$$[[5]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;6\;2$
$$[[0, 6], [1, 5], [2, 4], [3, 3]]$$

---

$\text{partition}\;5\;1$
$$[[5]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;5\;2$
$$[[0, 5], [1, 4], [2, 3]]$$

---

$\text{partition}\;4\;1$
$$[[4]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;4\;2$
$$[[0, 4], [1, 3], [2, 2]]$$

---

$\text{partition}\;3\;1$
$$[[3]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;3\;2$
$$[[0, 3], [1, 2]]$$

---

$\text{partition}\;2\;1$
$$[[2]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;2\;2$
$$[[0, 2], [1, 1]]$$

---

$\text{partition}\;1\;1$
$$[[1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;1\;2$
$$[[0, 1]]$$

---

$\text{partition}\;0\;1$
$$[]$$

---

$\text{partition}\;0\;2$
$$[]$$

---

$\text{partition}\;7\;3$
$$[[0, 0, 7], [0, 1, 6], [0, 2, 5], [0, 3, 4], [1, 1, 5], [1, 2, 4], [1, 3, 3], [2, 2, 3]]$$

## Aufgabe 4
_a)_

Die Wahrscheinlichkeit das bei einem Wurf keine $6$ gewürfelt wird ist $\frac{5}{6}$, in $m$ Würfen ist die Wahrscheinlichkeit dann:
$$P(\text{keine 6})\left(\frac{5}{6}\right)^m$$

_b)_

$$\begin{align}
\left(\frac{5}{6}\right)^m < 0.5\\
m \cdot \ln\left(\frac{5}{6}\right) < \ln 0.5\\
m > \frac{\ln 0.5}{\ln\left(\frac{5}{6}\right)}\\
m > 3.80
\end{align}$$

Wir betrachten nur ganzzahlige $m$ also $m=4$.


## Aufgabe 5

_a)_

Für festes $f\in S_4$ seien zwei Ecken $a$ und $b$ äquivalent, wenn man durch mehrfaches Anwenden von $f$ die Ecke $a$ auf die Ecke $b$ abbilden kann.

Jedes Element $e\in\lbrace 1, 2, 3, 4\rbrace$ ist in genau einem Zykel. Wir schreiben $[e]$ für den Zykel des Elements(der der Äquivalenzklasse entspricht). Wir schreiben $|[e]|$ für die länge eines Zykels

__Reflexiv:__
Wir zeigen $m \sim m$.
Per Definition gilt $m\sim m \iff \exists n f^n(m) = m$, es gilt aber auch $f^0(m) = m$.

__Transitiv:__
Wir zeigen $m\sim l, l\sim n \implies m \sim n$

Da $m\sim l$ und $m\sim n$ gilt, gibt es $x, y$ sodass $f^x(m) = l$ und $f^y(l) = n$.
Daraus folgt $f^x(f^y(m)) = n \iff f^{x+y}(m) = n$. 

__Symmetrisch:__
Wir zeigen $m \sim n \implies n\sim m$

Da $m \sim n$, gibt es ein $x$ sodass $f^{x}(m) = n$. Sei $l = |[n]| = |[m]|$, 
Wir wählen $y = l-x$, per Definition von $f$ gilt dann $f^y(n) = m$ und damit $n \sim m$.

_b)_
Wir definieren $f$ über die Zykel:
$(1, 2, 3, 4)$ Zahlpartition: $4 = 1 + 1 + 1 +1$
$(4), (1, 2, 3)$ Zahlpartition: $4 = 1 + 3$
$(4, 3), (1, 2)$ Zahlpartition: $4 = 2 + 2$
$(3), (4, 1, 2)$ Zahlpartition: $4 = 1 + 3$
$(4, 3, 2), (1)$ Zahlpartition: $4 = 3+1$
$(3, 2), (4, 1)$ Zahlpartition: $4 = 2 + 2$
$(4, 2), (3, 1)$ Zahlpartition: $4 = 2 + 2$
$(2), (4, 3, 1)$ Zahlpartition: $4 = 1 + 3$
$(4), (3), (1, 2)$ Zahlpartition: $4 = 1+1+2$
$(4), (3, 2), (1)$ Zahlpartition: $4 = 1 + 2 + 1$
$(4), (2), (3, 1)$ Zahlpartition: $4=1 + 1 + 2$
$(4, 3), (2), (1)$ Zahlpartition: $4=2 + 1 +1$
$(3), (4, 2), (1)$ Zahlpartition: $4=1 + 2 + 1$
$(3), (2), (4, 1)$ Zahlpartition: $4=1 + 1 + 2$
$(4), (3), (2), (1)$ Zahlpartition: $4 = 1 + 1 + 1 + 1$
