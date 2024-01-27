
Dies bezeichnet die [Theorie](Theorien%20der%20ersten%20Stufe.md) von $(\mathbb N; +, 1, 0)$.

Folgendes ist Presburgers Axiomatisierung von $(\mathbb N; +, 1, 0)$ 
1. $\forall x \neg(x+1 = 0)$
2. $\forall x(x +0 = x)$
3. $\forall x, y(x+1 = y+1 \to x = y)$
4. $\forall x, y(x + (y+1) = (x+y) + 1)$
5. $\forall x, y(x+(y+1) = (x+y)+1)$
6. $\varphi(0) \land \forall x(\varphi(x) \to \varphi(x+1)) \to \forall x\varphi(x)$ für jede FO-Formel $\varphi$ mit einer freien Variable

