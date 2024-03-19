Sei $P = (P_1, P_2, \dots, P_n)$ ein Prozesssystem. Eine __Verklemmung(Deadlock)__ von $P$ liegt dann vor, wenn jeder [Prozess](Prozess.md) aus $P$ auf Bedingungen wartet, die nur durch den jeweils anderen Prozess erfüllbar sind.

Die folgenden Bedingungen sind notwendig für eine Verklemmung:

- Ressourcen sind nur exklusiv benutzbar
- Prozesse sind bereits im Besitz von Ressourcen, während sie weitere anfordern
- Kein zwangsweiser Entzug von Ressourcen
- Es existiert ein Zyklus von Prozessen, in dem jeder Prozess Ressourcen besitzt, die vom nächsten Prozess des Zyklus angefordert werden


## Praezedenzmatrix

für Ressourcen $r$ und $s$ sowie Prozess $P$:

$r <_p s$: Prozess $P$ hat $r$ und fordert $s$ an

Wir stellen Anfragen als Tabelle/Matrix da mit
- Werte für $r$ als Zeile
- Werte für $s$ als Spalte
- $>_p$ als Tabelleninhalt

## Praezedenzgraph

Wir stellen Ressourcen als Knoten da. Eine Kante von Knoten $r$ nach Knoten $s$ mit Beschriftung $P$ stellt dar dass $P$ $r$ hat und $s$ anfordert. Ein Zyklus bedeutet eine mögliche Verklemmung