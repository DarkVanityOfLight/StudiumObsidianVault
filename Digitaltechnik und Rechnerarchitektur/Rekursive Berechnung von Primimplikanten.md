

Für eine Formel $\varphi$, sei $\sqcap(\varphi)$ die Menge aller Primimplikanten.

Für eine Formel $\varphi$ über den Variablen $V$, gilt das folgende:

- Wenn $c_0$ und $c_1$ Implikanten von $[\varphi]^0_x$ und $[\varphi]^1_x$ sind, dann sind $\neg x \land c_0, x\land c_1$ und $c_0 \land c_1$ Implikanten von $\varphi$
- Wenn $\text{cube}_V(v \cup \lbrace x\rbrace, g) \in\sqcap(\varphi)$ dann $\text{cube}_{V}(v, g) \in\sqcap([\varphi]^1_x)$
- Wenn $\text{cube}_V(v, g \cup\lbrace x\rbrace) \in\sqcap(\varphi)$, dann $\text{cube}_V(v,g) \in\sqcap([\varphi]^0_x)$
- für einen beliebigen $\text{cube}_V(v,g) \in\sqcap(\varphi)$ mit $x \not\in(v\cup g)$ gibt es $c_0 \in\sqcap([\varphi]^0_x)$ und $c_1 \in \sqcap([\varphi]^1_x)$ sodass $\text{cube}_V(v, g) = c_0 \land c_1$

Daraus bilden wir eine Rekursive Berechnung von Primimplikanten durch das löschen von Cubes die Strikte Supersets von anderen Cubes sind.

$$\sqcap(\varphi) = \lbrace x\land c |c\in\sqcap([\varphi]^1_x) \rbrace \cup \lbrace \neg x\land c | c\in\sqcap([\varphi]^0_x)  \rbrace \cup (\sqcap([\varphi]^0_x) \cap \sqcap([\varphi]^1_x))$$


