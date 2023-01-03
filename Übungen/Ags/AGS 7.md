> Jannis Lauterbach, Gregor Stöbener, Kilian Lichtner

## Aufgabe 1

$$\begin{align}
&x \equiv 8 \mod 10\\
&x \equiv -1 \mod 21
\end{align}$$
---

$$\begin{align}
&21 \cdot x_1 \equiv 1 \mod 10 \implies x_1 = 1\\
&10 \cdot x_2 \equiv 1 \mod 21 \implies  x_2 = 19
\end{align}$$
---

$$\begin{align}
& x = 8 \cdot 21 \cdot x_1 + -1 \cdot 10 \cdot x_2\\
& x = 8 \cdot 21 \cdot 1 + -1 \cdot 10 \cdot 19\\
& x = -22
\end{align}$$

---

$$\begin{align}
-22 \mod 10 \cdot 21 = 188
\end{align}$$
---

$$\begin{align}
R = \{ 188 + z \cdot 210 | \forall z \in \mathbb Z\}
\end{align}$$

## Aufgabe 2

### a)

$$\begin{align}
\varphi: &\mathbb Z / (a \cdot b) \to \mathbb Z / a \times \mathbb Z / b\\
&\overline x \mapsto (\overline x, \overline x)\\
\end{align}$$

Seien $\overline x, \overline y \in \mathbb Z/(a, b)$

$$\varphi(\overline x + \overline y) = (\overline x + \overline y, \overline x + \overline y) = (\overline x + \overline x) + (\overline y + \overline y) = \varphi(\overline x) + \varphi(\overline y)$$

Injektiv

$$\text{Ker}(\varphi) = \{\overline x \in \mathbb Z / (a b)| \varphi(\overline x) = (\overline 0, \overline 0)\}$$
Sei $\overline x \in \text{Ker}(\varphi)$
-> $x = k_1 \cdot a \land x = k_2 \cdot b$
-> $kgv(a,b) = a \cdot b$ da $a, b$ teilerfremd
-> $x$ muss Vielfaches von $ab$ sein, $x = k \cdot a \cdot b$
$\implies \overline x = \overline 0 \& \text{ker}(\varphi) = \{\overline 0\}$
$\implies \varphi$ injektiv

Surjektiv:
Sei $(\overline y_a , \overline y_b) \in \mathbb Z/a \times \mathbb Z/b$
Wir erhalten die Kongruenz

$$\begin{align}
&x \equiv y_a \mod a\\
& x \equiv y_b \mod b
\end{align}$$

-> Nach Chin. Restsatz existiert eine Lösung, die eindeutig ist modulo $a \cdot b$
-> $\varphi$ ist surjektiv (Wir finden für jedes Element im Zielraum ein Urbild)

### b)
$(\overline 8, \overline {-11}) = (\overline 8, \overline 10) \in \mathbb Z/10 \times \mathbb Z/21$

$$\begin{align}
&x \equiv 8 \mod 10\\
&x \equiv 10 \mod 21
\end{align}$$
$ggT(10, 21) = 1 \cdot 21 + (-2) \cdot 10 = 1$
$x = 8 \cdot 1 \cdot 21 + 10 \cdot (-2) \cdot 10 = -32$
$-32 \equiv 178 \mod 210$

$\overline {178} \mapsto (\overline{178} = \overline 8, \overline{178} = \overline{10})$


## Aufgabe 3
### a)
$$
sign\left(
\begin{matrix}
1 & 2 & 3 & 4\\
3 & 4 & 2 & 1
\end{matrix}
\right)
$$
$$\begin{align}
sign&={3-4\over1-2}\cdot{3-2\over1-3}\cdot{3-1\over1-4}\cdot{4-2\over2-3}\cdot{4-4\over2-1}\cdot{2-1\over3-4} \\
&=-1
\end{align}$$

### b)
$$
\sigma=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7\\
2 & 1 & 5 & 6 & 4 & 3 & 7
\end{matrix}
\right)
$$
$$\begin{align}
sign(\sigma)=&{2-1\over1-2}\cdot{2-5\over1-3}\cdot{2-6\over1-4}\cdot{2-4\over1-5}\cdot{2-3\over1-6}\cdot{2-7\over1-7}\cdot \\ \\
&{1-5\over2-3}\cdot{1-6\over2-4}\cdot{1-4\over2-5}\cdot{1-3\over2-6}\cdot{1-7\over2-7}\cdot \\ \\
&{5-6\over3-4}\cdot{5-4\over3-5}\cdot{5-3\over3-6}\cdot{5-7\over3-7}\cdot \\ \\
&{6-4\over4-5}\cdot{6-3\over4-6}\cdot{6-7\over4-7}\cdot \\ \\
&{4-3\over5-6}\cdot{4-7\over5-7}\cdot \\ \\
&{3-7\over6-7} \\ \\
=&-{1\over6}\cdot 6 \cdot {1\over6} \cdot 1 \cdot -{3 \over 2} \cdot {3-7\over6-7} \\ \\
=& 1
\end{align}$$

---

$$
\tau=\left(
\begin{matrix}
1 & 3 & 4 & 2 & 5 & 7 & 6 \\
1 & 2 & 3 & 4 & 5 & 6 & 7
\end{matrix}
\right)
$$

