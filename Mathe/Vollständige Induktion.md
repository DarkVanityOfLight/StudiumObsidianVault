
Angenommen wir haben für jedes $n\in\mathbb N_0$ eine beliebige Aussage $A(n)$ gegeben, und man hat gezeigt:

1) __Induktionsanfang:__ $A(0)$ ist wahr
2) __Induktionsschritt:__ Es gilt für jedes $n>0$, dass $$A(n-1) \text{ist wahr} \implies A(n) \text{ist wahr}$$
Dann ist $A(n)$ für alle $n\in\mathbb N_{0}$, denn wir haben eine Kette von Schlussfolgerungen

$$A(0)\text{wahr} \implies A(1)\text{wahr} \implies A(2) \text{wahr} \implies ...$$

Analog kann man natürlich vorgehen um Aussagen $A(n)$ für $n \ge n_{0}\in\mathbb Z$ zu beweisen. Man muss nur stets sicherstellen, dass man den Induktionsanfang $A(n_0)$ und alle verwendeten Folgepfeile in der Kette von Schlussfolgerungen

$$A(n_{0})\text{wahr} \implies A(n_{0} + 1)\text{wahr} \implies A(n_{0} +2) \text{wahr} \implies ...$$
bewiesen hat.

## Beispiel
![Summe von 1 bis n](Summe%20von%201%20bis%20n.md)