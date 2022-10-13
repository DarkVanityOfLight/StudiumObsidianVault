Beweise, dass für $n \in \mathbb N_{\geq 1}$ gilt:
$$\sum_{k=1}^n k^2 = {n \cdot (n+1) \cdot (2n+1) \over 6}$$
IA:
$$
\sum_{k=1}^1 1^2 = 1 = {1 \cdot (1 + 1)\cdot (2\cdot 1 +1) \over 6} = {2\cdot 3 \over 6} = 1
$$
IV: 
Für $n\in \mathbb R$ gelte $A(n)$

IS: $A(n+1)$ ist wahr da:
$$\begin{align}
&\sum_{k=1}^{n+1} k^2 + (n+1)^2 &|& k^2 mit\ der\ IV ersetzen\\
&\iff {n\cdot(n+1) \cdot (2n+1) \over 6} + (n +1)^2 &|&mit\ 6\ erweitern\\
&\iff {n \cdot (n+1) \cdot (2n+1)+6(n+1)^2 \over 6} &|& Ausklammern\\
&\iff {(n+1) \cdot (n \cdot (2n+1) + 6(n+1)) \over 6} &|& Ausmultiplizieren \\
&\iff {(n+1) \cdot (2n^2 +n+6n+6) \over 6} &|& 7n(6n+n)\ auseinander\ schreiben \\
&\iff {(n+1) \cdot (2n^2+3n+4n+6) \over 6} &|& Ausklammern\\
&\iff {(n+1) \cdot (n \cdot (2n+3) + 2 \cdot (2n+3)) \over 6} &|& Weiter\ Ausklammern \\
&\iff {(n+1) \cdot (n+2) \cdot (2n+3) \over 6} &|& Jetzt\ der\ linken\ Seite\ n+1\ auch\ einsetzen\\
&{(n+1) \cdot (n+2) \cdot (2n+3) \over 6} = {(n+1) \cdot (n+2) \cdot (2n+3) \over 6} q.e.d\blacksquare
\end{align}$$