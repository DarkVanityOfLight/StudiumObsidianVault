## Aufgabe 2.1

Sei $X$ eine endliche Menge mit $n$ Elementen

1. Wie viele bijektive Abbildungen $X \to X$ gibt es? Beweisen Sie Ihre Behauptung.
2. Sei $Q$ ein Quadrat mit den Ecken $1, 2, 3, 4$
   Welche bijektiven Abbildungen $\lbrace1,2,3,4\rbrace \to\lbrace1,2,3,4\rbrace$ lassen sich geometrisch als Symmetrie (Drehung oder Spiegelung) von $Q$ interpretieren?

---
1. 
Es gibt $|X|!$ verschiedene Bijektive Abbildungen von $X \to X$

Induktionsbehauptung:

$$A: |X|!$$

Induktionsanfang:

$1! = 1$

Induktionsvoraussetzung:

$A$ gelte für ein beliebiges aber festes $X$.

Induktionsschritt:

Wenn die Aussage für $n$ Objekte gilt und ich will $n+1$ Objekte anordnen, dann kann ich aus jeder Anordnung der ersten $n$ Stück das $n+1$ Objekt entweder vor das 1. Stellen oder vor das 2. ( also zwischen 1. und 2. ) oder zwischen 2. und 3. etc. und kann das neue aber auch hinter das letzte stellen.

So erhalte ich aus jeder Anordnung der $n$ ersten dann $n+1$ verschiedene
Anordnungen für alle n+1 Objekte.

Weil das mit jeder Anordnung der ersten $n$ klappt, und auch jedes Mal etwas neues entsteht; denn das $n+1$ kommt ja unter den ersten $n$ nicht vor, erhält man die Anzahl der Anordnungen von $n$ Stück $\cdot (n+1)$ 
wegen Ind. vor. also  

$$N ! \cdot (n+1) = (n+1) !$$
2. 

Spiegelungen: 
$$\begin{align*}
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 4, 3,2,1\rbrace\\
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 2, 1, 4,3\rbrace\\
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 1, 4, 3, 2\rbrace\\
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 3, 2, 1, 4\rbrace\\
\end{align*}$$
Drehungen:
$$\begin{align*}
&\lbrace 1, 2, 3, 4\rbrace \to \lbrace 4, 1, 2 ,3\rbrace\\
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 3, 4, 1, 2\rbrace\\
&\lbrace1, 2, 3, 4\rbrace \to \lbrace 2, 3,4, 1\rbrace\\
\end{align*}$$

## Aufgabe 2.2

Zeigen Sie, dass $\mathbb Z^{2}$ zusammen mit der Addition und der Multiplikation 
$$\begin{align*}
(a,b) + (c, d) &= (a+c , b+d)\\
(a, b) \cdot (c, d) &= (ac - bd, ad + bc)
\end{align*}$$
zu einem kommutativen Ring mit $1$ wird. Dieser heißt Ring der Gaußschen Zahlen $\mathbb Z[i]$.
Welche Elemente von $\mathbb Z[i]$ haben ein Inverses bezüglich der Multiplikation?

---

$\mathbb Z^{2}$ mit $+$ ist eine abelsche Gruppe da die Operation:

1. Assoziativ ist: 
$$\begin{align*}
&((a, b) + (c, d)) + (e, f) = (a + c, b+d) + (e, f) = (a + c + e, b + d + f)\\
\iff& (a, b) + ((c, d))+ (e, f)) =  (a, b) + (c + e, d+ f) = (a + c + e, b + d + f)
\end{align*}$$
2. Ein neutrales Element existiert:
$$\begin{align*}
(0, 0)\\
(a, b) + (0, 0) &=  (a +0, b+0) =  (a, b)
\end{align*}$$
3. Es existiert ein inverses: 
$$\begin{align*}
(a, b) + (-a, -b) &= (a-a, b-b) = (0, 0)
\end{align*}$$

$\mathbb Z^{2}$ mit $\cdot$ ist eine abelsches Monoid da die Operation:

1. Assoziativ ist:
$$\begin{align*}
&((a,b) \cdot (c, d)) \cdot (e, f) = (ac - bd, ad+bc) \cdot(e, f) \\
&=  ((ac - bd) \cdot e - (ad+bc) \cdot f, (ac-bd) \cdot f + (ad + bc) \cdot e) \\
&=  ((ace -bde) - (adf + bcf), acf -bdf +ade +bce)\\

&(a, b) \cdot ((c, d) \cdot (e,f)) = (a, b) \cdot(ce - df, cf + de)\\
&=(a \cdot (ce -df) - b \cdot(cf+de), a \cdot (cf + de ) + b \cdot (ce -df))\\
&= ((ace -adf) -(bcf + bde), acf + ade + bce -bdf)
\end{align*}$$
2. Ein neutrales Element existiert:
$$\begin{align*}
&(a, b) \cdot (1, 0) = (a\cdot 1 -b \cdot 0, a\cdot 0 + b\cdot 1)\\
&= (a, b)
\end{align*}$$

Alle Elemente für in $\mathbb Z[i]$ die einen $ggT(x, i) = 1$ haben, haben auch ein inverses bezüglich der Multiplikation. 

   
## Aufgabe 2.3

