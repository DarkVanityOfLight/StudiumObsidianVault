Gegeben eine [Funktion](Mathe/Funktionen.md)
$$f:\mathbb R^{n} \times \mathbb R^{m} \to\mathbb R^{m}$$
suchen wir für ein gegebenes $x\in\mathbb R^{n}$ ein $y\in\mathbb R^{m}$ mit 
$$f(x,y) = 0$$
Im besten Fall erlaubt uns dies (eventuell nur lokal) eine Funktion
$$g: \mathbb R^{n} \to\mathbb R^{m}, x\mapsto y$$
zu finden mit
$$f(x, g(x)) = 0$$


--- 

Dadurch können wir die implizit gegebene Menge
$$M = \lbrace(x, y) \in\mathbb R^{n}\times \mathbb R^{m} | f(x, y) = 0\rbrace$$
parametrisch darstellen als
$$M = \lbrace (x, g(x) | x\in\mathbb R^{n}) \rbrace$$
Der Satz über implizite Funktionen gibt ein Kriterium in Termen der Ableitungsmatrix:

> Sei $f: D\to\mathbb R^{m}$ mit $D\subset R^{n} \times \mathbb R^{m}$ stetig differenzierbar und $(a,b) \in\mathbb R^{n}\times\mathbb R^{m}$ mit $$Df(a,b) = \left(\quad A\quad W\quad \right)$$
> mit $A\in\mathbb R^{m\times n}$ und $W\in \mathbb R^{m\times m}$. Ist $W$ invertierbar, dann gibt es ein $\varepsilon > 0$, und eine stetig differenzierbare Funktion
> $$g: U = B_{\varepsilon}(a) \to V = f(B_{\varepsilon} (a))$$
> sodass
> $$f(x, y) =0 \iff y = g(x)$$
> für alle $(x, y) \in U\times V$

Wir können also lokal die Gleichung $f = 0$ nach $y$ auflösen.