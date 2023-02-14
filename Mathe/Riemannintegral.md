
Eine [Funktion](Mathe/Funktionen.md) $f: [r, s]\to\mathbb R$ heißt __Treppenfunktion__, wenn es eine Unterteilung $r=t_{0} < t_{1} < ... < t_{n-1} < t_{n} = s$ des [Intervalls](Intervalle.md) $[r, s]$ gibt, sodass $f$ auf allen $]t_{i-1}, t_{i}[$ konstant ist.
Das __Riemannintegral__ (oder einfach Integral) von $f$ ist definiert als

$$\int^{s}_{r} f(x)dx = \sum\limits^{n}_{i=1} f(c_{i})\cdot (t_{i} - t_{i-1})$$
wobei $c_{i}\in ]t_{i-1}, t_{i}[$ beliebig.

An die Funktionswerte $f(t_{i})$ stellen wir keine Bedingung, und diese Spielen auch keine Rolle für das Integral. Anschaulich macht das Sinn, da die Fläche unter einem einzelnen Punkt gleich $0$. $f(t_{i})= 0$ ist.

---

Sei $f: [r, s]\to\mathbb R$ eine [beschränkt](Mathe/Funktionen.md#Beschränkt) [Funktion](Mathe/Funktionen.md). 
Sei 
$$O = \inf \left\lbrace \int^{s}_{r} g(x) | g: [r, s] \to\mathbb R\;\text{Treppenfunktion mit}\; g(x) \ge f(x)\forall x \right\rbrace$$
das [Infimum](Schranken.md) aller __Obersummen__ und 

$$U = \sup \left\lbrace \int^{s}_{r} g(x) | g: [r, s] \to\mathbb R\;\text{Treppenfunktion mit}\; g(x) \le f(x)\forall x\right\rbrace$$
das [Supremum](Schranken.md) aller __Untersummen__. Die Funktion $f$ heißt __Riemannintegrierbar__ (oder einfach integrierbar) auf $[r, s]$ wenn
$$O = U$$
und wir bezeichnen diese Zahl mit 
$$\int^{s}_{r}f(x)dx$$
## Beispiel

Wir zeigen, dass $\exp(x)$ auf $[0, 1]$ integrierbar ist mit
$$\int^{1}_{0}\exp(x)dx = \exp(1) -\exp(0)$$

### Beweis
Für festes $n\in\mathbb N$ bilden wir mittels der __äquidistanten Unterteilung__
$$t_{i} = \frac{i}{n}, i=0, ..., n$$
Treppenfunktionen, die $\exp(x)$ von oben und unten beschränken.
Mit der [geometrischen Summenformel](Geometrische%20Summenformel.md) koenne wir die Untersumme
$$\begin{align*}
U_{n} &= \sum\limits^{n}_{i=1} f(t_{i-1})(t_{i} - t_{i-1})\\
&= \frac{1}{n}\sum\limits^{n-1}_{i=0} \exp\left(\frac{1}{n}\right)^{i} &=  \frac{1}{n} \frac{1-\exp\left(\frac{1}{n}\right)^{n}}{1-\exp\left(\frac{1}{n}\right)}\\
&= \frac{1}{n} \frac{1-\exp(1)}{1-\exp\left(\frac{1}{n}\right)}
\end{align*}$$
berechnen, wobei $\exp\left(\frac{1}{n}\right)^{n}= 1$ nach der Funktionalgleichung der [Exponentialfunktion](Exponentialfunktion.md). Im Grenzwert erhalten wir 
$$\lim_{n\to\infty} U_{n} = \exp(1) -1$$
denn mit der [Regel von L'Hopital](Regel%20von%20L'Hopital.md) ist

$$\lim_{n\to\infty} \frac{\frac{1}{n}}{\exp\left(\frac{1}{n}\right) -1 } = \lim_{x\to 0} \frac{x}{\exp(x) - 1} = \lim_{x\to0} \frac{1}{\exp(x)} = 1$$
Ebenso erhalten wir eine Obersumme

$$\begin{align*}
O_{n} &= \sum\limits^{n}_{i=1} f(t_{i}) (t_{i} - t_{i-1})\\
&= \frac{1}{n} \sum\limits^{n-1}_{i=0} \exp\left(\frac{1}{n}\right)^{i+1} &= \frac{1}{n} \exp\left(\frac{1}{n}\right) \frac{1-\exp(1)}{1-\exp\left(\frac{1}{n}\right)}\\
\end{align*}$$
also mit $\lim_{n\to\infty} \exp\left(\frac{1}{n}\right) = 1$ wieder
$$\lim_{n\to\infty} O_{n} = \exp(1) -1$$
Wir haben somit eine [Folge](Mathe/Folgen.md) von Obersummen und eine [Folge](Mathe/Folgen.md) von Untersummen gefunden, die beide gegen $\exp(1) -1$ konvergieren. Da außerdem
$$O_{n} =\exp\left(\frac{1}{n}\right) U_{n} > U_{n}$$
folgt $O = U = \exp(1)-1$
Wie bei Treppenfunktionen gibt also das Integral eine mathematisch exakte Definition für die Fläche unter dem Funktionsgraphen. Das Beispiel illustriert ein allgemeines Prinzip:

> Jede Obersumme(oder Untersumme)  können wir als Näherung für das Integral betrachten. Diese lässt sich durch Verfeinern der Unterteilung des Integrationsintervalls verbessern.
>  Damit erhalten wir ein Verfahren zur numerischen Berechnung von Integralen. Allerdings gibt es dafür wesentlich effizientere Algorithmen. Beispielsweise können wir das arithmetische Mittel einer Ober- und Untersumme verwende.
>  Allgemein verwendet man statt Treppenfunktionen andere Klassen von Funktionen, die die gegebene Funktion genauer approximieren. Statt Treppenfunktionen(die stückweise konstant sind), kann man z.B. auch Funktionen betrachten, die stückweise durch [Polynome](Polynome.md) höheren Grades gegeben sind.

---

Es ist nahe liegend, dass für das Riemannintegral das Folgende gilt:

Seien $f, g: [r, s] \to\mathbb  R$ integrierbar. Es gilt:

1. Linearität des Integrals: $$\int^{s}_{r} (\lambda \cdot f(x) +\mu \cdot g(x))dx = \lambda \cdot \int^{s}_{r} f(x) dx +\mu \cdot g(x)dx$$ für alle $\lambda, \mu \in\mathbb R$
2. Additivität des Integrals: $$\int^{s}_{r}f(x)dx = \int^{t}_{r} f(x) dx + \int^{s}_{t} f(x)dx$$ für alle $t\in[r, s]$
3. Monotonie des Integrals: Ist $f(x) \le g(x)$ für alle $x$, dann $$\int^{s}_{r}f(x)dx \le \int^{s}_{r} g(x)dx$$
---

> Stetige Funktionen sind integrierbar

Allerdings ist nicht jede Funktion integrierbar.