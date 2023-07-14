
Ein Objektdiagramm beschreibt eine Art Momentaufnahme des Systems:
Eine Menge von Objekten, wie sie zu einem bestimmten Zeitpunkt vorhanden sind.

Ein Objekt kann, muss aber keinen Namen haben. Es muss aber stets die Klasse angegeben werden, von der dieses Objekt eine Instanz ist

![](obj1.png)

Es muessen in Objektdiagrammen nicht alle Attributbelegungen angegeben werden.

## Link

Ein Link beschreibt eine Beziehung zwischen zwei Objekten. Er ist eine Instanz einer Assoziation auf Klassenebene.

Ein Link beschreibt genau eine Beziehung, die [Multiplizitaetsbedingungen](Klassendiagramme.md#Assoziation) des [Klassendiagramms](Klassendiagramme.md) eingehalten werden. Das bedeutet, dass die Anzahl der Objekte, die miteinander in Beziehung stehen, innerhalb der jeweiligne Schranken sein muss.

## Aggregation/Komposition

Auch [Aggregation](Klassendiagramme.md#Aggregation) und [Komposition](Klassendiagramme.md#Komposition) duerfen in Objektdiagrammen auftauchen.

Beziehungen zwischen Klassen werden vererbt und muessen dann auch entsprechend im Objektdiagramm bei den Instanzen der Unterklasse auftauchen.