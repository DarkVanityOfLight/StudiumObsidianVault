```csharp
let s = 4711 + 815 in s*s 
```
berechnet den Flächeninhalt eines Quadrates der Seitenlänge 4711 + 815.
Wir können das Programm verallgemeinern indem wir von der Seitenlänge abstrahieren: aus s * s wird eine Funktion in s.

```csharp
let area(s: Nat): Nat = s*s
```

- area ist der Name der Funktion
- s vom Typ Nat ist der formale Parameter
- s * vom Typ Nat heißt Rumpf der Funktion

Um nun den Flächeninhalt für eine gegebene Seitenlänge zu berechnen, wenden wir die Funktion an:
```csharp
area(4711 + 815)
```

4711 + 815 ist das Argument oder der aktuelle Parameter der Funktion.

Der Funktionsaufruf wird ausgerechnet, indem der Formale Parameter an den aktuellen Parameter gebunden wird und in dieser Umgebung der Rumpf ausgewertet wird.
$$\text{area}(4711+815) \cong {\color{blue}\text{let}}\, s = 4711 + 815\, {\color{blue}\text{in}}\, s*s$$
Der Vorteil einer Funktionsdefinition ist, dass die Funktion mehrfach angewendet werden kann: 
```csharp
area(4711) + area(815)
```

Ohne Funktionen müssten wir formulieren:

```csharp
(let s 4711 in s*s) + (let s = 815 in s*s)
```

Funktionsdefinitionen sind Definitionen und können wie diese in in-Ausdrücken verwendet werden.

```csharp
let area(s: Nat): Nat = s*s
in area(4711) + area(815)
```

Sichtbarkeit: area ist im in-Ausdruck sichtbar; der formale Parameter s hingegen nur im Funktionsrumpf.

## [Abstrakte Syntax](Syntax.md#Abstrakte%20Syntax)

$$
\begin{align}
&f \in Ident&\\
&d::= &\text{Deklarationen}\\
&\quad |let f(x: t_1): t_2 =e&\text{Funktionsdefinition}\\
&e ::= ...& \text{Funktionsausdrücke}\\
&\quad |f(e) & \text{Funktionsapplikation}
\end{align}
$$
$t_1$ ist der Argumenttyp von $f$ und $t_2$ der Ergebnistyp.
Funktionsapplikation ist der vornehme Name für Funktionsaufruf oder Funktionsanwendung.


## [Statische Semantik](Semantik.md#Statische%20Semantik)
Eine Funktion mit dem Argumenttyp $t_1$ und dem Ergebnistyp $t_2$ erhält den Typ $t_1\to t_2$ Lies: $t_1$ nach $t_2$.
$$
\begin{align}
&t ::= ...\\
&|\quad t_1 \to t_2
\end{align}
$$

Typregelen:

$$

{ \sum, \{x_1 \to t_1\} \vdash e_2:t_2 \over
\sum\vdash({\color{blue}\text{let}}f(x_1:t_1): t_2 = e_2): \{f\mapsto t_1\to t_2\}
}
$$



$$
{\sum(f) = t_1 \to t_2 \qquad\sum\vdash e_1:t_1 \over \sum\vdash f(e_1) :t_2} f\in dom\sum
$$
Der Rumpf einer Funktion wird in der um den formalen Parameter erweiterten [Signatur](Signatur.md) getypt (',' ist der [Die Erweiterung(Kommaoperator)](Endliche%20Abbildungen.md#Die%20Erweiterung(Kommaoperator))).

## [Dynamische Semantik](Semantik.md#Dynamische%20Semantik)

- Was ist der Wert einer Funktion?
- Können wir Funktionen überhaupt auswerten?
- Man könnte eine Funktion tabellieren: für jedes Argument wird der Funktionswert ausgerechnet. 

Der Bereich der Werte wird um Funktionsabschlüsse erweitert(engl. closures).

$$\begin{align}
&v ::=...\\
&\quad | \langle\delta, x,e\rangle

\end{align}$$
Auswertungsregel:
$$
\over \delta \vdash (\text{let} f(x) = e) \Downarrow \{f\mapsto\langle\delta, x,e\rangle\}
$$
Eine Funktionsdefinition wertet zu einer Bindung aus, in der der Funktionsname an einen Funktionsabschluss gebunden ist.

Die Kombination aus Umgebung und Ausdruck $\delta \vdash e$, kann als Konfiguration oder [[Zustand]] eines Rechners aufgefasst werden; die Auswertungsregeln legen die Arbeitsweise des Rechners fest; eine "closure" speichert im Wesentlichen eine Konfiguration
### Auswertungsregel
$$
\delta(f) = \langle\delta', x_1, e\rangle \qquad \delta\vdash e_1 \Downarrow v_1 \qquad \delta', \{x_1\mapsto v_1\} \vdash e \Downarrow v \over \delta \vdash f(e_q) \Downarrow v
$$
Jetzt da der aktuelle Parameter bekannt ist kann die verzögerte Auswertung wiederaufgenommen werden.

### Beispiel
```csharp
let not(a: Bool): Bool = if a then false else true
```
wird ausgewertet zu
$\{\text{false} \mapsto \text{true}, \text{true} \mapsto \text{false}\}$
Dies ist nicht machbar, wenn das Argument eine natürliche Zahl ist.

Die Auswertung einer Funktion wird verzögert oder "eingefroren", bis der aktuelle Parameter bekannt ist.

## Verzögerte Auswertung
Was passiert, wenn der Funktionsrumpf freie Bezeichner enthält?

$$
{\emptyset \vdash 2\Downarrow2\over \emptyset \vdash \text{let d} =2 \Downarrow \{d\mapsto2\}}\qquad {\over \{d\mapsto2\}\vdash \text{let next}(n) = n+d \Downarrow?}\over \emptyset \vdash \text{let}\; d=2\; \text{let next}\; (n) = n+d \Downarrow?
$$
Wenn wir die Auswertung "einfrieren" und später fortsetzen "auftauen" wollen, müssen wir uns die Funktionsdefinition und die aktuelle Umgebung merken.