1. Konstruieren Sie einen Körper mit genau zwei Elementen, indem Sie auf $K = \lbrace0,1\rbrace$ die Verknüpfungen $+$ und $\cdot$ spezifizieren.
2. Zeigen Sie, dass es einen Körper $K$ mit genau $4$ Elementen gibt, indem Sie die Verknüpfungstafeln der Addition und Multiplikation aufstellen.
   
Hinweis: Bezeichnen Sie die Elemente von $K$ als $0, 1, a, a+1$

---


1. 
XOR
| + | 1 | 0 |
|---|---|---|
| 1 | 0 | 1 |
| 0 | 1 | 0 |

AND
| * | 1 | 0 |
|---|---|---|
| 1 | 1 | 0 |
| 0 | 0 | 0 |

2. 
| +   | 0   | 1   | a   | a+1 |
|-----|-----|-----|-----|-----|
| 0   | 0   | 1   | a   | a+1 |
| 1   | 1   | 0   | a+1 | a   |
| a   | a   | a+1 | 0   | 1   |
| a+1 | a+1 | a   | 1   | 0   |

| *   | 0 | 1   | a   | a+1 |
|-----|---|-----|-----|-----|
| 0   | 0 | 0   | 0   | 0   |
| 1   | 0 | 1   | a   | a+1 |
| a   | 0 | a   | a+1 | 1   |
| a+1 | 0 | a+1 | 1   | a   |

## Aufgabe 2.4

Zeigen Sie:

1. Auf $M = \mathbb N_{0} \times \mathbb N_{0}$ ist durch 
   $$(a,b) \sim (c, d) \iff a+d = b+c$$
   eine Äquivalenzrelation gegeben.
2. Die Verknüpfungen Addition und Multiplikation 
   $$\begin{align*}
   [(a,b)] + [(c, d)] &= [(a+c, b+d)]\\
   [(a,b)] \cdot [(c, d)] &= [(a\cdot c + b\cdot d, a\cdot d + b\cdot c)]
   \end{align*}$$
   auf $\mathbb Z = (\mathbb N_{0} \times \mathbb N_{0}) \diagup \sim$ sind wohldefiniert, assoziativ, kommutativ und distributiv.

---
1. 
Reflexiv:
$$(a, b) \sim (a, b) \iff a+b = a+b$$
Transitiv:
$$\begin{align*}
&(a, b) \sim (c, d), (c, d) \sim(e, f) \implies (a, b) \sim (e, f)\\
\iff & a + d =  b +  c\qquad c + f = d + e\\
\iff &c = a + d - b \qquad c = d + e - f\\
\iff & a + d -b = d + e -f\\
\iff & a-b =  e-f
\end{align*}$$
Symmetrisch:
$$\begin{align*}
&(a,b) \sim (c, d) \iff a+ d = b + c\\
&(c, d) \sim (a, b) \iff b + c = a+d
\end{align*}$$
2. 
Die Addition ist wohldefiniert, da bei der Addition von Natürlichen Zahlen nie aus dem Raum der natürlichen Zahlen herausgeführt wird.
Das selbe gilt für die Multiplikation.

Assoziativ:
$$\begin{align*}
&([(a, b)] + [(c, d)]) + [(e, f)]  \sim [(a, b)] + ([c, d] + [e, f])\\
\iff & [(a + c, b+d)] +  [(e, f)] \sim [(a, b)] + [(c+e, d+f)]\\
\iff & [(a + c + e, b+d+f)] \sim [(a + c+ e, b + d+f)]\\
\iff & a + c +e + b+d+f  =  b+d +f +a+c+e
\end{align*}$$
$$\begin{align*}
&([(a, b)] \cdot [(c, d)]) \cdot [(e, f)] \sim [(a, b)] \cdot ([(c, d) ] \cdot [(e, f)])\\
&[(a\cdot c + b\cdot d, a \cdot d + b\cdot c)] \cdot [(e, f)] \sim [(a, b)] \cdot [(c \cdot e + d \cdot f , c\cdot f + d \cdot e)]\\
& [((a\cdot c + b \cdot d) \cdot e + (a \cdot d + b\cdot c) \cdot f), (a\cdot c + b\cdot d) \cdot f + (a\cdot d + b\cdot c) \cdot e] \\
&\sim[a\cdot(c\cdot e + d\cdot f) + b\cdot(c\cdot f + d\cdot e), a \cdot (c\cdot f + d\cdot e) + b \cdot (c\cdot e + d\cdot f)]\\
&[(ace  + bde) + (adf + bcf), (acf + bdf) + (ade + bce)] \\
&\sim [(ace + def) + (bcf + bde), (acf +ade) + (bce + bdf)] \iff\\
& ace + bde + adf +bcf + acf + ade + bce +bdf = acf + bdf +ade+bce +ace +def + bcf +bde\\
&
\end{align*}$$

Kommutativ:

$$\begin{align*}
&[(a, b)] + [(c, d)] = [(c, d)] + [(a, b)]\\
&[(a+c , b+d)] = [(c+a, b+d)]
\end{align*}$$

