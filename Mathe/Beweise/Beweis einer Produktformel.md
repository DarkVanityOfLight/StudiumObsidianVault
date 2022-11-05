Beweise, dass für $n \geq 2$ gilt:

$$\prod^n_{k=2} \left(1- {2\over k\cdot(k+1)}\right) = {1\over3} \cdot\left(1+ {2\over n}\right)$$

IA: 
$$\begin{align}
A(2) &= \prod^n_{k=2} \left(1- {2\over k\cdot(k+1)}\right)\\ &= \left(1- {2\over 2\cdot(2+1)}\right)\\
&=(1- {2 \over6})\\
&= 1 - {1\over3}\\
&={2\over 3} = {1\over3}\cdot({1+2\over2})
\end{align}$$
IV: 
Für $n\in \mathbb R | n \geq 2$ gelte $A(n)$

IS:
$$\begin{align}
&\prod^{n+1}_{k=2}\left(1- {2 \over k \cdot (k+1)}\right) = 
\underbrace{\prod^{n}_{k=2}\left(1- {2 \over k \cdot (k+1)}\right)}_{\text{Induktionsvoraussetzung einsetzen}} \cdot \left( 1- {2\over (n+1) \cdot(n+ 2)} \right)\\

=& {1\over3} \cdot\left(1+{2\over n}\right) \cdot\left(1-{2\over (n+1) \cdot (n+2)}\right)\\
=& \left({1\over3} + {2\over3 n}\right) \cdot \left(1-{2\over (n+1) \cdot (n+2)}\right)\\
=& {1\over3} - {2\over 3 \cdot (n+1) \cdot (n+2)} + {2\over 3n} - {4\over 3n \cdot (n+1) \cdot (n+2)}\\
=& {1\over3} - {2n \over 3 n\cdot(n+1) \cdot (n+2)} + {2\over 3n} - {4\over3n\cdot(n+1)\cdot(n+2)} \\
=& {1\over3} - {2n-4 \over 3n\cdot(n+1)\cdot (n+2)} + {2\over 3n}\\
=& {1\over3} - {2n-4 \over 3n\cdot(n+1)\cdot (n+2)} + {2(n+1)(n+2)\over 3n\cdot(n+1) \cdot (n+2)}\\
=& {1\over3} + {2(n+1)(n+2) - 2n-4 \over 3n\cdot(n+1) (n+2)}\\
=& {1\over3} +{2\cdot(n^2 + 2n +n+ 2) -2n -4 \over 3n(n+1)(n+2)}\\
=& {1\over3} +{2n^2 + 4n +2n +4 - 2n -4 \over 3n(n+1)(n+2)}\\
=& {1\over3}+ {2n^2 +4n \over 3n(n+1) (n+2)}\\
=& {1\over3} + {2n(n +2) \over 3n(n+1) (n+2)}\\
=& {1\over 3} + {2n \over 3n (n+1)} \\
=& {1\over3} + {2 \over 3(n+1)}\\
=& {1\over3} + ({2\over3} \cdot {2\over n+1})\\
=& 1
\end{align}$$

