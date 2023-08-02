

## Vorteile

- Sehr flexibel mit der Empfangsreichweite
- Es können große Flächen abgedeckt werden da Radiowellen durch Wände gehen
- Keine Kabel :D

## Nachteile

- Geringere Bandbreite
- Viele unterschiedliche Protokolle
- Unterschiede zwischen Ländern, wegen belegten Frequenzbändern

## Infrastruktur Netzwerke

Kabellose Hosts sind mit einem AP(Access Point) verbunden

## Ad-Hoc Netzwerk

Kabellose Hosts Kommunizieren untereinander


## Funktionen und Layer

- MAC
	- Zugriffsmechanismen, Fragmentation, Verschlüsselung
- MAC Management
	- Synchronisation, Roaming, MIB(Management Information Base)
- PLCP(Physical Layer Convergence Procedure)
	- Signal um zu zeigen das der Channel Frei ist
- PMD(Physical Medium Dependent)
	- [Modulation](Modulation.md), [Encodings](Encodings.md)
- PHY Management
	- Kanal auswahl, MIB
- Station Management
	- Koordination aller Management Funktionen

![lf802](lf802.png)

## MAC Layer

Die Mac Layer besteht aus einem Asynchronen Daten Service der Pakete auf einer "best-effort" Basis austauscht, er muss Broad und Multicast unterstützen und wird durch DCF(Distriubuted Coordination Function) implementiert. Außerdem muss er DCF [CSMA/CA](Random%20Access.md#CSMA%20with%20Collision%20Avioadance%20(CSMA/CA%20802.11))unterstützen oder optional DCF CSMA/CA mit [RTS/CTS](Random%20Access.md#^f3976f).

Ausserdem kann ein "time-bounded service" implementiert sein, dieser verteilt Pakete auf einer "master-slave" Basis und wirt durch PCF(Point Coordination Function) implementiert.


### Prioritäten
Prioritäten werden durch unterschiedliche Zwischen Frame Spaces definiert, die Prioritäten sind nicht garantiert.

- SIFS(Short Inter Frame Spacing)
	- Höchste Priorität, reserviert für ACK, CTS und Polling Responses
- PIFS(PCF Inter Frame Spacing)
	- Mittlere Priorität für Zeitgebundene Services mit PCF
- DIFS(DCF Inter Frame Spacing)
	- Geringste Priorität, für Asynchrone Daten Services

![prio](prio.png)


## DCF CSMA/CA

Wenn eine Station zum Senden bereit ist wird das Medium abgetastet. Sollte das Medium für die Zeit eines IFS frei sein kann die Station senden.

Sollte das Medium nicht frei sein muss der Sender für eine freies IFS warten plus eine zufällige back-off Zeit, sollte eine andere Station während der Back-off Zeit senden wird der back-off Timer gestoppt.

Beim Senden von Unicast Paketen passiert folgendess:

1. Die Sation wartet fuer DIFS bevor sie sendet
2. Der Empfänger bestätigt nachdem er für SIFS gewartet hat wenn das Paket korrekt empfangen wurde

![retrans](retrans.png)



## DCF CSMA/CA mit RTS/CTS

Beim Senden von Unicast Paketen:

1. Warte auf DIFS -> Die Station kann RTS mit NAV senden
2. Bestätigung durch CTS nach SIFS
3. Der Sender kann jetzt seine Daten senden, er bekommt ACK zurück


> Network Allocation Vector(NAV)
> Parameter der die Zeit bestimmt wie lange das Datenpaket das Medium braucht


![dcfcsmarts](dcfcsmarts.png)


## Point Coordination Function(PCF)

Es handelt sich um einen Mechanismus, der in drahtlosen lokalen Netzwerken (WLANs) in Zusammenarbeit mit der "Distributed Coordination Function" (DCF) gemäß dem IEEE 802.11-Standard eingesetzt wird.

Im PCF-Modus fungiert ein Zugriffspunkt im WLAN-Netzwerk als Punkt-Koordinator. Der Punkt-Koordinator plant und verwaltet den Zugriff auf das drahtlose Medium für alle Stationen (Client-Geräte) innerhalb seines Abdeckungsbereichs. Dadurch können zeitkritische Datenverkehr, wie Sprache oder Video, priorisiert und effizienter bedient werden.

Der PCF-Modus wechselt sich mit dem DCF-Modus ab. Während der konfliktfreien PCF-Periode fragt der Punkt-Koordinator die Stationen (Client-Geräte) ab, um Daten zu senden und kontrolliert den Zugriff auf das Medium. Nach der PCF-Periode wechselt das Netzwerk wieder in den DCF-Modus, in dem die Stationen um den Zugriff auf das Medium mit dem CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) Protokoll konkurrieren.