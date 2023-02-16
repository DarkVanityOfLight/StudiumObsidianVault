Nehmen wir an wir haben eine Funktion $f(x)$ und einen Grenzwert $L$ also
$$\lim_{x\to a} f(x) = L$$
Dann gilt:

Für alle $\epsilon > 0$ existiert ein $\delta > 0$, sodass $0< |x-a| < \delta \implies |f(x) -L| < \epsilon$
Formal also:

$$\forall\epsilon > 0, \exists \delta > 0 \text{ sodass } 0 < |x-a| < \delta \implies |f(x) - L| < \epsilon$$

---
## Beispiel

$$\lim_{x\to 4} \sqrt{2x + 1} = \sqrt{2(4) + 1} = 3$$

$$\forall \epsilon > 0, \exists \delta > 0 \text{ sodass } 0 < |x-4| < \delta \implies |\sqrt{2x+1} - 3| < \epsilon$$
Sei $\epsilon = 0.2$

$$\begin{align*}
&\sqrt{x+1} = 3.2\\
&x = 4.62
\end{align*}$$$$\begin{align*}
&\sqrt{x+1} =  2.8\\
&x = 3.42
\end{align*}$$
$$\begin{align*}
&0 < |4.62 - 4|<\delta = 0.62\\
&0 < |3.42 - 4| < \delta = 0.58
\end{align*}$$
Wähle das kleinere $\delta$. Also $\delta = 0.58$ 


