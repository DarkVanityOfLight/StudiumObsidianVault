
Das Grundlegende Prinzip der Logikminimierung:
- Wir Starten mit einer DNF aus Mintermen und versuchen [Cubes](Cubes.md) zu vereinen


>[!IMPORTANT] Hauptprinzip
> Die Kombination von Adjazenten Cubes
> $$x\land \varphi \lor \neg x \land \varphi \iff \varphi$$
> lässt den Infimum Cube $\varphi$ zurück

>[!NOTE] In [BDDs](Binary%20Decision%20Diagramms.md) wird diese Prinzip zum löschen von Knoten verwendet

Algorithmen verwenden diese Regel Symmetrisch.

