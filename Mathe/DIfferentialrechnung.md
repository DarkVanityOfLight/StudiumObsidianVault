# Differentialrechnung
Sei $f: \mathbb R \supseteq [a,b] \rightarrow \mathbb R$ eine Funktion, sei $x_0 \in [a, b]$.
$f$ heißt differenzierbar in $x_0$, wenn der Grenzwert
$$
\lim_{x\to\infty} {f(x) - f(x_0) \over x-x_0}
$$
existiert. Wir bezeichnen diesen Grenzwert als Ableitung von $f$ in $x_0$ und schreiben $f'(x_0)$.
$f$ heißt differenzierbar auf $[a, b]$, wenn $f$ in jedem Punkt aus dem Intervall $[a,b]$ differenzierbar ist.
Der Quotient ${f(x) - f(x_0) \over f(x_0)}$, $X \not x_0$ heißt Differenzquotient.
Äquivalente Formulierung von (*):
$$\begin{align}
&h:= x-x_0 \\
&\lim_{h\to 0} {f(x_0+h) - f(x_0) \over h}
\end{align}$$
## Geometrische Interpretation
Geometrisch lässt sich die Ableitung einer Funktion $f$ an der Stelle $x_0$ als Tangentensteigung interpretieren:
$$\begin{align}
f(x_0+h) - f(x_0) \over h
\end{align}$$
ist die Steigung der Sekante durch die Punkte $(x_0, f(x_0))$ und $(x_0 ++ h, f(x_0+h))$. Der Grenzwert gibt die Steigung der Tangente in $x_0$ an.
![[differentierung]]
Berechnung der Gleichung der Tangente durch $(x_0, f(x_0))$:
$$\begin{align}
&t_{(x_0, f(x_0))}(x) = m \cdot x+c= f'\cdot x+c\\
Es\ gilt:\ &t_{(x_0, f(x_0))}(x_0) = f'(x_0) \cdot x_0+c= f(x_0) \\
\iff &c=f(x_0) -f'(x_0) \cdot x_0\\
Also:\ &t_{(x_0, f(x_0))}(x) = f'(x_0) \cdot x + f(x_0) - f'(x_0) \cdot x_0\\
&=f'(x_0) (x-x_0)+f(x_0)
\end{align}$$
### Beispiel
$$\begin{align}
f: &\mathbb R \to \mathbb R, f(x)=x^2, x_0 \in\mathbb R \\
&{f(x)-f(x_0) \over x-x_0} = {x^2-x_0^2 \over x - x_0} = {(x-x_0)\cdot(x+x_0) \over x-x_0} = x+x_0\\
&f'(x_0) = \lim_{x\to x_0} {f(x) -f(x_0) \over x-x_0} = \lim_{x\to x_0}(x+x_0) \\
&=\lim_{x\to x_0} x + \lim_{x\to x_0} = x_0 + x_0 = 2\cdot x_0
\end{align}$$

Sei $f: \mathbb R \supseteq[a,b] \rightarrow \mathbb R$ in $x_0 \in [a,b]$ differenzierbar.
Dann ist $f$ in $x_0$ [stetig](Folgen.md#Stetig).
- nicht stetig $\implies$ nicht differenzierbar
- Die Umkehrung gilt nicht. z.B Betragsfunktion stetig in $x_0 = 0$, aber nicht differenzierbar in $x_0 = 0$

## Differentiationsregeln
Sind $f, g$ in $x_0\in D_f \cap D_g$ differenzierbar, so sind auch $f+g$, $f-g$, $\lambda \cdot f(\lambda \in \mathbb R)$, $f \cdot g$ und $f\over g$(falls $g(x_0)\not = 0$) in $x_0$ differenzierbar und es gelten die folgenden Regeln:

### Summenregel
$(f\pm g)'(x_0) = f'(x_0) \pm g'(x_0)$
### Faktorregel
$(\lambda \cdot f)'(x_0) = \lambda \cdot f'(x_0)$
### Produktregel:
$(f \cdot g)'(x_0) = f'(x_0) \cdot g(x_0) + f(x_0) \cdot g'(x_0)$
### Quotientenregel
$({f\over g})'(x_0) = {f'(x_0)\cdot g(x_0) - f(x_0)\cdot g'(x_0) \over g(x_0)^2}, g(x_0) \not = 0$
### Kettenregel
Ist $h$ in $x_0$ differenzierbar und $g$ in $h(x_0)$ differenzierbar, so ist die ssoziativ,Kssoziativ,omposition $g \circ h$ in $x_0$ differenzierbar und es gilt
$$(g\circ h)'(x_0) = g(h(x_0))' = g'(h(x_0)) \cdot h'(x_0)$$
