
## Real-World Measurments

Dabei werden vollständige Systeme mit echten Nutzern Betrachtet:

_Vorteile:_
- Realistischer geht es nicht
- Es müssen keine Annahmen getroffen werden

_Nachteile:_
- Schwierig exakt zu messen
- Schwere Integration von Aspekten
- Lange Entwicklungszeiten

## Testnets

Ei vollstaendiges System, das nur von Entwicklern/Freiwilligen genutzt wird, jedoch Global an verschiedenen Standpunkten aufgesetzt wird.

_Vorteile:_
- Gesamtsystem
- Testen von neuen Aspekten

_Nachteile:_
- Lange Entwicklungszeiten
- Nutzer verhalten vielleicht nicht realistisch

## Testbeds

Testbeds sind lokale Testnets, in denen das Nutzer verhalten meist simuliert/automatisiert ist

_Vorteile:_
- Vollständige Implementierung
- Einfachere Entwicklung/Realisierung
- Entwickler haben volle Kontrolle

_Nachteile:_
- Latenzen müssen bei nicht-lokalen Systemen simuliert werden
- Nutzer verhalten eventuell nicht realistisch
- Skaliert nicht

## Emulation

Eine vollständige Implementierung, bei der jedoch [Prozesse](Prozess.md) die auf verschiedenen Maschinen laufen sollen, nur auf einer Maschine laufen. Das Netzwerk wird durch die Verzögerung interner Nachrichten simuliert.

_Vorteile:_
- Effizient, skaliert besser als Testbeds
- Fast vollständige Implementierung

_Nachteile:_
- Netzwerklatenzen und andere Aspekte werden oft nicht realistisch dargestellt

## Simulation

Eine Simulation ist eine unvollständige Implementierung des Systems, bei der nur relevante Aspekte des Systems getestet werden.

_Vorteile:_
- Sehr flexibel und effizient
- Skaliert gut
- Einfach zu implementieren

_Nachteile:_
- Nicht realistisch

Dabei hängt es von den Zielen der Simulation ab, welche Teile des Systems vereinfacht werden.
Es werden die Teile vereinfacht/nicht implementiert, die nicht wichtig sind um die gewünschte Metriken zu messen.

## Belastbarkeit

Empirische Methoden sind keine Beweise, die Evaluation ist also in den meisten Fällen probabilistisch. Deshalb müssen Experimente mehrfach ausgeführt werden um auf statistische Signifikanz getestet zu werden.

## Zeit

### Simulierte Zeit
Laufzeit der Simulation in reeller Zeit

### Simulationszeit
Zeit, wie sie in der virtuellen Welt der Simulation vergeht.

## Discrete-Event Simulation

Bei der discrete event Simulation werden jedem Ereignis eine simulierte Zeit zugewiesen, diese werden dann in zeitlicher Reihenfolge abgearbeitet

Am Anfang werden die Ereignisse in eine Priority Queue eingetragen, dabei werden erst Ereignisse ohne Vorgänger Ereignisse eingefügt.

Nach dem Ausführen werden Ereignisse aus der Queue entfernt.
Wenn Ereignisse ausgeführt werden, resultieren daraus neue Ereignisse, diese werden dann wiederum in die Queue eingefügt. Ereignisse, die durch mehrere vorherige Ereignisse bedingt sind, werden in die Queue eingefügt wenn alle diese Ereignisse ausgeführt wurden.