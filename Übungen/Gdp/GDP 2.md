
## Aufgabe 2

```csharp
module Zahlen
open Mini

// Wir verwenden hier den Ausdruck failwith "TODO" als Platzhalter
// für Ihren Code. Dieser Ausdruck bewirkt, dass jeder Aufruf der
// Funktion mit der Fehlermeldung TODO fehlschlägt.
// So können wir Ihnen eine Vorlage bereitstellen, die vom Compiler
// akzeptiert wird. Solange der Platzhalter nicht ersetzt wurde,
// liefern die Testfälle für die jeweilige Funktion daher die
// Fehlermeldung TODO.

// a)
let dist (a: Nat) (b: Nat): Nat = max a b - min a b

// b)
let max3 (a: Nat) (b: Nat) (c: Nat) = max a (max b c) 

// c)
let median (a: Nat) (b: Nat) (c: Nat): Nat = a + b + c - (min a (min b c)) - max3 a b c
```


## Aufgabe 3

- Idempotenz: Nein da $x - x = 0$,
    - Beispiel: $dist\, 1\, 1 = 1 - 1 = 0$
- Kommutativität: Ja da wir immer `max` - `min` rechnen und max und min  Kommutativ sind
- Assoziativität: Nein
    - Beispiel: $$\begin{align}
    &\text{dist $($dist} 1\, 2)\, 3 = \text{dist} 1\, (\text{dist} 2\, 3)\\
    &\text{dist}\, 1\, 3 = \text{dist}\, 1\, 1\\
    &2 = 0
    \end{align}$$
- Distributivität über Multiplikation: Ja da wir bei der Substraktion das Distributiv Gesetz anwenden dürfen $$\begin{align}
&(max\, x\, y - min\, x\, y)\cdot2\\
& 2\cdot max\, x\, y - 2\cdot min\, x\, y
\end{align}$$
    und `max` und `min` auch Distributiv über die Multiplikation sind.

## Aufgabe 4