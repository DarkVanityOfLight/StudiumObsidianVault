# Ungleichungen mit Beträgen sowie mit der Variable im Nenner eines Bruchs

## Beträge in Ungleichungen
Der [Betrag](Vorzeichen%20und%20Betrag.md) eines Terms $x-b$ ist so definiert:
$$|x-b| = \sqrt{(x-b)^2} = \left\{
x-b\ für\ x \geq b\atop
b-x\ für\ x<b
\right.$$
## Ungleichungen mit der Variable im Nenner eines Bruchs
Werte der Variablen $x$, an denen Terme nicht definiert sind, müssen vorab ausgeschlossen werden. Im ersten Beispiel sind alle $x \in R$ zu untersuchen, im zweiten ist $x=2$ auszuschließen (keine Division durch Null), im dritten Beispiel sind negative $x$ auszuschließen ($\sqrt{x}$ ist nur für $x\geq 0$ definiert) und auch $x=1$ ist auszuschließen (keine Division durch Null).
Um für die verbleibenden Werte von $x$ die Lösungsmenge zu bestimmen, ist es meist zielführend, die Ungleichung mit dem Nenner zu multiplizieren. Wenn der Nenner für alle x dasselbe Vorzeichen hat, erhalten wir dabei eine äquivalente Ungleichung. Wenn der Nenner aber verschiedene Vorzeichen hat, dann muss eine Fallunterscheidung gemacht werden, denn bei negativem Nenner kehrt sich bei der Multiplikation das Vergleichszeichen um, bei positivem Nenner bleibt es unverändert. In verschiedenen Bereichen der x-Werten erhalten wir unterschiedliche äquivalente Ungleichungen. Die folgenden Beispiele erläutern das Vorgehen.
$$1 \leq {2\over x^2+1}$$
Der Nenner $x^2 +1 \geq 1$ ist für alle $x \in R$ positiv. Multiplikation mit $x^2 +1$ ergibt die äquivalenten Ungleichungen $$x^2 + 1 \leq 2 \iff x^2 -1 \leq 0$$
Die quadratische Gleichung $x^2 -1 = 0$ hat die Lösungen $x_1 = -1$ und $x_2 = 1$. Die Lösungsmenge ist $$L = [-1;1]$$
$${1\over 1-x} > 3$$
Die Nullstelle des Nenners $x =1$ ist auszuschließen. Für $x < 1$ ist der Nenner positiv, für $x>1$ negativ. Deshalb gelten folgende äquivalente Umformungen
$$für\ x <1:{1\over1-x} > 3 \iff 1 > 3(1-x)\iff x > {2\over 3}$$
$$für x>1:{1 \over1-x} > 3\iff 1<3(1-x)\iff x < {2\over 3}$$
Die Ungleichung in der ersten Zeile ist für ${2\over 3} <x<1$ erfüllt, in der zweiten Zeile widersprechen sich die Bedingungen $x>1$ und $x<{2\over 3}$. Die Lösungsmenge ist $$L=({3\over3}; 1)$$
