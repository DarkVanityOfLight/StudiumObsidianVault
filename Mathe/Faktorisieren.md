# Lösen von Gleichungen durch Faktorisieren
Wir betrachten zwei [reelle Zahlen](Reelle%20Zahlen.md) a,b deren Produkt gleich Null ist: $ab  = 0$. Wenn $a$ von Null verschieden ist, können wir die Gleichung durch $a$ dividieren und erhalten $b = 0$. Analog folgt aus $b \neq 0$, dass $a = 0$ ist, d.h. mindestens eine der beiden Zahlen $a,b$ muss Null sein. Dies nennt sich Nullproduktregel. Dies impliziert die folgende Regel für zwei beliebige Terme.
> Das Produkt zweier Terme hat genau dort Nullstellen, wo mindestens einer der Faktoren eine Nullstelle hat.

Die Umformung eines terms in eine Produktform nennt man Faktorisierung des Terms. Faktoren der Form $x-a$, wobei $a$ eine [reelle Zahlen](Reelle%20Zahlen.md) ist, heißen [Linearfaktoren](Linearfaktorzerlegung%20und%20der%20Satz%20von%20Viëta.md).

## Faktorisierung durch Ausklammern 
Haben alle [Summanden](Die%20Grundrechenarten.md) eines Terms einen gemeinsamen Faktor, so lässt sich dieser ausklammern:$$4x^2 + 32x+12=4(x^2+8x+3)$$
Der allgemeine quadratische term ist durch Ausklammern als [Produkt](Die%20Grundrechenarten.md) aus der Zahl 4 und einem  quadratischen Term in [Normalform](Normalform.md) umgeformt worden.
Besonders nützlich ist es wenn beide Faktoren die Variable enthalten.
$$x^4+2x^3+3x^2=x^2(x^2+2x+3)$$
Die Faktoren sind quadratische Terme, die wir  mit den selben Methoden wie[Lineare Gleichungen](Lineare%20Gleichungen.md), [p-q-Formel und Diskriminante](p-q-Formel%20und%20Diskriminante.md) oder [Quadratische Ergänzung](Quadratische%20Ergänzung.md) lösen können.
$$\begin{align}
&x^4 + 2x^3 +3x^2 &=& 0\\
\iff&x^2(x^2+2x+3)&=&0\\
\end{align}$$$$\iff x^2=0\ oder\ x^2+2x+3 = 0$$
Da $x^2+2x+3 =0$ [keine Lösung hat](Linearfaktorzerlegung%20und%20der%20Satz%20von%20Viëta.md), ist die Gleichung nur bei $x^2 = 0$ erfüllt, also $L = \{0\}$.
## Faktorisieren mit Hilfe der binomischen Formeln
Terme der Form $a^2 - b^2$ sowie $\pm 2ab+b^2$ können mit den [binomische Formeln](Binomische%20Formeln.md) als Produkte von $(a+b)$ und $(a-b)$ geschrieben werden. Bei der Differenz von Quadraten, z.B. $x^2-9$, können wir mit der Wahl $a=x$ und $b=3$ die dritte binomische Formel anwenden und erhalten $$x^2-9=(x+3)\cdot (x-3)$$
Bei vollständigen Quadraten wie $x^2-3x +1$ wenden wir die erste oder zweite binomische Formel an, hier die zweite mit $a=x$ und $b=1$
$$x^2-2x+1 = (x-1) \cdot (x-1) = (x-1)^2$$
## Faktorisierung eines quadratischen Terms, wenn eine Nullstelle bekannt ist
Wenn bei einem quadratischen Term in [Normalform](Normalform.md) $x^2+px+q$ eine Nullstelle $x_1$ bekannt ist, dann besagt der [Satz von Viëta](Linearfaktorzerlegung%20und%20der%20Satz%20von%20Viëta.md), dass auch $x_2={q\over x_1}$ eine Nullstelle ist. Damit erhalten wir die Faktorisierung $x^2+px+q = (x-x_1) \cdot (x-x_2)$.

> Die Faktorisierung eines Terms gelingt nicht immer und muss durch Ausprobieren und Raten versucht werden.
> Für quadratische Gleichungen der Form $x^2+px+q=0$ gelingt das Faktorisieren mit Hilfe der [p-q-Formel](p-q-Formel%20und%20Diskriminante.md). Für die Spezialfälle $x^3+px^2+qx+r=0$ und $x^4+px^3+qx^2+rx+s=0$ gibt es komplizierte Formeln. Für $x^n + c_{n-1} \cdot x^{n-1}+...+c_1 \cdot x + c_0 = 0$ gibt es überhaupt kein systematisches Verfahren des Faktorisierens, falls $n \geq 5$ ist.