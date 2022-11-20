## Aufgabe 1

### a)

$$\begin{align}
&M = \{1, 2, 3, 4, 5, 6, 7, 8\}\\
&N = \{a, b, c, d, e, f, g, h\}\\

&\phi_{2, |M \times N|}(\underbrace{1, 1, 1, 1, ..., 1}_{|M \times N|}) = 1\cdot2^0 +1\cdot 2^1 + ... + 2^{|M\times N|-1}\\
&= 2^{|M\times N|} -1\\
&= 2^{64} - 1\\
&= 18446744073709551616 -1\\
&= 18446744073709551615
\end{align}$$
### b)
$$\begin{align}
n \in \mathbb N_0\qquad 1 \not = \lambda \in \mathbb R\\
A(n) = \sum^{n}_{k=0} \lambda^k = {1-\lambda^{n+1} \over 1 -\lambda}
\end{align}$$
IA:
$$\begin{align}
&n = 0\\
&1 \not = \lambda \in \mathbb R\\
&\sum^{0}_{k=0} \lambda^0 = {1 - \lambda^{1} \over 1 -\lambda} \\
&1 = {1 - \lambda \over 1 - \lambda}\\
& 1 = 1
\end{align}$$

IV: Für ein beliebiges aber festes $n \in \mathbb N_0$ und ein beliebiges aber festes $1 \not = \lambda \in \mathbb R$gelte $A(n)$
IB: $A(n+1) = {1 - \lambda^{n+2} \over 1 - \lambda}$
IS: 
$$\begin{align}
&n \to n+1 \\
&\sum^{n+1}_{k=0} \lambda^{k}\\
=&\underbrace{\sum^{n}_{k=0} \lambda^{k}}_{IV} + \lambda^{n+1}\\
=& {1 - \lambda^{n+1} \over 1 -\lambda} + \lambda^{n+1}\\
=& {1-\lambda^{n+1} \over 1 - \lambda} + {\lambda^{n+1} \cdot (1 - \lambda) \over 1-\lambda}\\
=& {1 - \lambda^{n+1} \over 1-\lambda} + {\lambda^{n+1} - \lambda^{n+2} \over1 - \lambda}\\
=& 1 - \lambda^{n+2}\over 1 - \lambda\\
\blacksquare
\end{align}$$

## Aufgabe 2

## Aufgabe 3

## Aufgabe 4

## Aufgabe 5