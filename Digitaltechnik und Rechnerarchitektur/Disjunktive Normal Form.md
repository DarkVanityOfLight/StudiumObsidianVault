

Eine Disjunktive Normalform sind mit oder Verknüpfte minterme aus und Verknüpfungen.

$$\bigwedge^n_{i=1}\bigvee^{m_i}_{j=1} \alpha_{i,j}$$



## Berechnen der DNF

Um aus einer Beliebigen Formel eine DNF zu erhalten folgt man diesen Schritten:

- Erstelle die [Negation Normal Form](Negation%20Normal%20Form.md)
- Wende die [Distributivgesetze](Distributivgesetz.md) an: $$\begin{align}
\alpha \land (\beta \lor \gamma) = \alpha \land \beta \lor \alpha \land \gamma\\
(\beta \land \gamma) \land \alpha = \alpha \land\beta \lor \alpha \land \gamma
\end{align}$$
- Definiere eine Variablen Ordnung und eine Minterm Ordnung
- Ordne neu
- Räume auf: $$\begin{align}
x_i \land x_i = x_i\\
x_i \land \neg x_i = 0\\
\neg x_i \land x_i = 0\\
\neg x_i \land \neg x_i = \neg x_i
\end{align}$$

## Kanonische DNF

DNFs müssen nicht unbedingt Kanonisch sein, vor allem Minimale Disjunktive Normalformen sind meist nicht kanonisch. Die Maximale Disjunktive Normalform jedoch ist Kanonisch.

Die Kanonische DNF kann einfach aus der Wahrheitstabelle abgelesen werden, dazu werden alle Minterme die eine erfüllende Belegung sind aufgelistet.
