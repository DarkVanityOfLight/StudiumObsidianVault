
Das Grundlegende Prinzip der Logikminimierung:
- Wir Starten mit einer DNF aus Mintermen und versuchen [Cubes](Cubes.md) zu vereinen


>[!IMPORTANT] Hauptprinzip
> Die Kombination von Adjazenten Cubes
> $$x\land \varphi \lor \neg x \land \varphi \iff \varphi$$
> lässt den Infimum Cube $\varphi$ zurück

>[!NOTE] In [BDDs](Binary%20Decision%20Diagramms.md) wird diese Prinzip zum löschen von Knoten verwendet

Algorithmen verwenden diese Regel Symmetrisch.

## Einfache Minimisierung

- Berechne die Kanonische DNF
- Ersetze Adjazente [Cubes](Cubes.md) mit ihrem Infimum


## Implikant

Ein $\text{cube}_v(v, g)$ ist ein Implikant des Grades $k$ von $\varphi$ wenn:
- $\text{cube}_v(v, g) \to \varphi$ 
- $\text{cube}_v(v, g)$ den Grad $k$ hat.

### Primimplikant

Ein $\text{cube}_{v}(v, g)$ ist ein Primimplikant vom Grad $k$ von $\varphi$ wenn:
- $\text{cube}_v(v,g)$ ein Implikant vom Grad $k$ von $\varphi$ ist und
- $\text{cube}_v(v, g)$ wird nicht von einem anderen Implikanten von $\varphi$ bedeckt

Ein Primimplikant ist ein minimaler Implikant, das herausnehmen eines Literals wird nicht zu $\varphi$ führen.

Cubes vom Grad $k$ stellen $2^k$ Variablenbelegungen dar.

Implikanten vom Grad $k$ stellen $2^k$ minterme von $\varphi$ dar.

## Quine

Jede minimale Disjunktion von Cubes ist eine disjunktion von Primimplikanten.


