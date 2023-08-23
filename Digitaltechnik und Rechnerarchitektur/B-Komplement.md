
>[!IMPORTANT] Gegeben sei $X := [x_n, ..., x_0]$ mit $x \leq x_i < B$, wir definieren das $B-1$-Komplement als $\overline X:= [(B-1) -x_n, \dots, (B-1) - x_0]$

Deshalb gilt:
$\langle X\rangle^\mathbb N_B + \langle \overline X \rangle^\mathbb N_B - (B-1) \sum\limits^{n-1}_{i=0} B^i = B^n - 1$

>[!IMPORTANT]
> Wir definieren das B-Komplement als:
> Gegeben sei $X := [x_n, \dots, x_0]$ mit $0 \leq x_i < B$, wir definieren das B-Komplement von $x$ als $\langle \overline X \rangle^\mathbb N_B +1 := \langle[(B-1) - x_n, \dots, (B-1) - x_0)]\rangle^\mathbb N_B + 1$

Das B-Complement von $\langle X\rangle\mathbb N_B = 0$ benötigt eine weitere Stelle.


## Subtraktion durch Addition 

```python
def nat_sub_by_compl(x: List[int], y: List[int],
					 s: List[int], B: int):
    N = len(x)
    c = [0] * (N + 1)
    c[0] = 1
    
    for i in range(N):
        sm = x[i] + ((B - 1) - y[i]) + c[i]
        c[i + 1] = sm // B
        s[i] = sm % B
    
    s[N] = 1 - c[N]

```

Wenn ein Carry in `NatSub` 1 war ist es hier `0`
Es geschieht ein Overflow wenn $c[N]=0$ als wenn $s[N]=1$

---

Für $B=2b >1$ definieren wir:

$$\langle[x_{n-1}]\rangle^\mathbb Z_B := \langle[\alpha(x_{n-1}), x_{n-2},\dots, x_0]\rangle^\mathbb N_B = \alpha(x_{n-1}) \cdot B^{n-1} + \sum\limits^{n-2}_{i=0} x_i \cdot B^i$$

mit 

$$\alpha := \begin{cases}x : \text{ if } x < b\\x-B : \text{ if } x\geq b\end{cases}$$
$$\gamma(x) := \begin{cases}x : \text{ if } x \geq b\\x+B : \text{ if } x< b\end{cases}$$

für Radix-B Zahlen werden die Zahlen aus $nat\lbrace B\rbrace = \lbrace 0, \dots, B-1\rbrace$ genommen, bei B-Komplement, ist dies auch so nur die erste Linke Zahl wird als $int\lbrace b \rbrace = \lbrace-b, \dots, b-1 \rbrace$

B-Komplement Zahlen gehen von 
$$MaxInt_B(n) = \langle[b-1, B-1, \dots, B-1]\rangle^\mathbb Z_B = b\cdot B^{n-1} -1 $$
$$MinInt_B(n) = \langle[b, 0, \dots, 0]\rangle^\mathbb Z_B = -b \cdot B^{n-1}$$

## Vorzeichen


