

## Checksum berechnen

$n = r-1$ wobei $r$ die Länge des Generatorpolynoms ist.
An die den Daten Frame werden $n$ Nullen angehängt. Anschliessend wird der Datenframe durch den Generator geteilt. Die ersten $n$ BIts(von Links) des Rests werden anstatt der angehängten Nullen an den Datenframe angehängt.

## Checksum Validieren

Der Datenframe mit der angehängten Checksum werden erneut durch den Generator geteilt, bei Rest $0$ ist die Nachricht intakt, sonst nicht.



