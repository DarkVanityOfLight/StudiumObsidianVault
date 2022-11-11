> Kilian Lichtner, Jannis Lauterbach

## Aufgabe 1

### a)
$$\begin{align}
|M\cup N|&= |M| + |N| - |M\cap N| \\
|\forall x: x\in M \lor  x\in N| &= |M|+|N|-|\forall x : x\in M \land x\in N| \\
 &= |\forall x: x\in M \lor x\in N| +\\ 
 &\quad|\forall x: x\in M \land x\in N| - |\forall x: x\in M \land x\in N| \\
 &= |\forall x:x\in M \lor x \in N| \\
\end{align}$$
### b)
$$\begin{align}
|M \times N| = |M| \cdot |N|\\
|M| \cdot |N| = |M\times N|
\end{align}$$
## Aufgabe 2
$$\begin{align}
& \{1,3\} \in P({1,2,3}) & \text{wahr} \\
& \{1,3\} \subset P({1,2,3}) & \text{wahr} \\
& \emptyset \subset P({1,2,3}) & \text{wahr} \\
& |P({1,2,3})| = 8 & \text{wahr} \\
& |P({})| = 0 & \text{falsch} \\
& \emptyset \in P({1,2,3}) & \text{falsch} \\
\end{align}$$




## Aufgabe 3

$$\begin{align}
\sum^n_{k=1} k^2 = {n(n+1)(2n+1) \over 6}\\
\end{align}$$
IA:
$$A(1): \sum^{n}_{k=1} k^2 = 1 = {1(1+1)(2\cdot 1 + 1)\over 6}$$
IV: Für alle $n \in \mathbb N$ gelte $A(n)$
IS:
$$\begin{align}
\sum^{n+1}_{k=1} k^2 &=  {(n+1)(n+2)(2n+3)\over 6} \\
&= \underbrace{k^2}_{IV} + (n+1)^2 \\
&= {n(n+1)(2n+1) \over 6} + (n+1)^2\\
&= {n(n+1)(2n +1) + 6(n+1)^2 \over 6}\\
&= {(n+1)(n (2n+1) + 6(n+1)) \over 6}\\
&= {(n+1)(2n^2 +3n + 4n +6) \over 6}\\
&= {(n+1)(n (2n+3) + 2(2n+3)) \over 6}\\
&= {(n+1)(n+2)(2n+3)\over 6} \\
\square q.e.d
\end{align}$$
## Aufgabe 4

Turm verschieben(Ziel, Hilfsplatz, Startplatz)
    Wenn wir nur 1 Scheibe auf dem Startplatz haben verschiebe sie auf den Zielplatz, Zurückgeben
    Turm mit -1 Scheiben verschieben (Hilfsplatz, Zielplatz, Startplatz)
    Bewegung von letzter Scheibe von Startplatz auf Zielplatz
    Turm mit -1 Scheiben verschieben(Zielplatz, Startplatz, Hilfsplatz)


Die optimale Anzahl an Zügen ist $2^n -1$

$A: 2^n -1 = 2\cdot A(n-1) + 1$
IA: $A(1) = 2^1 -1 = 1 = 2\cdot 0 +1$
IV: Für $n\in \mathbb N$ gelte $A(n)$
IB: $A(n+1) = 2^{(n+1)} -1$
IS: 
$$\begin{align}
&A(n+1)=2 \cdot A(n) + 1\\
&=2\cdot (2^n -1) +1\\
&=2\cdot 2^n -2+1\\
&=2^{(n+1)} -1 \\
&\square q.e.d
\end{align}$$

## Aufgabe 5

$$\begin{align}
\sum_{k=1}^n k^3 = {n^2(n+1)^2 \over 4} = {1\over 4} n^4+ {1\over 2} n^3 + {1\over 4}n^2
\end{align}$$
IA: ...
IV: ...
IS: $$\begin{align}
&n\to n+1\\
&\sum_{k=1}^{n+1} k^3 = \sum^{n}_{k=n} k^3 + (n+1)^3\\
&= n^2
\end{align}$$

b)
```python

def sum(n):
    if n == 1:
        return 1

    return sum(n-1) + n^3

```