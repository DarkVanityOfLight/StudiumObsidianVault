__Scheduling__ ist das Zuweisen von Ressourcen, d.h. das Entscheiden welche Prozesse/Threads zu welchen Zeiten welche Ressourcen benutzen dürfen.

## Scheduling Algorithmus

Scheduling Algorithmen planen wie Ressourcen vergeben werden, meist versuchen diese Algorithmen eine oder mehrere der folgenden [Mektriken](Mektrik.md) zu optimieren:

- Bearbeitungszeit pro Task
- Maximale Zeit bis ein Task bearbeitet ist
- Anteile an Tasks, die vor der Deadline bearbeitet werden
- Auslastung des Systems (Ressourcen nicht ungenutzt lassen)

Tasks können in den obigen Metriken nach Priority gewichtet werden.

## Präemptiv

Tasks koennen unterbrochen und spaeter fortgesetzt werden(Gegenteil nicht-Präemptiv)

## Statisch

Die Reihenfolge der Tasks in der Warteschlange wird nicht geändert. 


## First Come First Served

Tasks werden in der Reihenfolge in der sie eingereicht werden ausgeführt

## Shortest Job First

Der Task mit dem geringsten (erwarteten) Zeitaufwand wird zuerst ausgeführt, dies kann Präemptiv oder nicht-Präemptiv sein

## Round Robin mit Time Slicing

Es wird zwischen den Tasks regelmässig gewechselt

## Highest Priority/Earliest Deadline First

Hier wird der Task mit der höchsten Priorität/nächsten Deadline zuerst ausgeführt.

Dies kann präemptiv oder nicht präemptiv sein