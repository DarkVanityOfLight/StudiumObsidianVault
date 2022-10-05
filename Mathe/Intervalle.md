# Intervalle

Für spezielle [Teilmengen](Mengen.md) der [reellen Zahlen](Reelle%20Zahlen.md), die Intervalle, gibt es noch eine besondere Notation:$$(a;b) = \{x \in R | a < x < b\}$$![](Intervall.jpg)
Da Intervalle immer [Teilmengen](Mengen.md) der [reellen Zahlen](Reelle%20Zahlen.md) sind, wird anstelle von $\{x \in R \ a<x<b\}$ auch kürzer $\{x|a<x<b\}$ geschrieben

## Abgeschlossene Intervalle
Das abgeschlossene Intervall von a bis b ist die [Menge](Mengen.md) aller [reellen Zahlen](Reelle%20Zahlen.md) zwischen a und b einschließlich der Randpunkte a und b, also: $$[a;b] = \{x \in R| a\leq x \leq b\}$$![](Abgeschlossenes%20Intervall.png)

## Schranken
- Ein $s \in R$ heißt obere Schranke für $M$ und $M$ heißt nach oben beschränkt wenn
$x \leq s$ für all $x \in M$.
- Ein $r \in R$ heißt untere Schranke für $M$ und $M$ heißt nach unten beschränkt wenn $x \geq r$ für alle $x \in M$
- M heißt beschränkt, wenn  $M$ sowohl nach oben als auch nach unten beschränkt ist.
- Eine obere Schranke $s$ für $M$ heißt Supremum(oder kleinste obere Schranke) von $M$, in Zeichen $s=sup\ M$, wenn für jede obere Schranke $u$ von $M$ gilt:$s \leq u$  Falls $s=sup\ M$ und $s\in M$, so heißt $s$ Maximum von $M$, in Zeichen $s=max\ M$
- Eine untere Schranke $r$ für $M$ heißt Infimum (oder größte untere Schranke) von $M$, in Zeichen $R = inf M$, wenn für jede untere Schranke $l$ von $M$ gilt: $r \geq l$.  Falls $r= inf M$ und $r\in M$, so heißt $r$ Minimum von M, in Zeichen $r = min M$.
### Beispiel
$$M = \{{1 \over x} | x\in R^+\}$$
Nach unten beschränkt:
$inf M = 0$ $0 \not\in M$
nach oben unbeschränkt
$$Z=\{1-{1\over n}| n \in N\}$$
nach unten beschränkt, $inf Z= 0$, $min Z = 0$
nach oben beschränkt, $sup Z = 1$, aber $1 \not \in Z$
deshalb besitzt $Z$ kein Maximum