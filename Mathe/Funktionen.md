Eine Funktion $f$ von $D_f \subseteq A$ nach $B$ ist eine Vorschrift, die jedem $x \in D$ genau ein Element von $B$, genannt $f(x)$, zuordnet. $D_f$ heißt Definitionsmenge von $f$.
$$\begin{align}
f: &A \supseteq D_f \rightarrow B \\ 
&x \mapsto f(x)
\end{align}$$
Die Menge $W_f = \{f(x)\}: x \in S \subseteq B$ heißt Werte menge von $f$ oder Bild von $f$
![funktion](funktion.png)


## Bild
Fuer eine Teilmenge $S \subseteq D_f$ heißt $f(S) = \{f(x) | x \in S\}$ das Bild von $S$ unter $f$.
Insbesondere also $f(D_f) = W_f$
![bild](bild.png)

## Urbild
Fuer eine Teilmenge $T \subseteq B$ heißt $f^-1(T) = \{x \in D_f | f(x) \in T\}$ das Urbild von $T$ unter $f$
![urbild](urbild.png)

## Injektiv
$f$ heißt injektiv, wenn für alle $x_1,x_2 \in D_f$ gilt: wenn $x_1 \not = x_2$, dann $f(x_1) \not = f(x_2)$. Mit anderen Worten: $f$ heißt injektiv, wenn je zwei verschiedene Elemente aus $D_f$ auf verschiedene Elemente von $B$ abgebildet werden.
Weitere äquivalente Formulierung:
>$f$ heißt injektiv, wenn aus $f(x_1) = f(x_2)$ für $x_1, x_2 \in D$ stets $x_1 = x_2$ folgt.

$$\forall x_1, x_2 \in D_f, f(a) = f(b) \implies a = b$$
![injektiv](injektiv.png)

##  Surjektiv
$f$ heißt surjektiv, wenn für alle $z \in B$ ein $x \in A$ existiert, so dass $f(x) = z$.
Mit anderen Worten: $f$ heißt surjektiv, wenn jedes Element von $B$ als Bild unter Funktion $f$ angenommen wird, d.h wenn Bild$(f)=B$.
$$\forall z \in B: \exists x \in A: f(x) = z$$
![surjektiv](surjektiv.png)

### Bijektiv
$f$ heißt bijektiv, wenn $f$ injektiv und surjektiv ist.

## Gerade
$f$ heißt gerade, wenn mit $x \in D_f$ ist und $f(-x) = f(x) \forall x \in D_f$.

## Ungerade
$f$ heißt ungerade, wenn mit $x \in D_f$ auch $-x \in D_f$ auch $-x\in D_f$ ist und $f(-x) = -f(x) \forall x \in D_f$ 

## Monotonie
### Monoton  Wachsend
$f$ heißt monoton wachsend, wenn aus $x_1, x_2 \in D_f$ mit $x_1 < x_2$ stets $f(x_1) \leq f(x_2)$ folgt.

### Streng Monoton Wachsend
$f$ heißt streng monoton wachsend, wenn aus $x_1, x_2 \in D_f$ mit $x_1 < x_2$ stets $f(x_1) < f(x_2)$ folgt.

### Monoton Fallend
$f$ heißt monoton fallend, wenn aus $x_1, x_2 \in D_f$ mit $x_1 < x_2$ stets $f(x_1) \geq f(x_2)$ folgt.

### Steng Monoton Fallend
$f$ heißt streng monoton fallend, wenn aus $x_1, x_2 \in D_f$ mit $x_1 < x_2$ stets $f(x_1) > f(x_2)$ folgt.


## Stellen
Sei $f: R \supseteq D_f \rightarrow R$ eine [reelle](Reelle%20Zahlen.md) Funktion.

Sei $b \in R$ beliebig
$x \in D_f$ heißt eine b-Stelle von $f$, wenn $f(x) = b$.

### Nullstelle
$x \in D_f$ heißt Nullstelle von f, wenn $f(x) = 0$

## Beschränkt
$f$ heißt nach oben beschränkt, wenn es ein $K \in R$ gibt, so dass $f(x) \leq K$ für alle $x\in D_f$. K heißt obere Schranke von $f$

f heißt nach unten beschränkt, wenn es ein $L \in R$, so dass $f(x) \geq L$ für alle $x \in D_f$. $L$ heißt eine untere Schranke von $f$
Siehe auch [Schranken](Intervalle.md#Schranken)
