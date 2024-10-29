
Wir unterscheiden zwischen einem Hauptspeicher  der Daten beinhaltet und einem Prozessor der Daten aus dem Hauptspeicher schreibt und liest. Das Programm selbst ist im Hauptspeicher und die Speicheradresse des nächsten Maschinenbefehls ist im Programm Zähler(PC) auf dem Prozessor gespeichert. 

Der Prozessor und der Hauptspeicher sind durch einen Adresse Bus(Prozessor nach Hauptspeicher) und einen Daten Bus. 

## Lesen
Wenn der Prozessor eine Speicherzelle lesen will, schreibt er die Adresse auf den Adress Bus mit der Information das ein Wert gelesen werden soll, der Hauptspeicher wählt dann die Speicherzelle und legt den Inhalt auf den Daten Bus.

## Schreiben
Um einen Wert in den Hauptspeicher zu schreiben muss der Prozessor die Adresse auf den Adressbus schreiben zusammen mit der Information das ein Wert geschrieben werden soll, dann legt er die Daten auf den Daten Bus wo der Hauptspeicher sie Abruft und an die angegebene Adresse abspeichert.


Es kann immer nur ein Wert auf dem Daten Bus liegen. Außerdem ist zu beachten das der Speicherzugriff ca. 100x länger dauert als übliche Operationen.

---

In einem Rechnersystem gibt es nur einen Hauptspeicher wo das Programm und die Daten gespeichert werden. 

Da der Prozessor Daten und Anweisungen aus dem Speicher lesen muss, kommt es immer dann zu einem Konkurrenzkampf um den Speicherzugriff wenn Zusatzlicht zu der Anweisung auch noch Daten gelesen werden müssen. Deswegen gibt es meist zwei Speicher, einen für das Programm, der sogenannte "Befehlscache" und einen für die Daten der "Daten Cache". Diese Verfeinerung wird meist auch Harvard Architektur genannt.

Die Daten im Programmspeicher können meist nur gelesen werden.

In Wirklichkeit wird meist trotzdem nur ein Speicher verwendet mit unterschiedlichen Hierarchien.