$$\begin{align}
sign(\tau)=&{1-3\over1-2}\cdot{1-4\over1-3}\cdot{1-2\over1-4}\cdot{1-5\over1-5}\cdot{1-7\over1-6}\cdot{1-6\over1-7}\cdot \\ \\
&{3-4\over2-3}\cdot{3-2\over2-4}\cdot{3-5\over2-5}\cdot{3-7\over2-6}\cdot{3-6\over2-7}\cdot \\ \\
&{4-2\over3-4}\cdot{4-5\over3-5}\cdot{4-7\over3-6}\cdot{4-6\over3-7}\cdot \\ \\
&{2-5\over4-5}\cdot{2-7\over4-6}\cdot{2-6\over4-7}\cdot \\ \\
&{5-7\over5-6}\cdot{5-6\over5-7}\cdot \\ \\
&{7-6\over6-7} \\ 
=&1 \cdot -{1\over5} \cdot -{1\over2} \cdot 10 \cdot 1 \cdot {7-6\over6-7} \\
=& -1
\end{align}$$

---

$$
\sigma \circ \tau=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
2 & 5 & 6 & 1 & 4 & 7 & 3
\end{matrix}
\right)
$$

$$\begin{align}
sign(\sigma \circ \tau)=&{2-5 \over 1-2}\cdot{2-6 \over 1-3}\cdot{2-1 \over 1-4}\cdot{2-4 \over 1-5}\cdot{2-7 \over 1-6}\cdot{2-3 \over 1-7}\cdot \\ \\
&{5-6 \over 2-3}\cdot{5-1 \over 2-4}\cdot{5-4 \over 2-5}\cdot{5-7 \over 2-6}\cdot{5-3 \over 2-7}\cdot \\ \\
&{6-1 \over 3-4}\cdot{6-4 \over 3-5}\cdot{6-7\over 3-6}\cdot{6-3 \over 3-7}\cdot \\ \\
&{1-4 \over 4-5}\cdot{1-7 \over 4-6}\cdot{1-3 \over 4-7}\cdot \\ \\
&{4-7 \over 5-6}\cdot{4-3 \over 5-7}\cdot \\ \\
&{7-3 \over 6-7}\cdot \\ \\
=&-{1\over6}\cdot{-2\over15}\cdot-{5\over4}\cdot6\cdot-{3\over2}\cdot{7-3 \over 6-7} \\ \\
=&-1
\end{align}$$

---

$$
\tau \circ \sigma=\left(
\begin{matrix}
1 & 2 & 3 & 4 & 5 & 6 & 7 \\
3 & 1 & 5 & 7 & 2 & 4 & 6
\end{matrix}
\right)
$$
$$\begin{align}
sign(\tau \circ \sigma)=&{3-1\over1-2}\cdot{3-5\over1-3}\cdot{3-7\over1-4}\cdot{3-2\over1-5}\cdot{3-4\over1-6}\cdot{3-6\over1-7}\cdot \\ \\
&{1-5\over2-3}\cdot{1-7\over2-4}\cdot{1-2\over2-5}\cdot{1-4\over2-6}\cdot{1-6\over2-7}\cdot \\ \\ 
&{5-7\over3-4}\cdot{5-2\over3-5}\cdot{5-4\over3-6}\cdot{5-6\over3-7}\cdot \\ \\
&{7-2\over4-5}\cdot{7-4\over4-6}\cdot{7-6\over4-7}\cdot \\ \\
&{2-4\over5-6}\cdot{2-6\over5-7}\cdot \\ \\
&{4-6\over6-7} \\ \\
=&{1\over15}\cdot3\cdot{1\over4}\cdot-{5\over2}\cdot4\cdot{4-6\over6-7} \\ \\
=&-1
\end{align}$$


## Aufgabe 4

```python
from functools import reduce
import operator


def prod(l):
    return reduce(operator.mul, l)

def signum(l):
    
    permutations = []

    for i in l:
        for j in l:
            if i < j:
                permutations.append((i, j))

    product = prod(
    [(l[perm[0]-1] - l[perm[1]-1]) / (perm[0] - perm[1])
    for perm in permutations]
    )
    return int(round(product, 0))

print(signum([2, 1, 5, 6, 4, 3, 7]))
# 1
print(signum([1, 3, 4, 2, 5, 7, 6]))
# -1
print(signum([3, 1, 5, 7, 2, 4, 6]))
# -1
print(signum([2, 5, 6, 1, 4, 7, 3]))
# -1

```

## Aufgabe 5

$$\begin{align}
sign:& S_n \to (\{-1, 1\})\\
&sign(\sigma \circ \tau) = sign(\sigma) sign(\tau)
\end{align}$$
Seien $\sigma, \tau \in S_n$

$$\begin{align}
sign(\sigma \circ \tau) &=\prod^{n}_{i, j = 1, i < j} \frac{\sigma \circ \tau(i) - \sigma \circ \tau(j)}{i - j} \\
&= \prod_{i < j} \frac{\sigma \circ \tau(i) - \sigma \circ \tau(j)}{\tau(i) - \tau(j)} \cdot \frac{\tau(i) - \tau(j)}{i-j}\\
\end{align}$$
