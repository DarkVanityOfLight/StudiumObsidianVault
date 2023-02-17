Zur qualitativen Beschreibung des Verhaltens einer Funktion ist es oft nützlich, ihre Extremwerte, d.h. ihre Minima und Maxima zu bestimmen.

## Lokale Minima
Für eine [Funktion](Mathe/Funktionen.md) $f:]r, s[\to\mathbb R$ heißt $a\in]r, s[$ ein lokales __Minimum__, wenn es ein $\varepsilon > 0$ gibt mit 
$$f(x) \ge f(a)$$
für alle $|x-a| < \varepsilon$. 

## Lokale Maxima
Gilt dagegen
$$f(x) \le f(a)$$
so spricht man von einem lokalen __Maximum__.

## Sattelpunkte
Gilt

$$\begin{align*}
f(x) &< f(a)\; \text{für}\; x < a\;\text{und}\\
f(x) &> f(a)\;\text{für}\; x > a
\end{align*}$$
oder
$$\begin{align*}
f(x) &> f(a)\;\text{für}\; x < a\;\text{und}\\
f(x) &< f(a)\;\text{für}\; x>a
\end{align*}$$
dann spricht man von einem __Sattelpunkt__.

---

Über die Ableitung erhalten wir ein notwendiges Kriterium für ein lokales Minimum oder Maximum

> Ist $f:]r, s[\to\mathbb R$ [differenzierbar](Differenzierbarkeit.md) in $a \in ]r, s[$ und hat dort ein lokales Minimum oder Maximum, dann gilt
> $$f'(a) = 0$$

### Beweis

Ist $a$ ein lokales Minimum, so gibt es ein $\varepsilon > 0$ mit 
$$f(x) \ge f(a)$$
fuer alle $|x-a| <\varepsilon$. Dann ist
$$\frac{f(x)-f(a)}{x-a} \ge 0\;\text{für}\; x > a$$
und 
$$\frac{f(x) -f(a)}{x-a} \le 0\;\text{für}\; x < a$$
also
$$0 \ge \lim_{\begin{array}{}x\to a\\ x < a\end{array}} \frac{f(x) -f(a)}{x-a} = f'(a) = \lim_{\begin{array}{}x\to a \\ x > a\end{array}}\frac{f(x) -f(a)}{x-a} \ge 0$$
also
$$f'(a) = 0$$
Die Aussage fuer das Maximum zeigt man analog.

## Hinreichendes Kriterium

Ist $f: ]r, s[ \to\mathbb R$ mindestens k-mal differenzierbar, ist $f^{(k)}$ [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und
$$
f'(a) = ... = f^{(k-1)}(a) = 0\;\text{und}\; f^{(k)}(a) \not =0 
$$
mit $k\ge 2$, dann hat $f$ in $a$ ein
- lokales Maximum, wenn $k$ gerade ist und $f^{(k)}(a) < 0$
- lokales Minimum, wenn $k$ gerade ist und $f^{(k)}(a) > 0$
- einen Sattelpunkt, wenn $k$ ungerade ist


Insbesondere erhalten wir mit $k=2,3$ folgende Kriterien
- $f'(a) = 0$ und $f''(a) < 0 \implies$ lokales Maximum
- $f'(a) = 0$ und $f''(a) > 0 \implies$ lokales Minimum
- $f'(a) = f''(a) = 0$ und $f'''(a) \not = 0 \implies$ Sattelpunkt




