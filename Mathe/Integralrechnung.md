# Integralrechnung
Sei $f: \mathbb R \to \mathbb R$ beschränkt mit $f(x) \geq 0$ für $x\in[a,b]\subseteq \mathbb R, a<b$.
Wir wählen eine Zerlegung des Intervalls $[a,b]$:
$$Z = (x_0, x_1,...,x_n), n\in \mathbb N, a=x_0 <x_1<x_{n-1}<x_n = b$$
## Obersumme
Wir definieren die Obersumme von $f$ bzgl. $Z$ als
$$OS(f, Z) := \sum_{i=1}^{n}(x_i - x_{i-1})\cdot sup\{f(x)|x \in [x_{i-1}, x_i]\}$$
## Untersumme
und die Untersumme von $f$ bzgl. $Z$ als 
$$US(f, Z):= \sum_{i=1}^n (x_i -x_{i-1}) \cdot inf\{f(x)|x\in [x_{i-1}, x_i]\}$$
## Oberintegral
Wir definieren das Oberintegral von $f$ als
$$OI(f) := inf\{OS(f, Z) | Z\ Zerlegung\ von\ [a,b]\}$$
## Unterintegral
und das Unterintegral von $f$ als

$$UI(f) := sup\{US(f, Z) | Z\ Zerlegung\ von\ [a,b]\}$$
dann gilt $UI(f) \leq OI(f)$.
$f$ heißt Riemann integrierbar auf $[a,b]$, falls $UI(f) = OI(f)$.
Dann heißt $$\int_a^b f(x)dx :=OI(f)\in \mathbb R$$
das Integral von $f$ auf $[a,b]$

## Stammfunktion
Eine Funktion $F: \mathbb R \to \mathbb R$ heißt Stammfunktion von $f$ auf $[a, b]$, wenn $F'(x) = \int f(x)dx$ und nennt F auch unbestimmtes Integral von $f$.
Zwei verschiedene Stammfunktionen einer Funktion unterscheiden such nur durch eine eine additive Konstante.

## Hauptsatz der Differential- und Integralarechnung
Sei $f:[a,b] \to \mathbb R$ eine stetige Funktion und sei  $F:[a,b]\to R$ eine Stammfunktion von $f$. Dann ist das bestimmte Integral von $f$ in den Grenzen von $a$ und $b$ gegeben als 
$$\int_a^b f(x)dx = [F(x)]^b_a = F(b) -F(a)$$
## Rechenregeln
- $\int^b_a f(x)dx = -\int^a_b f(x)dx$
- $\int^a_a f(x)dx = 0$
- $\int^b_a f(x)dx=\int^c_a f(x)dx + \int^b_c f(x)dx$ für $a\leq c\leq b$
- $\int^b_a \lambda f(x)dx = \lambda \cdot \int^b_a f(x)dx$ für $\lambda \in \mathbb R$
- $\int^b_a f(x)dx \leq \int^b_a g(x)dx$, wenn $f(x) \leq g(x) \forall x \in [a,b]$

## Partielle Integration
Seien $f$ und $g$ auf $[a,b]$ differenzierbar. Dann gilt
$$
\int^b_a f(x)g'(x)dx=[f(x) \cdot g(x)]^b_a - \int^b_a f'(x)g(x)dx
$$
