Eine Floating Point Zahl wird durch zwei Natürliche Zahlen bestimmt, die Mantissa $M$ und der Exponent $E$, zusammen definieren sie die Floating Point Nummer $\langle M, E\rangle^\mathbb R_B := M \cdot B^E$ relativ zur Basis $B$.

## Multiplikation

Multipliziere die Mantissa und Addiere die Exponenten

## Division

Dividiere die Mantissa und Subtrahiere den Exponenten

---

> [!IMPORTANT] Wenn wir den Exponenten nicht Anpassen werden die Rundungsfehler zu gross

Nehmen wir an $E_2 < E_1$ dann:

$$\begin{align}
(M_1 \cdot B^{E_1}) + (M_2 \cdot B^{E_2})\\
= (M_1 \cdot B^{E_1}) + ((M_2 \cdot B^{E_2 -E_1}) \cdot B^{E_1})
\end{align}$$

deswegen muss $M_2$ um $E_1 - E_2$ Stellen geshifted werden bevor wir auf $M_1$ addieren. Dadurch kann es passieren das viele Stellen von $M_2$ verloren gehen.

---

Wir stellen die Mantisse als eine [Radix-B](Radix-B.md) Zahl dar und, den Exponenten als eine Radix-B Zahl mit einem bias $\beta$ (Excess-$\beta$)

$$\begin{align}
\langle[x_{e+m}, x_{e+m-1}, \dots, x_m, x_{m-1}, \dots, x_0]\rangle^\mathbb R_{B, m, e}\\
:= \underbrace{(-1)^{x_e+m}}_{\text{Sign}} \cdot \underbrace{\left(\langle[x_{m-1}, \dots, x_0]\rangle^\mathbb N_B \cdot B^{1-m}\right)}_{mantissa} \cdot B^{\underbrace{\langle[x_{e+m-1}, \dots, x_m]\rangle^\mathbb N_B -\beta}_{exponent}}
\end{align}$$

wobei
$\beta := MaxNat(e) \div 2 = (B^e -1) \div 2$
Wir nehmen an das $x_{e+m} \in \lbrace1,0\rbrace$


- Warum Multiplizieren wir mit der Mantissa $B^{1-m}$?
$M := \langle[x_{m-1}, \dots, x_0]\rangle^\mathbb N_B \cdot B^{1-m}$ ist eine [Fixed-Point Nummer](Fixed-Point%20Nummern.md), der Dezimalpunkt ist zwischen $x_{m-1}$ und $x_{m-2}$, also $0.0 \leq M \leq B-B^{1-m} < B$
- Warum Verwenden wir ein Explizites Zeichen für die Mantissa?
Dies vereinfacht den Vergleich von Floating-Point Zahlen, und ermöglicht einen Symmetrischen Darstellungsbereich.
- Warum verwenden wir Excess-$\beta$ als Exponenten?
Darum

## Vergleich

Der Vergleich von zwei Floating Point Zahlen benoetigt eine Normalisierte Zahl, dann koennen wir mit Radix-B Vergleich vergleichen:

- Vergleiche die Vorzeichen
- Vergleiche die Exponenten
- Vergleiche die Mantissa

## Negative Zahlen

Der Zahlen Bereich ist Symmetrisch durch ein ändern des Vorzeichens

## Normalisierung

Generell haben wir $M \cdot B^E = (M\cdot B^\lambda) \cdot B^{E-\lambda}$, die beste Präzession bekommen wir wenn wir alle Bits für die Mantissa verwenden $[x_{m-1}, \dots, x_0]$ wir wählen als $\lambda$ so, das $x_{m-1} \not = 0$ außer $x = 0.0$. Denn dann werden alle Stellen Verwendet wir haben also maximale Präzision.

> [!IMPORTANT] $M\cdot B^E$ ist normalisiert wenn $1 \leq M < B$


## Zahlenbereiche

### Normalisisert

#### Positiv


Exponent: $MaxNat(e) = (B^e - 1) -\beta$
Mantissa: $MaxNat(m) = (B^m -1) \cdot B^{1-m} = B-B^{1-m}$
-> $(B-B^{1-m} \cdot B^{(B^e -1) - \beta})$

Exponent: $-\beta$
Mantissa: $\langle[1, 0, \dots, 0]\rangle^\mathbb N_B \cdot B^{1-m} = 1.0$
-> $B^{-\beta}$

## Denormalisiert

Exponent: $E = -\beta$ 
Mantissa $(B^{m-1} -1) \cdot B^{1-m} = 1 - B^{1-m}$
-> $(1-B^{1-m}) \cdot B^{-\beta}$

