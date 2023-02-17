Wollen wir eine Taylorformel entwickeln, dann müssen wir höhere Ableitungen berechnen. Es wäre schön, wenn wir eine Formel in Termen der partiellen Ableitungen erhalten könnten. Hier stellt sich die Frage, ob wir die Reihenfolge der partiellen Ableitungen berücksichtigen müssen. Das ist unter geeigneter Voraussetzung zum Glück nicht der Fall, wie der folgende Satz zeigt:

> Ist $f: D\to\mathbb R^{m}$ mit $D\subset \mathbb R^{n}$ zweimal stetig [differenzierbar](Differenzierbarkeit%20in%20der%20Multivariaten%20Analysis.md), dann gilt $$\frac{\partial}{\partial x_{i}} \frac{\partial}{\partial x_{j}} f = \frac{\partial}{\partial x_{j}} \frac{\partial}{\partial x_{i}} f$$

Für eine k-mal stetig differenzierbare [Funktion](Mathe/Funktionen.md) kommutieren alle partiellen Ableitungen bis zur Ordnung $k$.

Wir verwenden auf $\mathbb R^{2}$ die [partielle Ableitung](Differenzierbarkeit%20in%20der%20Multivariaten%20Analysis.md#Partielle%20Ableitung) $\frac{\partial}{\partial x_{1}} \frac{\partial}{\partial x_{2}} f$ und $\frac{\partial}{\partial x_{2}} \frac{\partial}{\partial x_{1}}$ ,
aber
$$\frac{\partial}{\partial x_{1}}\frac{\partial}{\partial x_{2}} f(0, 0) \not = \frac{\partial}{\partial x_{2}} \frac{\partial}{\partial x_{1}} f(0, 0)$$
Wir verwenden für Ableitungen die Multiindexnotation: Ist $\alpha = (\alpha_{1}, ..., \alpha_{n}) \in\mathbb N^{n}_{0}$ dann schreiben wir
$$\begin{align*}
|\alpha| &= \alpha_{1}+ ... + \alpha_{n}\\
\alpha! &= \alpha_{1}! \cdot ... \cdot \alpha_{n}!
\end{align*}$$
und für $x \in\mathbb R^{n}$
$$x^{\alpha} = x_{1}^{\alpha_{1}} \cdot ... \cdot x^{\alpha_{n}}_{n}$$
und für eine $|\alpha|$-mal stetig partiell differenzierbare Funktion
$$\frac{\partial f}{\partial x^{\alpha}} = \frac{\partial}{\partial x_{\alpha1}} ... \frac{\partial}{\partial x_{\alpha_{n}}} f$$
Im Folgenden schränken wir uns auf Funktionen $f: D\to\mathbb R$ mit $D\subset\mathbb R^{n}$ ein. Den allgemeinen Fall erhält man, indem man die einzelnen Komponentenfunktion betrachtet.

## Taylorpolynom

Ist $f: D\to\mathbb R$ mit $D\subset \mathbb R^{n}$ beliebig oft differenzierbar in $a\in D$, dann heißt
$$T_{k}(x) = \sum\limits_{|\alpha| \le k} \frac{1}{\alpha!} \frac{\partial f(a)}{\partial x^{\alpha}} (x-a)^{\alpha}$$
das k-te __Taylorpolynom__ von $f$

## Taylorreihe

$$T(x) = \lim_{k\to\infty} T_{k}(x)$$
heißt Taylorreihe von $f$.

---

Ist $f$ partiell differenzierbar und hat in $a$ ein lokales Minimum oder Maximum, dann gilt 
$$\triangledown f(a) = 0$$
Mit der Taylorformel und einer zum univariaten Fall analogen Darstellung  des Restglieds zeigt man dann:

> Sei $f$ zweimal stetig partiell differenzierbar mit $\triangledown f(a) = 0$ und $H = \text{Hess}f(a)$ ist positiv definit, d.h. $$x^{t} \cdot H \cdot x > 0$$
> für alle $x\in\mathbb R^{n}$ so ist $a$ ein lokales Minimum. Ist $h$ negativ definit d.h.
> $$x^{t} \cdot H \cdot x < 0$$
> für alle $x$, so hat $f$ ein lokales Maximum

---
 Die Eignenschaften positiv und negativ definit von $H$ kann man in Termen der [[Eigenwerte]] von $H$ charakterisieren: $H$ ist positiv definit falls alle Eigenwerte positiv sind(das selbe gilt fuer negativ). Diese Charakterisierung ist möglich, da sich symmetrische Matrizen durch einen Basiswechsel mittels einer orthogonalen Matrix diagonalisieren lassen.
 