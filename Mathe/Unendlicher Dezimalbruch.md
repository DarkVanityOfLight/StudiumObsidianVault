Ein unendlicher Dezimalbruch ist eine Folge $(a_n)_{n\in\mathbb N_0}$ von  [Dezimalbruechen](Dezimalbruch.md)
$$\begin{align}
&a_0 = \pm s_0 \cdot 10^k\\
&a_1 = \pm s_0.s_1 \cdot 10^k\\
&\quad\vdots\\
&a_n = \pm s_0.s_1s_2...s_n \cdot 10^k\\
&\quad \vdots
\end{align}$$
mit festen Vorzeichen, $k \in \mathbb Z$ und einer Folge $(s_n)_{n\in\mathbb N_0}$ von Dezimalstellen $s_i \in \{0,...,9\}$.

## Beispiel
Als unendlicher Dezimalbruch wird $\sqrt 2$  dargestellt durch die Folge
$$\begin{align}
&a_0 = 1\\
&a_1 = 1.4\\
&a_2 = 1.41\\
&a_3 = 1.414\\
&a_4 = 1.4142\\
&\quad \vdots
\end{align}$$
mit $k=0$ und den Dezimalstellen

|i|0|1|2|3|4|
|-|-|-|-|-|-|
|$s_i$| 1|4|1|4|2|

---

Jedes Folgeglied eines unendlichen Dezimalbruchs kann man schreiben als Summe
$$a_n = \sum^{n}_{i=0} s_i \cdot 10^{k-i}$$
Eine Folge, die in einer solchen Summendarstellung gegeben ist, bezeichnet man auch als [Reihe](Reihe.md). 

---

Jeder unendliche Dezimalbruch ist eine Cauchyfolge.

### Beweis

Ist $(a_n)$ ein unendlicher Dezimalbruch, dann gilt für $n>m$
$$\begin{align}
|a_n -a_m| &= \sum^{n}_{i = m+1} s_i \cdot 10^{k-i}\\
& \leq \sum^{n}_{m+1}(10-1)10^{k-i} = \sum^{n}_{i=m+1}(10^{k-i+1} - 10^{k-i})\\
&=10^{k-m} - 10^{k-n} < 10^{k-m}
\end{align}$$