$$\begin{align*}
[(a, b)] \cdot [(c, d)] &= [(a\cdot c + b\cdot d, a\cdot d + b\cdot c)]\\
[(c, d)] \cdot[(a,b)] &= [(c \cdot a + d \cdot b,  d\cdot a + b\cdot c)]\\
\end{align*}$$

Distributiv:
$$\begin{align*}
&[(a, b)] \cdot ([(c, d)] + [(e, f)]) = ([(a, b)] \cdot [(c, d)]) + ([(a, b)] \cdot [(e, f)])\\
&[(a, b)] \cdot[(c + e, d + f)] = [(a\cdot c + b\cdot d, a\cdot d + b\cdot c)] + [(a\cdot e + b\cdot f, a\cdot f + e\cdot b)]\\
&[(a\cdot (c+e) + b \cdot (d+f), a\cdot (d+ f) + b \cdot(c+e))] = [(a\cdot c + b\cdot d + a\cdot e + b\cdot f, a\cdot d + b\cdot c + a\cdot f + e\cdot b)]\\
&[(ac + ae + bd + bf, ad + af + bc + be)] = [(ac + bd + ae+bf, ad+bc + af+eb)]
\end{align*}$$

## Aufgabe 2.5

Beschreiben und implementieren Sie ein Verfahren, das
1. Für eine ganze Zahl $n\in \lbrace-2^{r}, ..., 0, ... 2^{r} -1\rbrace$ die Zweierkomplementdarstellung in $r$ Bits und einem Vorzeichenbit berechnet.
2. Zwei Zahlen in Zweierkomplementdarstellung addiert. Wie können Sie einen arithmetischen Überlauf erkennen?

---

1. 
   Berechne das Einerkomplement
   Addiere 1 auf das Einerkomplement
   
2. Falls sich das erste Bit verändert ändert sich auch der Wertebereich (vorne 0 = positiv + 0, vorne 1 = negativ) 

## Aufgabe 2.6

Auf $M = \mathbb Z \times (\mathbb Z \setminus\lbrace0\rbrace)$  ist durch
$$(a,b) \sim (c, d) \iff a\cdot d = b\cdot c$$
eine Äquivalenzrelation gegeben. Zeigen Sie, dass die Verknüpfungen Addition und Multiplikation
$$\begin{align*}
[(a, b)] + [(c, d)] = [(ad + bc, bd)]\\
[(a, b)] \cdot [(c, d)] = [(ac, bd)]
\end{align*}$$
auf $\mathbb Q = M\diagup \sim$ wohldefiniert, assoziativ kommutativ und distributiv sind.

---



## Aufgabe 2.7
Schreiben Sie ein Programm, das $\mathbb Q$ abzählt.
Wie können Sie das Programm modifizieren, dass es eine bijektive Abbildung
$$\mathbb N \to \mathbb Q$$
konstruiert?

---


```fsharp
let rec countRationals (n: int) (d: int) =
    if d = 0 then 0
    elif n = 0 then 1 + countRationals (1, d)
    else countRationals (n-1, d+1) + countRationals (n, d-1)
```

Um eine solche bijektive Abbildung zu konstruieren könnte man die einzelnen Rationalen zahlen in einer Liste speichern, der Index($n\in\mathbb N_{0}$)korrespondiert dann zu der Rationalen Zahl, allerdings müssten wir dafür Doppelzählungen verhindern($\frac{1}{2} = \frac{2}{4} = \frac{4}{8}$).


## Aufgabe 2.8
Sei $M$ eine unendliche Menge. Zeigen Sie, dass es keine injektive Abbildung $\psi: 2^{M} \to M$  gibt.

---

Nehmen wir an es existiert eine solche Abbildung $\psi: 2^{M} \to M$, dann können wir eine Teilmenge $A\subseteq M$ konstruieren, indem wir $A = {x \in M : x \notin \psi(B) \text{ für } B \subseteq A}$ setzen. Anders gesagt, $A$ ist die Menge aller Elemente aus $M$, die nicht durch $\psi$ auf eine Teilmenge von $A$ abgebildet werde.

Da $\psi$ injektiv ist, muss es ein $a\in A$ geben, das auf ein bestimmtes $B \subseteq A$abgebildet wird. Dann haben wir aber $a\in A$ und $a\notin \psi(B)$ was im Widerspruch zur Definition von $A$ steht. Also kann es keine injektive Abbildung $\psi 2^{M} \to M$ geben.

Vereinfacht kann man auch zeigen das es mehr Elemente in $2^{M}$ gibt als in $M$ und daher keine injektive Abbildung existieren kann.


## Aufgabe 2.9

Zeigen Sie: Die Menge aller endlichen Teilmengen von $\mathbb N$ ist abzählbar.

Hinweis: Assoziieren Sie zu jeder endlichen Teilmenge eine Binärzahl.

---

Wir assozieren die Teilmenge mit einer Binärzahl die aus der Darstellung der Elemente der Teilmenge in aufsteigender Reihenfolge erstellt wird, also z.B $\lbrace1, 3, 4, 5\rbrace$ ist die Binärzahl $10111$.

