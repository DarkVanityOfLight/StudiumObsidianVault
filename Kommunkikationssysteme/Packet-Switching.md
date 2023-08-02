
Daten werden als kleinere Teile durch das Netz gesendet.

Jeder Ende zu Ende Datenstrom wird in Pakete aufgeteilt, mehrere Nutzer Teilen sich die Netzwerk Ressourcen, wobei jedes Paket die volle Bandbreite verwendet, dadurch werden alle Ressourcen verwendet so wie sie gebraucht werden.

## Congestion
Dabei kann es passieren das mehr Ressourcen gebraucht werden als verfügbar sind.
Dann müssen die Pakete in einer Warteschlange warten bis der Link frei ist. 


## Store and Forward
Pakete wandern immer einen "Hop" einzelne Knoten erhalten das gesamte Paket bevor es weiter gesendet wird.

## Beispiel

Gegeben ist ein $1 \frac{Gb}{s}$ link. Jeder der $N$ Nutzer verwendet $100\frac{Mb}{s}$ wenn er aktiv ist, jeder Nutzer ist aktiv $10\%$ der Zeit

Wie viele Nutzer können das System Verwenden.

Bei $35$ Benutzern ist die Wahrscheinlichkeit, dass mehr als $10$ Benutzer gleichzeitig aktiv sind, kleiner als $0,0004$.
$$\sum\limits^{35}_{i=11} \left(35 \atop i\right)0.1^{i} \cdot 0.9^{35 -i}$$

[Circuit-Switching](Circuit-Switching.md)