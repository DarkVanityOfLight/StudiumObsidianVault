Hosts und Router werden auch Nodes genannt, Kommunikationskanäle die verschiedene Nodes verbinden nennt man [Links](Link.md), diese können über Kabel, Kabellos oder LANs funktionieren.
Ein Paket der Link Layer nennt man Frame, dieser encapsulated Daten.

> Die Link-Layer hat die Verantwortung dafür das die Daten von einer Node zu einer anderen Physisch benachbarten Node über einen Link Transportiert werden

Ein Datagram wird über verschiedene Link Protokolle über verschiedene Links verschickt, z.b. WiFi -> Ethernet. Jedes Protokoll bietet unterschiedliche Services, ein Protokoll könnte z.b eine zuverlässige Datenübertragung sicherstellen, oder eben nicht.

Die Link Layer bietet folgende Services:
Encapsulte die Daten in einen Frame und füge sowohl einen Header als auch einen Trailer hinzu, falls wir über ein [geteiltes Medium](Multiplexing.md) senden bietet die Layer Kanalzugriff und die MAC Adresse im Header des Frames identifiziert die Quell und Zieladresse.

Weiterhin bietet die Linklayer:
Flusskontrolle, also die Regulierung der Empfangs und Sendegeschwindigkeit zwischen benachbarten Nodes.
Fehlererkennung, zb. Fehler die durch Signal rauschen und Signal Schwächung, falls ein solcher Fehler erkannt wird, wird der Frame fallen gelassen und eine erneute Sendung angefordert.
Neber der Fehlererkennung können auch Fehler behoben werden, dabei identifiziert und korrigiert der Empfänger Fehler ohne das Paket neu zu übertragen.

Auch die Regulierung zwischen Halb und Vollduplex geschieht auf der Link Layer, da bei Halbduplex nur einer der beiden Nodes gleichzeitig senden kann.

## NIC
Die Linklayer findet man in jedem Host, sie befindet sich auf der Network Interface Card(NIC), diese ist verbunden mit dem System Bus.
Die Link Layer an sich besteht also aus einer Kombination von Software, Hardware und Firmware.

Wenn zwei NICs miteinander kommunizieren Funktioniert das folgendermaßen:

Die Sendende Seit encapsulates das Datagram in den Frame und fügt Checksums, zuverlässige Datenübertragung, Flusskontrolle und so weiter hinzu.

Die Empfangende Seite ueberprueft auf Fehler, zuverlässige Datenübertragung, Flusskontrolle und so weiter. Danach wird das Datagram aus dem Frame extrahiert und an die oberen Schichten weitergegeben.

## Multiple Access Protocols

Wenn sich mehrere Nodes einen Broadcast Channel teilen kann es zu bei zwei gleichzeitigen Übertragungen zu einer Interferenz kommen, daraus folgt eine Kollision sollte eine Node zwei oder mehr Signale auf einmal Empfangen.

Dafuer gibt es Multiple Access Protocols, diese Regeln wie Nodes sich einen Channel teilen, also bestimmen wer gerade Senden darf.

Das Problem dabei liegt darin das auch diese Informationen über den Channel gesendet werden müssen. 
Wir unterscheiden generell zwischen sogenannten [Taking Turns](Taking%20Turns.md), wobei Nodes sich immer abwechseln und Nodes die mehr senden müssen länger senden dürfen und [Random Access](Random%20Access.md) Protokollen, bei denen es zwar noch zu Kollisionen kommen kann, es jedoch Regeln zum "erholen" von diesen gibt.

