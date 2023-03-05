Schreiben wir 
$$a_{j}= \pm  1 \cdot \prod^{s}_{i=1} p_{i}^{r_{ji}}$$
mit $p_{i}$ prim und $r_{ji} \ge 0$, dann ist 
$$ggT(a_{1}, ..., a_{t}) = \prod^{s}_{i=1} p_{i}^{\min\lbrace r_{ji} | j\rbrace}$$
(und fuer $kgV$ analog mit dem Maximum). Mit diesen Formeln sehen wir:

1. Zwei Zahlen $a, b \in\mathbb Z$ sind teilerfremd genau dann, wenn
   $$ggT(a,b) = 1$$
2. Für $a, b \in\mathbb N$ ist
   $$ggT(a, b) \cdot kgV(a,b) = a\cdot b$$
Eine wesentlich effizientere Methode zur Bestimmung des [größten gemeinsamen Teilers](Größter%20gemeinsamer%20Teiler.md) (und damit auch des [kleinsten gemeinsamen Vielfachen](Kleinstes%20gemeinsames%20Vielfaches.md)) liefert der Euklidische Algorithmus:

---

## Euklidischer Algorithmus

Seien $a_{1}, a_{2} \in\mathbb Z\setminus\lbrace0\rbrace$. Dann terminiert die sukzessive Division mit Rest
$$\begin{align*}
a_{1} &= q_{1} a_{2} + a_{3}\\
\vdots\\
a_{j}&= q_{j}  a_{j+1} + a_{j+2}\\
\vdots\\
a_{n-2} &= q_{n-2} a_{n-1} + a_{n}\\
a_{n-1} &= q_{n-1}a_{n} +0
\end{align*}$$
und

$$ggT(a_{1}, a_{2}) = a_{n}$$
Rückwärtseinsetzen dieser Gleichungen
$$\begin{align*}
a_{n}&= a_{n-2} -q_{n-2}a_{n-1}\\
\vdots\\
a_{3} &= a_{1} -q_{1}a_{2}
\end{align*}$$
liefert eine Darstellung
$$ggT(a_{1}, a_{2}) = u\cdot a_{1}+v\cdot a_{2}$$
mit $u, v \in\mathbb Z$. Die Berechnung dieser Darstellung bezeichnen wir auch als den __erweiterten Euklidischen Algorithmus__

## Beispiel

Wir bestimmen den $ggT$ von $66$ und $18$ mit Hilfe des Euklidischen Algorithmus, d.h. durch sukzessive Division mit Rest:

$$\begin{align*}
66 &= 3\cdot 18 + 12\\
18 &= 1\cdot 12 + 6\\
12 &= 2 \cdot 6 + 0
\end{align*}$$
Somit ist $ggT(66, 18) = 6$, denn von unten gelesen gilt
$$6 | 12 \text{ also } 6|18 \text{ 6|66 }$$
und von oben gelesen, ist $t$ ein Teiler von $66$ und $18$, dann
$$t|12 \text{ also } t|6$$
Weiter erhalten wir eine Darstellung von $ggT(36, 15)$ als $\mathbb Z$-[Linearkombination](Linearkombination.md) von $66$ und $18$

$$6 = 18 - 1\cdot 12 = 18 -1 \cdot(66-3 \cdot 18) = 4 \cdot 18 + (-1) \cdot 66$$