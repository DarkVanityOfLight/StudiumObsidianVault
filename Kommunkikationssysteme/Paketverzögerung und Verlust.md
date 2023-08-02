
Pakete werden in einer Warteschlange von den Routern gespeichert während sie darauf warten gesendet zu werden. Falls die Rate mit der Pakete ankommen die sende Rate übersteigt wächst die Schlange.

Paketverlust tritt dann auf wenn der Speicher der die Pakete hält zu voll wird.

Die Paketverzögerung besteht aus $4$ Quellen:

![delay](delay.png)

Die Gesamtverzögerung kann dann folgendermaßen berechnet werden.

$$d_{nodal} = d_{proc} + d_{queue} + d_{trans} + d_{prop}$$
Das Processing Delay besteht aus:
- Das Prüfen auf Bit-Fehlern
- Bestimmung des Ausgangslinks

und berechnet sich folgendermaßen
$d_{trans} = \frac{L}{R}$
wobei $L$ die Paketlaenge ist und $R$ die Übertragungsrate(bps) des Links

Das Queueing Delay besteht aus:
- Die Zeit die wir am auf die Übertragung in der Warteschlange warten

und berechnet sich aus der Durchschnittlichen Paketankunftsrate $a$, der Paketlaenge $L$ und der Link Bandweite $R$
$$\frac{L\cdot a}{R} : \frac{Ankunftsrate}{Servicerate}$$

Das Propagation Delay berechnet sich aus der Länge des Physischem Links $d$ und der Ausbreitungsgeschwindigkeit $v$:
$$d_{prop}= \frac{d}{v}$$


## Packetloss

Die Queue(auch genannt der Buffer) hat eine endlich Kapazität, sollte ein Paket an einer vollen Queue ankommen wird es "gedroppt" und geht verloren. Verlorene Pakete können von der vorherigen Node, der Quelle oder gar nicht erneut übertragen werden.

## Durchsatz

Der Durchsatz ist die Rate(bits/Zeit einheit) mit welcher Bits vom Sender zum Empfänger gesendet werden. Links auf dem Weg können den Durchsatz einschränken.