Die Shannon normal Form wird oft auch als 'if-then-else' normal Form(INF) genannt.
In der Shannon normal form werden Boolische Funktionen mit der Hilfe der Konstanten $1,0$ und dem $if-then-else$([Shannon Operator](Shannon%20Operator.md)) Operator Dargestellt.


## Shannon's Decomposition Theorem
$$\varphi \iff x_i \land [\varphi]^1_{x_i} \lor  \neg x_i \land [\varphi]^0_{x_i}$$


---

Die Shannon Normalform wird durch das wiederholte Dekompositionieren aller Variablen erreicht. Danach Reduzieren wir noch $(\alpha \implies \varphi | \varphi)$ mit dem Äquivalentem $\varphi$

Wenn wir alle Cofaktoren mit der selben Variablenordnung Dekompositionieren erhalten wir eine Kanonische Shannon Normal form.
Auch Variablen muessen Dekompositioniert werden
$$\text{SNF}(x) = (x \implies 1 |0)$$
