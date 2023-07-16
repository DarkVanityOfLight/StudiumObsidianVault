
Nicht alle UML-Konzepte lassen sich auf jede Programmiersprache übertragen.

Übersetzung UML -> Java:
- Generell gut zu bewerkstelligen
- Probleme bei der Praktischen Umsetzung von
	- [Assoziationen in Java](Assoziationen%20in%20Java.md) 
	- [Sichtbarkeiten in Java](Sichtbarkeiten%20in%20Java.md)
	- [Mehrfachvererbung in Java](Mehrfachvererbung%20in%20Java.md)

- Probleme beim Initialisieren von Objekten
	- Java Klassen und Objekte sollten in einem konsistenten Zustand zum UML-Diagramm sein:
		 - Nach dem Instanziieren
	    - Nach dem Aufruf von Klassenoperationen

	- Falls die Kardinalität $0$ nicht vorgesehen ist, sollte beim Initialisieren die Übergabe von `null` als Argument geprüft und unterbunden werden.
