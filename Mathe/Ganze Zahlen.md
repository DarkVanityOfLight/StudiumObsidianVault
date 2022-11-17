Für jede natürliche Zahl 1, 2, ... lässt sich eine Gegenzahl konstruieren, sodass die Summe aus Zahl und Gegenzahl gerade Null ergibt. Sie wird durch Hinzufügen eines negativen Vorzeichens mit -1, -2, ... bezeichnet. Damit wird die [Menge](Mengen.md) der natürlichen Zahlen so vergrößert, dass damit auch Gleichungen wie $3 + x = 0$ gelöst werden können.

> Die Menge der ganzen Zahlen ist die Menge $$Z = \{...; -2; -1; 0; 1; 2;...\}$$

---

Eine Elegantere Möglichkeit eine ganze Zahl darzustellen ergibt sich durch die [Äquivalenzrelationen](Äquivalenzrelationen.md). Wir betrachten jede ganze Zahl als Tupel aus zwei [Natürliche Zahlen](Natürliche%20Zahlen.md):
$$
\mathbb Z := (\mathbb N_0 \times \mathbb N_0)/\sim \quad(a,b) \sim (c, d) :\iff (a+d) = (b+c)
$$
$$\begin{align}
&[(a,b)] + [(c, d)] := [(a+c , b+d)]\\
&[(a, b)] \cdot [(c, d)] := [(ac + bd, bc +ad)]\\
\end{align}$$
Dann: [Assoziativgesetz](Assoziativgesetz.md), [Kommutativgesetz](Kommutativgesetz.md), [Distributivgesetz](Distributivgesetz.md) gelten.
#übung 

$$
\underbrace{[(a, b)] + [(b,a)]}_{[(a+b, a+b)]} = [(0, 0)] =: 0
$$
Schreibe für $n\in \mathbb N_0$ dass $n=[(n, 0)]$
und $-n = [(0, n)]$
$\mathbb N_0 \hookrightarrow \mathbb Z$
$n \mapsto [(n, 0)]$

