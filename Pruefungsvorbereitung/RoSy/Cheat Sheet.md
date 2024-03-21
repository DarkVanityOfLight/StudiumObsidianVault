## Pipelining

|              | no forward, no bypass | no forward + bypass     | forward + bypass        |
| ------------ | --------------------- | ----------------------- | ----------------------- |
| after ALU    | $p_{WB} - p_{ID}$     | $(p_{wb} - p_{id}) - 1$ | $(p_{EX} - p_{ID}) - 1$ |
| after load   | $p_{WB} - p_{WB}$     | $(p_{WB} - p_{ID}) -1$  | $(p_{MA} - p_{ID}) - 1$ |
| after branch | $p_{WB} - p_{IF}$     | $(p_{WB} - p_{IF}) - 1$ | $(p_{EX} - p_{IF}) - 1$ |


## Speedup berechnen

Der Prozessor ohne Pipeline benötigt pro Befehl einen Takt, also dauert bei $M\text{ MHz}$ ein Takt $\Delta = \frac{1000}{M} ns$. Werden $n$ Befehle ausgeführt, so befinden sich darunter im Schnitt $\frac{a \cdot n}{100}$ ALU-Befehle, $\frac{se\cdot n}{100}$ Speicherbefehle, $\frac{su\cdot n}{100}$ Sprungbefehle und $\frac{so \cdot n}{100}$ sonstige Befehle. Daher müssen wir insgesamt die folgende Zahl an zusätzlichen nop-Anweisungen berücksichtigen:

Seien $x_i$ die anzahl an zusätzlichen Warte Takten und $y_i$ die Anzahl an Befehlen die diese brauchen

$$x_0 \cdot\frac{a \cdot n}{100} \cdot y_0 + x_1 \cdot \frac{se \cdot n}{100}\cdot y_1 + x_2 \cdot \frac{su \cdot n}{100} y_2 + x_3 \cdot \frac{so \cdot n}{100}\cdot y_3 = \frac{n_{nop}}{100}$$

Daher führt der Prozessor mit der Pipeline insgesamt $\frac{n_{nop}+100}{100} n = n_{nop1}$Befehle aus und es ergibt sich der folgende SpeedUp:
Mit $\tau$ als zusätzliche Wartezeit und $p$ die länge der Pipeline

$$S =  \frac{n\cdot\Delta}{n_p \cdot \left( \frac{\Delta}{p} + \tau \right)} $$
Der Prozessor ohne Pipeline führt pro Takt einen Befehl aus und führt somit $M$ Millionen Befehle pro Sekunde aus. Der Prozessor mit Pipeline hat einen SpeedUp von $\frac{800}{230}$ und führt somit $S \cdot M \text{ MIPS}$ aus

## Vergleiche für Pipelinekonflikte

$ID \times EX + ID \times MA$

## Ausfuehrungszeit

$\text{Zykluszeit: } \Delta = (1000/M)$
mit $M\; MHZ$

