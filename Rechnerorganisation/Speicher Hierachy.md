
Sogenannte [Caches](Cache.md) erschaffen die Illusion von Schnellem Grossem Speicher, der Cache enthält  die Momentan verwendeten Teile des Hauptspeichers. Der erste Zugriff auf den Speicher ist langsam, aber alle darauf folgenden sind schnell. Caches werden mit [SRAM](SRAM.md) implementiert und der Hauptspeicher durch [DRAM](DRAM.md).

Bei der Verwendung von Caches gehen wir nach zwei Haupt annahmen:
- _Zeitliche Lokalität_, eine Verwendete Adresse wird wahrscheinlich erneut benutzt
- _Räumliche Lokalität_, Adressen nahe einer Verwendeten Adresse werden wahrscheinlich verwendet

## Hierachy

Caches werden zwischen dem Hauptspeicher und dem [Prozessor](Prozessor.md) eingesetzt. Auf dem niedrigsten Cache Level unterscheiden wir zwischen Anweisung und Daten Speicher. Die $l$ verschiedeneren Cache Level, können unterschiedliche Cache Arten verwenden, eine Speicherzelle des $k$ten Levels sind auch im $k+1$ Level Vorhanden. Die Speicher groesse und Zugriffszeit erhöhen sich mit dem Level $k$ und die Kosten pro MB Verringern sich pro Level $k$. Heutzutage werden meist $2$ oder $3$ Cache Level verwendet.

Fuer einen Speicherzugriff suchen wir erst im ersten Cache Level, wenn die Daten dort gefunden werden, werden sie geliefert, ansonsten suchen wir im nächsten Cache Level.
Schließlich werden die Daten gefunden und wir haben einen _hit_, werden die Daten nicht gefunden gibt es einen _miss_. Im Falle eines Hits im Level $k$, werden die Daten auf alle Level $<k$ kopiert. Eine Hohe Hit Rate erschafft die Illusion von Speicher mit der Schnelligkeit von Level $1$ und der groesse von Level $l$.


