
Die [Exponentialreihe](Exponentialreihe.md) $\exp: \mathbb R \to \mathbb R$ ist [stetig](Stetigkeit%20und%20Zwischenwertsatz.md) und streng monoton wachsend und $\exp(\mathbb R) = ]0, \infty[$. Somit gibt es eine Umkehrfunktion
$$\ln:]0, \infty[\to\mathbb R$$
genannt Logarithmusfunktion.

Als Umkehrfunktion ensteht der Graph von $\ln$ durch Spiegelung des Graphen von $\exp$ and der Diagonalen.

---

Das [Bild](Abbildungen.md#Bild) der Exponentialfunktion ist
$$\exp(\mathbb R) = ]0, \infty[$$

Aus der Funktionalgleichung der [Exponentialfunktion](Exponentialfunktion.md) erhalten wir sofort die Funktionalgleichung des Logarithmus:

Für alle $x, y > 0$ gilt
$$\ln(xy) = ln(x) + ln(y)$$

## Allgemeine Potenzen

Mit dem Logarithmus können wir allgemeine Potenzen definieren:

Für jedes $x > 0$ und $a\in\mathbb R$ sei 
$$x^{a} = exp(a\cdot \ln(x))$$
Für $n\in\mathbb N$ bezeichnen wir
$$\sqrt[n]{x} = x^{\frac{1}{n}}$$
auch als n-te Wurzel von x.


Aus der Definition folgt unmittelbar
$$\ln(x^{a}) = a \cdot ln(x)$$


Für $a\in\mathbb N$ haben wir bereits die in jedem [Ring](Ring.md) gültige Notation
$$x^{a} = \underbrace{x \cdot ... \cdot x}_{\text{a-mal}}$$
Diese stimmt mit der allgemeinen [Potenz](Potenz.md) überein, denn mit der Funktionalgleichung der Exponentialfunktion gilt
$$\begin{align*}
\exp(a\cdot\ln(x)) &= \underbrace{\exp(\ln(x) + ... + \ln(x))}_{\text{a-mal}}\\
&= \underbrace{\exp(\ln(x)) \cdot ... \cdot \exp(\ln(x))}_{\text{a-mal}}\\
&= \underbrace{x \cdot ... \cdot x}_{\text{a-mal}}\\
\end{align*}$$
Allgemeiner erhalten wir mit den Funktionalgleichungen von Logarithmus und Exponentialfunktion:
> Für alle $x, y > 0$ und $a, b \in\mathbb R$ gilt
> $$\begin{align*}x^{a+b} &= x^{a} \cdot x^{b}\\(xy)^{a} &= x^{a} \cdot y^{a}\\(x^{a})^{b} &= x^{a\cdot b}\end{align*}$$

---

Mit der Eulerschen Zahl
$$e^{x} = \exp(x \cdot \ln(e) = exp(x))$$
mit $\ln(e) = 1$


