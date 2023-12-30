
SR Flip Flops können durch eine überkreuzte Implementation von [Gattern](Gatter.md) implementiert werden:

![](Asynchrone%20SR%20Flip-Flops%202023-11-22%2014.06.01.excalidraw.md)

$$\begin{align}
\cases{
q_0^{(t+\delta)} := \neg(s^{(t)} \land q_1^{(t)})\\
q_1^{(t+\delta)} := \neg(r^t \land q_0^{(t)})
}
\end{align}$$

Der Zustandsautomat dazu ist folgender:

![](Asynchrone%20SR%20Flip-Flops%202023-11-22%2014.20.27.excalidraw.md)

Die Roten Zustände Oszillieren und die grünen Zustände sind Stabil.

$$\begin{align}
q_0^{(t+\delta)} := \neg (s^{(t)} \land q_1^{(t)})\\
q_1^{(t+\delta)} := \neg (r^{(t)} \land q_0^{(t)})
\end{align}$$
-> $q_1^{(t+2\delta)} := \neg(r^{t+\delta} \land \neg (s^{(t))} \land q_1^{(t)}))$

- Die Eingabe $\overline r s$ führt von jedem Zustand nach $\overline q_0 q_1$
- Die Eingabe $r\overline s$ führt von jedem Zustand nach $q_0 \overline q_1$
- Die Eingabe $\overline{rs}$ führt von jedem Zustand nach nach $q_0 q_1$
- Die Eingabe $rs$ bleibt in einem grünen Zustand oder Oszilliert zwischen $\overline q_0 \overline q_1$ und $q_0q_1$


![](Asynchrone%20SR%20Flip-Flops%202023-11-22%2014.15.53.excalidraw.md)

$$\begin{align}
\cases{
q_0^{(t+\delta)} := \neg(s^{(t)} \lor q_1^{(t)})\\
q_1^{(t+\delta)} := \neg(r^t \lor q_0^{(t)})
}
\end{align}$$

![](Asynchrone%20SR%20Flip-Flops%202023-11-22%2014.30.22.excalidraw.md)


Die Roten Zustände Oszillieren und die grünen Zustände sind Stabil.

$$\begin{align}
&q_0^{(t+\delta)} := \neg(s^{(t)} \lor q_1^{(t)})\\
&q_1^{(t+\delta)} := \neg(r^{(t)} \lor q_0^{(t )})\\
\rightarrow& q_1^{(t+2\delta)} := \neg r^{(t+ \delta} \land \neg (s^{(t)} \lor q_1^{(t)})
\end{align}$$


- Die Eingabe $\overline r s$ führt von jedem Zustand nach $\overline q_0 q_1$
- Die Eingabe $r\overline s$ führt von jedem Zustand nach $q_0 \overline q_1$
- Die Eingabe $\overline{rs}$ führt von jedem Zustand nach nach $q_0 q_1$
- Die Eingabe $rs$ bleibt in einem grünen Zustand oder Oszilliert zwischen $\overline q_0 \overline q_1$ und $q_0q_1$


Egal ob wir die Implementation mit NOR oder NAND Gattern haben, gilt
- Reset: $q_1^{(t+2\delta)} := 0 \text{ for } r^{(t+\delta)} \land \neg s^{(t)}$
- Set: $q_1^{(t+2\delta)} := 1 \text{ for } \neg r^{(t+\delta)} \land s^{(t)}$

Die Möglichkeit einer Oszillation besteht, für NOR Gatter mit der Eingabe $\neg r^{(t)} \land \neg s^{(t)}$ und mit NAND für die Eingabe $r^{t} \land s^{(t)}$, wenn die Eingabe allerdings in einem Stabilen Zustand passiert speichert sie nur den Momentanen Wert.
Wenn wir die Invariante $q_1^{(t)} \oplus q_0^{(t)}$ eines Stabilen Zustands brechen, bei NOR Gattern durch die Eingabe $r^{(t)} \land s^{(t)}$ und  bein NAND Gattern mit $\neg r^{(t)} \land \neg s^{(t)}$.

Deshalb verbieten wir die Eingabe $r^{(t)} \land s^{(t)}$ für NOR Gatter und $\neg r^{(t)} \land \neg s^{(t)}$ für NAND Gatter.
