

## Makroarchitektur
Die Makroarchitektur bezeichnet den Befehlssatz mit dem der Programmierer Interagiert
Dies beinhaltet die anzahl und groesse der [Register](Register.md), die Wahl der Befehle und die Verschlüsselung von Befehlen durch Bitvektoren.

## Mikroarchitektur

Die Mikroarchitektur ist die Implementation eines Befehlssatzes. Dabei sind für jeden Befehl unterschiedliche Ausführungszeiten möglich. Die Semantik des Befehlssatzes ist jedoch unveränderbar. Verschiedene Mikroarchitekturen können unterschiedliche Leistungen haben. Neben dem Befehlssatz müssen folgende Dinge beachtet werden:
- Parallele Ausführung von Befehlen
- Interne Architektur des Prozessors
- Speicher hirachy

---

Die Definition einer Architektur hat einen großen Einfluss auf verschiedene Dinge:
- Die Komplexität/Effizienz einer Hardware Implementation
- Die Parallelisierung innerhalb des Prozessors
- Die länge von Maschinen Programmen
- Compiler Optimierungen
- Cycle Time(CPI) : Clocks per Instruction


---

## Register, Stacks, Queues
Da Speicherzugriff deutlich langsamer als der Prozessor ist, laden wir ganze Speicherblöcke aus dem [Speicher](Speicher.md) in den Cache um die Laufzeit zu Armotisieren.
Dabei können auch mehrere Caches hintereinander verwendet werden.

Diese Caches befinden sich auf dem Prozessor Chip, am Ende dieser Speicherhierachie, können wir Lokalen Speicher auf dem Prozessor einführen, dies führt zur sogenannten __Load/Store__ Architektur. Dabei finden alle Arithmetischen Operationen ihre Operanten in Lokalem Speicher und schreiben ihre Ergebnisse auch dort hin. Dieser Speicher kann durch Adressierbaren Speicher([Register](Register.md)) oder als [Stack](Stacks.md)/ [Queue](Queue.md) implementiert sein. 

### Register

Befehle haben [Register](Register.md) operanten und Register als Ergebnis. Dafür müssen wir Operanten in die Register laden um eine Arithmethisch Logische Operation auszuführen.
Wir versuchen die Ergebnisse möglichst lange in den Registern zu halten, zu diesem Zweck muss der Compiler die Programm variablen auf Register abbilden, da es meistens mehr Programm variablen als Register gibt, ist es unvermeidbar das mehrere Programm variablen auf das selbe Register abgebildet werden. Dafür ist es wichtig das diese Variablen nie in der gleichen Operation verwendet werden. Die Hauptarbeit des Compilers besteht darin  eine möglichst gute Abbildung zu finden.

### Stacks

Befehle gehen davon aus das die Operanten auf dem Stack liegen, die Befehle verbrauchen die Operanten und legen das Ergebnis zurück auf den Stack. Die Generation von Code wird durch eine [Tiefensuche](Algorithmen%20und%20Datenstrukturen/Graph.md#Tiefensuche) über die Syntaxbäume ausgeführt.

## Queue

Befehle finden die Argumente am Kopf der Schlange und hängen ihre Ergebnisse an das Ende an. Code wird hier durch eine [Breitensuche](Algorithmen%20und%20Datenstrukturen/Graph.md#Breitensuche) über den Syntaxbaum erstellt. 

---


Mehr oder weniger alle Prozessoren verwenden [Register](Register.md), aber wie diese Register verwendet werden unterscheidet sich. Es gibt spezielle [Register](Register.md) und allgemeine, außerdem kann sich die Zahl an [Registern](Register.md) stark unterscheiden.



##  CISC

Ein Prozessor hat mehrere [Register](Register.md), die Argumente für Arithmetisch Logische Operationen können Register oder Speicheradressen sein.

## RISC
Ein Prozessor hat mehrere [Register](Register.md) 
RISC Anweisungen erlauben Speicherzugriff nur für load/store Anweisungen, Argumente von Arithmetisch Logischen Operationen sind immer in Registern.

---

Heutzutage gibt es keine direkte Unterscheidung zwischen CISC und RISC, der letzte CISC Prozessor war Intels $80386$.  Um compatibilitaet zu gewährleisten werden CISC befehle intern zu RISC befehlen umgewandelt.


---

Das Designen eines Prozessors ist eine Abwägung zwischen verschiedenen Faktoren, um zwischen diesen zu entscheiden werden meist [Benchmarks](Benchmarks.md) verwendet.