Exponent: $E = -\beta$
Mantissa $\langle[0, \dots, 0, 1]\rangle^\mathbb N _B \cdot B^{1-m} = B^{1-m}$
-> $B^{1-m-\beta}$

## Konvertierung nach Floating-Point

### Normalisierung

Gegeben sei $x \in\mathbb R$ mit $x\not= 0$, berechne $S \in\lbrace1, -1\rbrace, 0 \leq M \in\mathbb R$ und $E\in\mathbb Z$ sodass:
$x = S\cdot M\cdot B^e$
$1 \leq M < B$
gilt.

```python

# Sign
if x < 0:
    S = -1
else:
    S = 1

M = S * x
E = 0

while M < 1:
    M *= B
    E -= 1

while M >= B:
    M /= B
    E += 1
```

Wir können die Werte auch direkt bestimmen:

$$S := \begin{cases}+1 : x > 0\\-1 : x < 0\end{cases}$$

$$E := \lfloor \log_B(|x|) \rfloor$$
$$M := |x| \cdot B^{-E}$$
$$x = S \cdot M\cdot B^{m-1} \cdot B^{1-m} \cdot B^{E' - \beta}$$
mit $E' := E + \beta$

### Overflows

Berechne $\beta:= MaxNat(e) \div 2 = (B^e - 1) \div 2$

Sollte $E+\beta \not\in\lbrace0, \dots, B^e - 1\rbrace$ können wir keine normalisierte Mantissa verwenden, stattdessen berechnen wir eine Denormalisiserte Zahl oder Werfen einen Overflow.

Wir definieren $M'$ und $E'$ so:

$$M' := \begin{cases}
M \cdot B^{E + \beta + m-1}: E + \beta < 0\\
\text{overflow}: E + \beta \geq B^e\\
M\cdot B^{m-1} : \text{sonst}
\end{cases}$$

$$E' := \begin{cases}
0 : E + \beta < 0\\
\text{overflow} : E + \beta \geq B^e
E + \beta : \text{sonst}
\end{cases}$$

Wir haben jetzt einen Overflow oder
- $x = S\cdot (M' \cdot B^{1-m}) \cdot B^{E' - \beta}$
- $E' \not = 0 \implies B^{m-1} \leq M' < B^{m}$ normalisiert
- $E' = 0 \implies 0 \leq M' < B^m$ denormalisiert

### Runden

Wir haben $S\in\lbrace+1, -1\rbrace$, $0 \leq M' < B^m$ mit $M' \in\mathbb R$ und
$E' \in \lbrace0, \dots, B^{e} -1\rbrace$ mit $x = S\cdot (M' \cdot B^{1-m}) \cdot B^{E' -\beta}$

Wir wandeln die Mantissa in eine $m$-Stellen [Fixed-Point](Fixed-Point%20Nummern.md) Zahl um.

Wir Runden $M'$ zur nächsten [Ganzen Zahle](Ganze%20Zahlen.md) $I_M := round(M')$

Sollte $I_M = B^{m-1} -1$ und $E' > 1$ gelten, definiere $M'' := B^m -1$  und $E'' := E'$

Sollte $I_M = -1$ und $E' = 0$ gelten:
$M'' := 0$ und $E'' := E'$

Sonst $M'' := I_M$ und $E'' = E'$

für gerade $B$ erhalten wir beim Runden zur nächsten geraden Zahl $I_M = B^{m-1} -1$

Zuletzt stelle $S$, $E''$ und $M''$ als Radix-B Zahl dar.

---

I think the best way to do this is as follows which is without remembering many complicated formulas:

1. Normalize the given number in that you haven/double it until the mantissa is between 1 and 2 while maintaining a product with a power of 2. Example: 0.2 = 0.2*2^0 = 0.4*2^{-1} = 0.8*2^{-2} = 1.6*2^{-3}
2. Convert the mantissa to radix 2: 1.6 = 1 + 1/2 + 1/16 + 1/32 + epsilon, i.e., **1**.**1001****1 + eps;** if you need four bits, compute five here (which is the additional red one called the rounding bit).
3. Consider the two representable numbers less and greater than the given number; in the example, these are 1.1001_2 * 2^{-3} and 1.1010_2 * 2^{-3}. Which is the nearest number? This is easily seen as follows: if eps=0, and the red digit is 1, we are exactly in the middle between two representable numbers, otherwise a red 1 tend to the upper number, and 0 to the lower one. Tie breaking is needed in case of the middle case which is done according to the rounding modes.
4. Rest depends on the rounding mode and whether you have a special case (denormal number, overflow, etc).


```python
def round(red, eps):
	if(red)
```