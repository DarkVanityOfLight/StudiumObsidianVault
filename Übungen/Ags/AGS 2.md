## Aufgabe 1
$\alpha$. $(A \land \neg C) \implies \neg B$ : Wenn der Herbst Sonnig ist und der Ertrag nicht gering ist, dann ist der Wein nicht teuer.

$\beta$. $(\neg A \lor B) \implies \neg C$ : Wenn der Herbst nicht Sonnig ist oder der Wein teuer ist dann ist der Ertrag nicht gering.

$\gamma$. $\neg(\neg A) \implies \neg C \land \neg B$: Wenn der Herbst (nicht nicht)sonnig ist dann  ist der Ertrag nicht gering und der Wein ist nicht teuer.

## Aufgabe 2
IB:
$$A:
\sum^{n}_{k=1}(6k -1) = 6\cdot\left({n(n+1) \over2}\right) -n
$$
IA:
$$\begin{align}
A(1) &= 6*1 -1 &=& 6\left({1(1+1) \over 2}\right) -1\\
&=  5 &=& 5
\end{align}$$

IV:
Für ein $n \in \mathbb N$ gelte $A(n)$

IS: $n \to n+1$
$$\begin{align}
&\sum^{n+1}_{k=1} (6k -1)\\
=& \underbrace{\sum^{n}_{k=1} (6k-1)}_{IV} + (6n-1)\\
=& {6n(n+1) \over 2} - n + (6n -1)\\
=& {6n(n+1) -2n + 2(6n-1) \over 2}\\
=& n(6n+6) -2n+2(6n-1) \over 2\\
=& {6n^2 +6n-2n+12n-2 \over 2}\\
=&6n^2 + 6n +12n -2n -2 \over 2\\
=& {6n^2 + 6n+12n \over 2} - {2(n+1)\over 2}\\
=&{6(n^2 +n + 2n) \over 2} - (n+1)\\
=&{6(n+1)(n+2) \over 2} - (n+1)
\end{align}$$

$$
{6(n+1)(n+2) \over 2} - (n+1)
$$