$$\langle[x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B < 0 \iff x_{n-1} \geq b$$


## Stellenerweiterung

Gegeben $\langle[x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B$ die eindeutig definierte Repräsentation mit $n + m$ Stellen ist:

$$x = \begin{cases}
\langle[0, \dots, 0, x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B : \text{ if } x_{n-1} < b\\
\langle[B-1,\dots, B-1, x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B : \text{ if } x_{n-1} \geq b
\end{cases}$$

## Vorzeichenwechsel

Für $x := \langle[x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B$ , definieren wir $C(x) := B^n - x$
Nehmen wir an wir haben $C(x) = \langle[y_{n-1}, \dots , y_0]\rangle^\mathbb N_B$ dann
haben wir für $y_{n-1} < b$:
$$-x = C(x) -B^n = (-1) \cdot B^n + \sum\limits^{n-1}_{i=0} y_i \cdot B^i = \langle[B-1, y_{n-1}, \dots , y_0]\rangle^\mathbb Z_B$$
und für $y_{n-1} \geq b$

$$-x = C(x) - B^n = (y_{n-1} - B) \cdot B^{n-1} + \sum\limits^{n-2}_{i=0} y_i \cdot B^i  = \langle[y_{n-1}, \dots , y_0]\rangle^\mathbb Z_B$$

Einfacher:

>[!IMPORTANT] Bilde das Komplement jeder Stelle
> $$\langle[x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B \rightarrow \langle[((B-1) - x_{n-1}), \dots , (B-1) - x_0]\rangle^\mathbb Z_B$$
> und Addiere $1$, füge eine führende Stelle an falls notwendig($0, B-1$)

## Modulo $B^k$

Es gilt:
$$\langle[x_{n-1}, \dots , x_0]\rangle^\mathbb Z_B = \langle[x_{n-1}, \dots , x_k]\rangle^\mathbb Z_B + \langle[x_{k-1}, \dots , x_0]\rangle^\mathbb Z_B$$

## Stellenanzahl

Jede [Natürliche Zahl](Natürliche%20Zahlen.md) kann als B-Komplement dargestellt werden, die anzahl an Stellen die dafuer benoetigt werden ist:
$$sizeOf(x) = \begin{cases}
1 +\lceil \log_B\left(\frac{x+1}{b}\right)\text{if } x > 0\\
1 : \text{if } x = 0\\
1 + \lceil\log_B\left(\frac{-x}{b}\right)\rceil \text{if } x <0
\end{cases}: $$

## Addition


```python
def int_add(x: List[int], y: List[int], s: List[int]):
    N = len(x)
    c = [0] * (N + 1)  # carry digits
    c[0] = 0
    for i in range(N - 1):
        sm = x[i] + y[i] + c[i]
        c[i + 1] = sm // B  
        s[i] = sm % B  

	# most significant digits
	# require alpha / gamma applications
    sm = alpha(x[N - 1]) + alpha(y[N - 1]) + c[N - 1]
    s[N - 1] = sm % B 
    s[N] = gamma(sm // B)
```

Nur der letzte Übertrag und das höchste Bit sind unterschiedlich.

## Subtraktion

```python
from typing import List

def IntSub(x: List[int], y: List[int], s: List[int]) -> None:
    N = len(x)
    c = [0] * (N + 1)  # carry digits
    c[0] = 0

    for i in range(N - 1):
        sm = x[i] - (y[i] + c[i])
        c[i + 1] = -(sm // 2)
        s[i] = sm % 2

    # Most significant digits require alpha/gamma applications
    sm = alpha(x[N - 1]) - (alpha(y[N - 1]) + c[N - 1])
    s[N - 1] = sm % 2
    s[N] = gamma(sm // 2)
```

Normalerweise werden $n$ Stellen von der Addition oder Subtraktion von $n$ Stelligen Nummern genommen, dann müssen wir untersuchen ob unser Ergebnis mit $n$ Stellen dargestellt werden kann, dies tun wir mit Stellenerweiterun:
$$s_n = 0 \land s_{n-1} < b \lor s_n = B-1 \land s_{n-1} \geq b$$

nehmen wir an das $s_n \in \lbrace0, B-1\rbrace$ gilt, erhalten wir:
- overflow wenn $s_n = 0 \land s_{n-1} \geq b$
- underflow wenn $s_n = B-1 \land s_{n-1} < b$

## Multiplikation

Wir gehen vor wie bei der Radix Multiplikation, nur müssen wir $\alpha$ auf das höchstwertigste Bit anwenden, dann betrachten wir die Summe aller Spalten modulo $B$

Jeder radix-B Multiplikationsalgorithmus kann für B-Komplement verwendet werden.

![bmult](bmult.png)

```python
def IntMulCRA(x: List[int], y: List[int], p: List[int]) -> None:
    B = 2  # Assuming base B is 2
    M = len(x)
    N = len(y)
    
    for j in range(N):
        c = 0
        for i in range(M):
            xin = alpha(x[i]) if i == M - 1 else x[i]
            yin = alpha(y[j]) if j == N - 1 else y[j]
            pin = alpha(p[i + j]) if i == M - 1 else p[i + j]
            sm = xin * yin + pin + c
            p[i + j] = sm % B
            c = sm // B
        p[M + j] = gamma(c)

```