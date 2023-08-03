
ICMP wird von Hosts und Routern verwendet um auf Netzwerk Ebene zu Kommunizieren, zb. um Fehler zu melden oder Pings. Es ist quasi eine Netzwerkschicht "ueber" IP, da ICMP Nachrichten in IP Datagrammen Transportiert werden. ICMP Nachrichten bestehen aus einem Typ, einem Code und die ersten 8 bytes des IP Datagramms das Fehler verursacht.

## Traceroute

Die Quelle sendet eine Menge von UDP Segmenten zum Empfänger. Die erste Menge hat eine Time to Live(TTL) von 1, die zweite 2 usw. Die n-te Menge von Datagrammen erreicht den n-ten Router, der Router schickt eine ICMP Nachricht(Typ 11, code 0, TTL expired). Die Nachricht kann den Routernamen und die IP-Adresse beinhalten, an der Quelle angekommen wird die Round Trip Time(RTT) aufgeschrieben. Irgendwann erreicht ein UPD Segment den Ziel Host, dieser schickt ICMP port unreachable(Typ 3, Code 3) zurück und die Quelle stopt.