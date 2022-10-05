# Aufgabe 1.1
a) $$n^2 + n +41 = Primzahl$$
IA: $$1^2 + 1+41 = 43$$
IV: Behauptung gilt für  $n\in N$
IS: $$\begin{align}
&(n+1)^2 + n +1+41\\
\iff& n^2 + 2n +1 +n +1+41\\
\iff& n^2+n+41+2n+2
\end{align}$$
Kein gutes Beispiel da Widerspruch nur durch ausprobieren eintritt.
b)$$\begin{align}
&A\setminus (B\cup C) = (A \setminus B) \setminus C \\
&x \in A \setminus (B\cup C) \\
\iff &x\in A \land x \not \in (B\cup C) \\
\iff &x\in A \land x\not \in B \land x \not \in C\\
\iff &x\in(A\setminus B) \setminus C \\
q.e.d \blacksquare
\end{align}$$
c) $$\begin{align}
A \setminus (B\setminus C) = (A \setminus B) \cup C

\end{align}$$
# Aufgabe 2.2
a)
$$\begin{align}
E &= (B \times C) \cap (C \times B) \\
  &= \{(0;0), (0;2), (2; 2), (2; 0), (4, 0); (4;2) \} \cap \{ (0; 0), (0;2), (0;4), (2; 0), (2;2), (2;4)\} \\
  &= \{(0;0), (0;2), (2;2), (2;0)\}
\end{align}$$
$$P(C) =\{\emptyset, (0), (2), (0;2)\} $$
b)
$$\begin{align}
&M \times M \times M\\
=&\{(0,0,0); (0,0,1); (0, 1, 0); (0, 1, 1); (1, 0,0); (1,0,1), (1,1,0), (1,1,1)\}
\end{align}$$
c) $$M = R^2 \setminus \{(x_1, x_2)\in R^2 | x_1 < x_2\}$$
