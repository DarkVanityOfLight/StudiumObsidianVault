
Die Idee ist das wir Systematisch alle Adjazenten Implikanten vom Grad $k$ vereinigen um alle Implikanten vom Grad $k+1$ zu generieren.

>[!NOTE]
> Wenn $C_1$ und $C_2$ Adjazente Implikanten vom Grad $k$ von $\varphi$ sind, dann ist $\text{inf}(C_1, C_2)$ ein Implikant vom Grad $k+1$ von $\varphi$

Wir erhalten alle Implikanten durch das Kombinieren von Implikanten, wir starten mit dem Grad $0$

Beim Konstruieren der Tabelle starten wir mit den Implikanten vom Grad $0$ in der Linken Spalte, es ist zu empfehlen die Tabelle zu nach der Anzahl an $1$en  zu sortieren und zu Partitionieren. Um die Implikanten des nächsten Grades zu bestimmen, reicht es die Adjazens von Implikanten in einer Partition und der nächsten zu ueberpruefen. Die Anzahl an Spalten ist gleich der Anzahl an Partionen der Linken Spalte.

Der Index eines Cubes ist die Menge an Implikanten die bei ihm bedeckt werden, deshalb ist die ueberdeckungs [Relation](Relation.md) das Inverse der Subset Relation von Index Mengen.

Die Primimplikanten sind die die nicht weiter Kombiniert werden koennen.

## McCluskey Tabelle

Um die ueberdeckung zu berechnen verwenden wir eine McCluskey ueberdeckungs Tabelle:

![mccluskey](mccluskey.png)

Ein Tabelleneintrag wird mit $x$ markiert wenn der Prim Implikant(Zeile) einen minterm(Spalte) abdeckt.

In diesem Beispiel ist keiner der Implikanten Redundant, die minimale DNF ist dann die Disjunktion der Cubes.

> [!IMPORTANT] Essentielle Primimplikanten
> Ein Primimplikant ist essentiell wenn er der einzige ist der einen minterm Abdeckt

