 ```csharp
 let s = 4711 + 815
 ```
 Das Konstrukt ist eine Wertedefinition der Bezeichner links wird an den Wert des Ausdrucks rechts gebunden. Lies: sei s gleich 4711 + 815
 Ein Bezeichner ist ein Ausdruck.

## [Abstrakte Syntax](Syntax.md#Abstrakte%20Syntax) Definitionen
Wir führen eine neue syntaktische Kategorie ein: Deklarationen.

$x\in Ident$
$d\in Decl ::=$
            $|let\, x\, = e$
## [Abstrakte Syntax](Syntax.md#Abstrakte%20Syntax) Ausdrücke
Ein in-Ausdruck verknüpft eine Definition mit einem Ausdruck

```csharp
e ::= ...
    | x
    | d in e
```
Der Teilausdruck e heißt Rumpf des in-Ausdrucks

## [Statische Semantik](Semantik.md#Statische%20Semantik) Ausdrücke

```csharp
let s = 4711 + 815 in s * s*
```
Wenn wir den Teilausdruck s*s typisieren, woher kennen wir den Typen von s?
Ein Bezeichner kann in unterschiedlichen Kontexten einen unterschiedlichen Typ besitzen.

```csharp
(let s = true in s) && (let s = 815 in s*s > 4711)
```
