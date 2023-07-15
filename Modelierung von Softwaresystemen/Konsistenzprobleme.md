[Klassendiagramme](Klassendiagramme.md) beschreiben die Statische Struktur eines Programmes, es gibt keine Zeitlichen ablaeufe, Programmcode hingegen stellt eine Sequenz von Maschinenbefehlen dar, diese werden nacheinander abgearbeitet, dadurch Momentaufnahmen von Software inkonsistent mit dem dazugehörigen [Objektdiagramm](Objektdiagramme.md)/[Klassendiagramm](Klassendiagramme.md) sein. Zum Beispiel sind Objekte noch unvollständig initialisiert, es liegt am Programmierer diese Konsistenz Sicherzustellen.


![](kons.png)

In Code wuerde das so aussehen

```java
Kunde k1 = new Kunde();
Kunde k2 = new Kunde();

k1.setNummer(42);
```

Die Konsistenz mit dem Diagramm ist erst nach dem Aufruf des Setters hergestellt.

Dieses Problem hat die selbe Lösung wie [Assoziationen in Java](Assoziationen%20in%20Java.md), durch die Verwendung von Konstruktoren können wir sicherstellen das alle Attribute nach der Erstellung des Objektes Initialisiert und Konsistent mit dem Diagramm sind
