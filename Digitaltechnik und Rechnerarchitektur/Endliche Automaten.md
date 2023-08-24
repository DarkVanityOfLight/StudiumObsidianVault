

>[!IMPORTANT] Definition
> Ein endlicher Automat $A$ ist ein Tupel $A = \langle\Sigma_{in}, S, L, R, F\rangle$ wobei
> $\Sigma_{in}$ das Eingabe Alphabet ist
> $S = \lbrace s_1, \dots, s_m$  eine endliche [Menge](Mengen.md) von Knoten ist
> $L\subset S$ die Menge von Start Knoten ist
> $R\subset S \times \Sigma_{in} \times S$ die Kanten sind
> $F \subset S$ die End Knoten sind.

Das Ziel einer Berechnung ist es entweder ein endliches Wort zu akzeptieren oder Zurückzuweisen.

Die Berechnung ist definiert als:
-  Die Berechnung beginnt in einem Startzustand $s_0 \in L$(nichtdeterministisch)
- Das Gegebene Wort $\sigma_1, \dots, \sigma_l$ wird Buchstabe für Buchstabe eingelesen.
- Wenn der Automat im Knoten $s_i$ den Buchstaben $\sigma_i$ ließt, ist der nächste Knoten ein Knoten $s_{i+1}$ mit $(s_i, \sigma_i, s_{i+1})\in R$
- gibt es keinen solchen Knoten $s_{i+1}$ wird das Wort nicht akzeptiert
- wenn mehr wie einer solcher Knoten existiert wird nichtdeterministisch gewählt.

Akzeptanz wird so definiert:
- $\sigma_1, \dots\sigma_l$ wird Akzeptiert wenn es eine Sequenz an Knoten $s_0, \dots, s_l \in S$ gibt sodass
	- $(s_i, \sigma_{i+1}, s_{i+1}) \in R$ gilt für $i \in\lbrace0, \dots, l-1\rbrace$
	- $s_0 \in L$
	- $s_l \in F$

## Sprachen

Die Menge an Akzeptierten Wörtern nennt man $\text{Sprache} L(A)$ des Automaten. Wörter in $L(A)$ haben eine endliche Länge, aber $L(A)$ kann unendlich viele Wörter haben. Die Menge aller endlichen Wörter schreibt man als $\Sigma^*_{in}$.

Nicht jede Menge $L\subseteq \Sigma^*_{in}$ kann akzeptiert werden.

## Transducer vs. Acceptor

Bisher haben wir nur Endliche Automaten betrachtet, diese akzeptieren oder weisen das Wort zurück. Es gibt auch Endliche Maschinen, diese übersetzen ein gegebenes Wort in ein anderes.

> [!IMPORTANT] FSM
> Eine FSM $A$ ist ein Tupel $A = \langle\Sigma_{in}, \Sigma_{out}, S, L, R\rangle$
> $\Sigma_{in}$ ist das Eingabe Alphabet
> $\Sigma_{out}$ ist das Ausgabe Alphabet
> $S = \lbrace s_1, \dots, s_m \rbrace$ ist eine endliche Menge aus Knoten
> $L \subseteq S$ ist eine Menge aus Anfangsknoten
> $R\subseteq S\times \Sigma_{in} \times \Sigma_{out} \times S$ ist die Übergangsrelation


## Umwandeln

Für jeden FSM $A = \langle \Sigma_{in}, \Sigma_{out}, S, L, R\rangle$ koennen wir einen FSA $A' = \langle\Sigma_{in} \times \Sigma{out}, S\cup\lbrace s_0\rbrace\rangle, L, R', F$ mit 

$s_0$ ist ein neuer Knoten nicht in $S$

$$R' = \begin{align}
&\lbrace(s, (i, o, s') | (s, i, o, s') \in R\rbrace \cup\\ &\lbrace (s, (i, o), s_0 | \neg\exists s' \in S.(s, i, o, s') \in R) \rbrace\cup\\
&\lbrace (s_0, (i, o), s_0) | (i, o) \in\Sigma_{in} \times \Sigma_{out} \rbrace
\end{align}$$

$F = S$

$A$ übersetzt $a_1, \dots, a_l \in \Sigma^*_{in}$ nach $b_1, \dots, l \in\Sigma_{out} \iff A'\text{ akzeptiert } (a_1, b_1) \dots (a_l, b_l)$ 

Wenn wir $(i, o)$ im Knoten $s$ lesen wechseln wir nach $s'$ in $A'$ wenn $A$ von $s$ nach $s'$ wechselt wenn es $i$ liest und $o$ generiert.

Der Fehlerknoten $s_0$ wird erreicht wenn ein Paar $(i, o)$ in einem Knoten $s$ gelesen wird sodass $A$ im Knoten $s$ für Input $i$ ein anderes Ergebnis $o$ liefert

Die andere Richtung funktioniert auch:


Für jeden FSA $A = \langle \Sigma_{in}, \Sigma_{out}, S, L, R\rangle$ koennen wir einen FSM $A' = \langle\Sigma_{in} \times \Sigma{out}, S\cup\lbrace s_0\rbrace\rangle, L, R', F$ mit 

$$R' \iff \begin{align}
\lbrace (s, i, 0, s') | (s, i, s') \in R \land s' \not\in F' \rbrace \cup\lbrace (s, i, 1, s') | (s, i, s') \in R \land s' \in F' \rbrace
\end{align}$$

$A$ akzeptiert 
$\alpha := a_1\dots a_l \in\Sigma^{*}_{in} \iff A'$ $\alpha$ nach $b_1, b_l \in \lbrace 0,1\rbrace^*$ sodass $b_l = 1$

Mit Ausnahme des leeren Wortes kann ein FSM also auch Informationen über das Akzeptieren generieren.

FSMs werden auch Mealy Maschine genannt.


## Moore Maschinen

Bei Moore Maschinen wird der Output über den Knoten generiert und nicht den Übergang.

Für jede Mealy Maschine $A = \langle\Sigma_{in}, \Sigma_{out}, S, L, R\rangle$ definieren wir die zugehörige Moore Maschine $M = \langle\Sigma_{in}, \Sigma_{out}, S', L', R'\rangle$ mit

$\Sigma'_{out} := \Sigma_{out} \cup \langle \# \rangle$ wobei $\#$ das Ausgabe Symbol ist
$S' :=  S\times \Sigma_{out} \subset L \times \lbrace\#\rbrace$ 
$L' = L\times\lbrace \#\rbrace$
$((s, b), a, b, (s', b')) \in R' \iff (s, a, b', s') \in R$

Wenn $A$ $a_1, \dots, a_l \in\Sigma*_{in}$ nach $b_1, \dots, b_l \in \Sigma^{*}_{out}$ übersetzt, dann übersetzt $M$ das Selbe Wort $\#b_1, \dots b_l \in(\Sigma_{out} \cup \langle\#\rangle)^*$

Wir Merken uns den Output von $A$ im nächsten Knoten von $M$

Jeder Knote $(s, b)$ der Moore Maschine $M$ hat einen eindeutigen Output $b$

Der Output $b$ der Moore Maschine $M$ hängt vom Knoten $s, b$ ab

## Deterministik

Bisher hatten wir keine Beschränkungen der Übergangsrelationen $R$, jedoch sind die Folgenden wünschenswert:

### Totaler Automat

Wenn jeder Knoten $s$ und jeder Input $\sigma\in\Sigma$ mindestens einen Knoten $s'$ mit $(s, \sigma, s') \in R$ hat.

### Deterministischer Automat

Totaler Automat und es gibt genau einen Startknoten

Jeder FSA mit $n$ Knoten hat einen Äquivalenten Deterministischen FSA mit maximal $s^n$ Knoten.

### Konstruktion

Gegeben sei $A = \langle \Sigma_{in}, S, L , R, F \rangle$, wir konstruieren $A_{det} = \langle \Sigma_{in}, S_{det}, L_{det} , R_{det}, F_{det} \rangle$ wiefolgt:

$S_{det} := 2^S$
$L_{det} := \lbrace L \rbrace$
$R_{det} \subseteq 2^S \times \Sigma_{in} \times 2^S$ definiert als

$R_{det} := \langle(Q, \sigma, \text{suc}_{\sigma}(Q)) | Q \subseteq, S, \sigma \in \Sigma_{in}\rangle$

mit den Folgeknoten $Q\subseteq S$ unter $\sigma \in\Sigma_{in}$

$\text{suc}_{\sigma}(Q) := \lbrace s' \in S | \exists s\in Q.(s, \sigma, s') \in R\rbrace$

Die Endknoten sind $F_{det} = \lbrace Q\subseteq S | F\cap Q \not = \lbrace\rbrace \rbrace$

## Rabin-Scott

```python
def RabinScott(Sigma, S, I, R):
    front = {I}
    S_tilde = set()
    R_tilde = set()

    while front != set():
        S = front.pop()
        S_tilde.add(S)

        for sigma in Sigma:
            S_prime = suc_sigma(S)
            R_tilde.add((S, sigma, S_prime))

            if S_prime not in S_tilde:
                front.add(S_prime)

    return (Sigma, S_tilde, {I}, R_tilde)
```

## Minimisierung

Die Idee:

Berechne Äquivalente Knoten $s_1, s_2 \subseteq S\times S$ und vereinige gleiche Knoten in einen Knoten.

### Minimaler Automat

Wir verwenden die selbe Konstruktion um $\Delta_i \subset \Delta_{i+1}$ zu berechnen, nach endlich vielen Schritten erreichen wir $\Delta_{*}$ 

Wir definieren $\varepsilon := (S \times S) \setminus \Delta$  als die Menge Äquivalenter Knoten, $\varepsilon$ ist eine [Äquivalenzrelation](Äquivalenzrelationen.md)

