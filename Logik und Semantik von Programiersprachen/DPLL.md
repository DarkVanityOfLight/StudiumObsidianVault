
DPLL ist ein Algorithmus fuer das SAT Problem, der auf der [Tiefensuche](Algorithmen%20und%20Datenstrukturen/Graph.md#Tiefensuche) und der Deduktion/Einheits[resolution](Resolution.md) basiert ist.

Ein einfacher Tiefensuche basierter [Algorithmus](Algorithmus.md) könnte in etwa so aussehen:
```python
def SAT(Formula):
	if Formula == True:
		return True
	elif Formula == False:
		return False
	else:
		x = CHOOSE_VAR(Formula)
		return SAT(Formula[0/x]) or SAT[Formula[1/x]]
```


Mithilfe von [Boolean Constraint Propagation](Boolean%20Constraint%20Propagation.md) sieht unser DPLL Algorithmus nun so aus:
```python
def SAT(Formula):
	Formula = BCP(Formula)
	if Formula == True:
		return True
	elif Formula == False:
		return False
	else:
		x = CHOOSE_VAR(Formula)
		return SAT(Formula[0/x]) or SAT[Formula[1/x]]
```

Eine einfache Verbessrung besteht daraus das wir ein [Literal](Literal.md) _pure_ nennen, falls es nur positiv oder negativ in der Formel auftritt. Diese Literale kann man wahr machen bevor man eine Variable für die Abzweigung auswählt.

Unser DPLL Algorithmus sieht dann so aus:

```python
def SAT(Formula):
	while True:
		Formula1 = SET_PURE_TRUE(Formula)
		Formula2 = BCP(Fomrula1)
		if Formula2 == Formula1:
			break
	if Formula == True:
		return True
	elif Formula == False:
		return False
	else:
		x = CHOOSE_VAR(Formula)
		return SAT(Formula[0/x]) or SAT[Formula[1/x]]
```

Wir wenden also `BCP` und `SET_PURE_TRUE` solange an bis es nicht mehr möglich ist diese zwei Schritte weiter anzuwenden.