$$(\#\text{Anweisungen} + \text{laenge Pipeline} - 1) \times (\Delta \cdot \frac{1}{\text{Pipeline laenge}} + \text{zusaetzliche Wartezeit})ns$$

## Caching

Cache Größe: $C$
Hauptspeichergröße: $HS$
Cache Zeilengröße: $Z$
Assoziativität $A$

Hauptspeicher Addresslänge $AL = \log_2(HS)$
Cache Addresslänge $CA = \log_2(C)$

Anzahl an Blöcken im Cache: $NB = \frac{C}{Z}$

__Anzahl an Sätzen__: $NS = \frac{C}{Z \cdot A}$

__Anzahl an Blöcken pro Satz__ $\frac{NB}{NS}$
__Anzahl an Satz Bits__: $NSB = \log_2(NS)$

__Anzahl an Tag Bits__: $NTB = AL - NSB$

### Direct Memory Mapping

$adr_k(a_l) := (a_l \mod size_k)$
$tag_k(a_l) := (a_l \text{ div } size_k)$
$a_l := tag_k[i] \times size_k + i$

## Block-Oriented

Adresse $a_l$ gehört zu block $a_l \text{ div } B$

Sei $s^b, s^k$ die Block/Cache groeßese
$block_k = sentence_k = a_l \text{ div } s^b \mod \#\text{Sentences}$
$tag_k(a_l) := (a_l \text{ div } s^b) \text{ div } \#\text{Sentences}$
$adr_k(a_l) := (a_l \text{ div } 2^b) \mod \#\text{Sentences}$


## Liveness
(Rueckwaerts)
$$Live(l_t) = Read(l_t)\cup (Live(l_{t+1} \setminus Write(l_t)))$$

Fixpunktrechnung


## Usedness

$$
U(l_t) =  Read(l_t) \cup (U(l_{t-1}) \cup Write(l_{t-1}))
$$
Fixpunktrechnung

## Eliminierung von Linksrekursion

Gegeben eine Linksrekursive Regel der Form

$$A \to A\alpha | \beta$$
erhalten wir
$$\begin{align}
&A \to \beta A'\\
&A' \to \alpha A' | \epsilon
\end{align}$$


## LR(0) Bottom Up Parser
Nach Konstruktion des Graphen:



__Shift__
Wir haben eine Shift Aktion, sollten wir ein Nichtterminal Symbol $a$ lesen und unser momentaner State enthält eine Regel der Art $A \to \alpha.a\beta$. 
Dann:
$S(q_i)$ Shifte das Eingabesymbol auf den Stack und lege $q_i$ darauf

__Reduce__
Enthält unser State eine Regel der Art $A\to\gamma.$ 
Dann:
$R(A\to \gamma)$ Reduce mit der Regel $A\to \gamma$ wenn der State $q_i$ durch das ersetzen von $\gamma$ durch $A$ auf dem Stack erreicht wird, dann lege den State $goto[q_i, A]$ auf den Stack

__Goto__
Beim Lesen eines Nichtterminal Symbols wechseln wir unsere State und schreiben dafür $G(q_i)$.

__Akzept__
Sollte $q_i$ eine Regel der Art $S' \to S.$ enthalten und unsere Eingabe ist $\epsilon(\$)$  Dann Akzeptieren wir das Wort.


## LRS(1) Bottom Up Parse Table


Nach Konstruktion des Graphen:



__Shift__
Wir haben eine Shift Aktion, sollten wir ein Terminal Symbol $a$ lesen und unser momentaner State enthält eine Regel der Art $A \to \alpha.a\beta$ 
Dann:
$S(q_i)$ Shifte das Eingabesymbol auf den Stack und lege $q_i$ darauf

__Reduce__
Enthält unser State eine Regel der Art $A\to\gamma.$ und das nächste Eingabe Token ist in $FOLLOW(A)$
Dann:
$R(A\to \gamma)$ Reduce mit der Regel $A\to \gamma$ wenn der State $q_i$ durch das ersetzen von $\gamma$ durch $A$ auf dem Stack erreicht wird, dann lege den State $goto[q_i, A]$ auf den Stack

__Goto__
Beim Lesen eines Nichtterminal Symbols wechseln wir unsere State und schreiben dafür $G(q_i)$.

__Akzept__
Sollte $q_i$ eine Regel der Art $S' \to S.$ enthalten und unsere Eingabe ist $\epsilon(\$)$  Dann Akzeptieren wir das Wort.


## Regex

- $a+b$ lets you choose between two patterns.
- $a·b$ lets you combine two patterns one after the other.
- $a∗$ lets you repeat a pattern zero or more times.
- $a\& b$ lets you find strings that match both patterns.
- $\overline a$ finds anything that doesn't match the pattern.

## First
- $FIRST(a) := \lbrace a\rbrace$
- $A\to \epsilon \implies \epsilon \in FIRST(A)$
- $A\to a\beta \implies a\in FIRST(A)$
- $A\to B\beta \implies (FIRST(B)\setminus \lbrace \epsilon\rbrace)\subseteq FIRST(A)$ wenn $\epsilon\in FIRST(B)$ dann alle Constraints von $A\to\beta$
## Follow
- $\$ \in FOLLOW(S)$
- Jede Regel $A \to \alpha B\beta \implies FIRST(\beta)\setminus\lbrace\epsilon\rbrace\subset FOLLOW(B)$
- Jede Regel $A\to \alpha B\beta$ mit $\epsilon \in FIRST(\beta) \implies FOLLOW(A) \subset FOLLOW(B)$

