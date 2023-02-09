

Bei dem [Ableiten von Potenzreihen](Abbleitungsregeln.md#Ableiten%20von%20Potenzreihen) haben wir gesehen, dass jede [Potenzreihe](Potenzreihe.md) in ihrem Konvergenzbereich eine beliebig oft differenzierbare Funktion liefert. Umgekehrt kann man auch jeder beliebig oft differenzierbaren Funktion $f$ eine Potenzreihe zuordnen. Dazu müssen wir die Koeffizienten $a_{n}$ festlegen. Soll die Potenzreihe die [Funktion](Mathe/Funktionen.md) $f$  darstellen, dann muss sie insbesondere in $x_{0}$ dieselben Ableitungen wie $f$ haben, es muss also gelten $a_{n} = \frac{f^{(n)}(x_{0})}{n!}$ für alle $n$. Deshalb definieren wir:


Ist $f: D\to\mathbb R$ eine in $x_{0} \in D$ beliebig oft differenzierbare Funktion, so heißt
$$T(x) = \sum\limits^{\infty}_{n=0} \frac{f^{(n)} (x_0)}{n!} (x-x_{0})^{n}$$
die Taylorreihe von $f$ in $x_{0}$./

Abgesehen von einer geschickten Wahl von $x_{0}$ haben wir keinen weiteren Spielraum bei der Darstellung von $f$ als [Potenzreihe](Potenzreihe.md). Im Folgenden werden wir sehen, dass diese Strategie oft funktioniert, aber manchmal eben auch nicht: Der [Konvergenzradius](Konvergenzradius.md) der Taylorreihe kann $0$ sein, und wenn sie konvergiert, dann nicht notwendigerweise gegen $f$.


## Taylorpolynom

Sei $f$ in $x_0$ mindestens k-mal [differenzierbar](Differenzierbarkeit.md) (d.h. $f'(x_{0),}..., f^{(k)}(x_0)$ existieren). Mit dem k-ten __Taylorpolynom__

$$T_{k}(x) = \sum\limits^{k}_{n=0} \frac{f^{(n)}x_{0}}{n!} (x-x_0)^n$$
ist das k-te Restglied der Taylorreihe von $f$
$$R_{k}(x) = f(x) - T_{k-1}(x)$$
Insbesondere gilt
$$T(x) = f(x) \iff \lim_{k\to\infty} R_{k(x)} = 0$$
denn $T(x) = \lim_{k\to\infty} T_{k}(x)$. Mit der folgenden Darstellung des Restglieds lässt sich oft die [Konvergenz](Konvergenz.md) der Taylorreihe beweisen

---

$$f: ]r, s[ \to \mathbb R]\qquad a \in ] r,s[]$$

## Lokale Minima

$$f(x) \ge f(a)$$

## Lokale Minima

$$f(x) \le f(a)$$

## Sattelpunkt

$$\begin{align*}
f(x) &< f(a) \qquad x < a\\
f(x) &> f(a) \qquad x > a\\
\text{oder}\\
f(x) &> f(a) \qquad x > a\\
f(x) &< f(a) \qquad x < a 
\end{align*}$$

## Notwendiges Kriterium

Sei $f: ]r, s[ \to \mathbb R$ differenzierbar, $a \in ]r, s[$ lokale Minima oder Maxima $\implies f'(a) = 0$


