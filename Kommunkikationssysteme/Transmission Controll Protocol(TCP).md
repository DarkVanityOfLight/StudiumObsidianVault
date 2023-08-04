
TCP findet zwischen einem Sender und einem Empfänger statt, es bietet einen zuverlässigen in-order byte Stream, dass heißt es gibt keine Nachrichten grenzen. Die Verbindung ist außerdem full duplex, beide Seiten können gleichzeitig die maximum segment size(MSS) senden. Zur Bestätigung werden "cumulative ACKs" verwendet. TCP ist "gepipelined" das heißt TCP congestion und flow control setzen die Fenster groeße. TCP Verbindungen orientieren sich an Verbindungen, es gibt also einen Handshake bevor Daten versendet werden, dabei werden Kontrollnachrichten ausgetauscht.
Da TCP Flow controll implementiert wird es nicht passieren das der Sender den Empfänger mit Nachrichten überfordert.

## Sequenz Numbers and ACKs

Die Sequenznummer entspricht der Byte-Stream nummer des ersten Bytes in den Daten des Segments, als Antwort erwartet der Sender nun die Sequenznummer des nächsten bytes und ein Cumulatitives ACK

## Timeout

Der Timeout wert muss länger als unsere Round Trip Time(RTT) sein, doch diese variiert. Wählen wir unsere Timout Zeit zu kurz könnten wir zu früh Timeouten und eine unnötige Neuübertragung senden, wählen wir sie zu lang reagieren wir nur langsam auf Segmentverluste.

Auch ist es schwer die RTT zu schätzen, eine einfache loesung ist die SampleRTT dabei wird die Zeit zwischen Übertragung un ACK gemessen.
Ein besserer Ansatz ist jedoch der Exponential weighted moving average(EWMA):
$$EstimatedRTT = (1-\alpha) \cdot EstimatedRTT + \alpha \cdot SampleRTT$$

dabei verringert sich der Einfluss von früheren Übertragungen Exponentiell schnell.

Das Timeout Intervall wird dann meistens so gewählt:

$$TimeoutInterval = EstimatedRTT + 4\cdot DevRTT$$

$$DevRTT = (1- \beta) \cdot DevRTT + \beta \cdot |SampleRTT - EstimatedRTT|$$


## TCP Fast Retransmit

Sollte der Sender 3 zusaetzliche ACKs fuer die selben Daten erhalten, sendet er das noch nicht durch ACK bestätigten Segment mit der kleinsten Sequenznummer erneut.


## Flow Control

Sollte die [Network Layer](Network%20Layer.md) schneller Daten senden als die [Application Layer](Application%20Layer.md) sie verarbeitet tritt Flow Control in Kraft. Der Empfänger setzt die Buffer Size bei der Socket erstellung und der Freie Bufferplatz wird im `rwnd` Feld des TCP Header mitgesendet. Der Sender passt dann seine Rate an unACKed("in-flight") Daten an die Empfangenen `rwnd` an.
Dadurch wird garantiert das der Buffer nicht überlaeuft. 

## Connection Management

Der Empfaenger und der Sender "connecten" bevor sie Daten austauschen, dabei werden TCP Variablen, wie z.b Sequenz Nummern, Buffer und Flow Control Info, initialisiert. Dabei wird ein "Three way Handshake" verwendet:

Der Client sendet ein TCP SYN Segment zum Server und spezifiziert die start Sequenznummer.

Der Server Empfängt SYN und antwortet mit einem SYN+ACK Segment. Der Server erstellt einen Buffer und Spezifiert die Sequenznummer des Servers. 

Der Client erhält SYN+ACK und Antwortet mit einem ACK Segment das Daten enthalten kann.

Eine Verbindung wird durch folgende Sequenz geschlossen.

Der Client sendet ein TCP FIN Segment.

Der Server erhaelt das FIN Segment und Antwortet mit ACK, daraufhin schließt er die Verbindung und Antwortet mit FIN

Der Client erhält FIN und Antwortet mit ACK, der client geht in den "timed wait" State und Antwortet mit ACK auf alle FINs

Der Server erhaelt ein ACK.
Die Connection ist geschlossen.


## Congestion Control

Congestion passiert wenn zu viele Quellen zu viele Daten zu schnell senden und das Netzwerk dies nicht mehr handeln kann. Dadurch kommt es zu Langen Wartezeiten in den Warteschlangen der Router und Paket loss, sollten die Router Schlangen voll sein.
Es gibt viele Formen von Congestion Control und es ist ein wichtiges Problem. Sollten Pakete wegen Congestion gedropt werden ist die gesamte Sende Zeit bisher verschwendet gewesen.

Eine Möglichkeit Congestion zu bemerken ist zu beobachten wie sich der Paket loss/delay verhält. Dies wird auch von TCP verwendet und nennt sich End-to-End Congestion Control.

Eine weitere moeglichkeit wäre das der Router Feedback an die Hosts gibt.

Bei TCP wird die Senderate durch den `cwnd` Teil des Headers angegeben. Wir senden `cwnd` Bytes und warten eine RTT für die ACKs, dann senden wir mehr Bytes.

$$TCP\;rate = \frac{cwnd}{RTT} \left[\frac{Byte}{sec}\right]$$

der Sender beschränkt also die Übertragung:
$$LastByteSent - LastByteAcked \leq \min\lbrace cwnd, rcvwnd \rbrace$$
dabei wird $cwnd$ Dynamisch angepasst, indem auf das Netzwerk geachtet wird. Sollte der Sender also ein Timeout oder 3 ACKs erhalten veringert er `cwnd`. Dies wird durch 3 unterschiedliche Mechanismen angepasst:
- Additive Increase, Multiplicative Decrease(AIMD)
- Slow start
- Conservative after timeout events

### Additive Increase Multiplicative Decrease(AIMD)

Der Sender erhöht die Sende rate bis er ein Packet Loss entdeckt, dann verringert er die Rate.

Dabei wird die Rate Additiv Erhöht und zwar genau um 1 Segment jedes mal bis ein Packet Loss entdeckt wird.

Wenn wir ein triple duplicate ACK(TCP Reno) erhalten oder auf 1 MSS(maximum segment size) gesetzt wenn wir einen Verlust entdecken(TCP Tahoe)

Dabei zeigt sich ein "Sägezahn Muster".
AIMD wird benutzt um die Bandbreite auszutesten.


AIMD ist ein verteilter, asynchroner Algorithmus der in der Praxis gezeigt hat das er die congestion raten im Netzwerk optimiert und wünschenswerte Stabilität bietet.

### TCP Slow Start

Wir erhöhen die Sende rate exponentiell bis wir unser erstes Loss Event erhalten:
Zuerst ist `cwnd` = 1MSS, dann verdoppeln wir `cwnd` jede RTT indem wir für jedes ACK `cwnd` erhöhen. Das heißt die Anfangs rate ist langsam aber wächst dann exponentiell schnell.

Wenn wir 3 duplicate ACKs erhalten halbieren wir `cwnd` und ab dem Zeitpunkt erhöhen wir die Sende rate nur noch Linear. 
Nach einem Timeout setzen wir `cwnd` zurück auf 1 MSS und lassen das Fenster bis zu einem gewissen Punk exponentiell wachsen und ab dort linear.

Dieser Punkt wird dort gesetzt wo `cwnd` zur hälfte seines vorherigen Wertes erreicht.

--- 

Das ganze laueft also folgendermaßen ab:

Sollte das `CongWin` kleiner als der `Threshold` sein sind wir in der [TCP Slow Start](#TCP%20Slow%20Start) Phase in der wir exponentiell wachsen.

Sobald `CongWin` ueber dem `Threshold` ist wechseln wir in die congestion-avoidance(CA) indem unser `CongWin` nur noch linear waechst.

Erhalten wir ein triple duplicate ACK, wird der `Threshold` auf `CongWin/2` gesetzt und `CongWin` auf 1 MSS bei Taheo und auf `Threshold` bei Reno gesetzt.

Sollte ein Timeout auftreten setzen wir `Threshold` auf `CongWin/2` und `CongWin` wird auf 1 MSS gesetzt.

Ignorieren wir die Slow Start Phase sieht unser Durchsatz folgendermaßen aus:

Sei $W$ die Window groesse in Bytes an dem Punk wenn unser Loss auftritt, die Durchschnittliche Window groesse ist dann $\frac{3}{4}W$ und der Durchsatz $\frac{3}{4}W$ pro $RTT$

$$\text{avg TCP thruput} = \frac{3}{4} \frac{W}{RTT} \frac{bytes}{sec}$$

## TCP CUBIC

Sei $W_{max}$ die sende Rate bei der der Loss entdeckt wurde, da sich der Congestion state wahrscheinlich nicht stark geändert hat gehen wir anfangs schneller nach $W_{max}$, aber sobald wir in die näher kommen nähern wir uns langsamer.

![cubic](cubic.png)

Sollten wir $W_{max}$ erreichen machen wir kleinere Schritte nahe an $W_{max}$ und immer grössere Schritte wenn wir weiter weg von $W_{max}$ sind.


## Fairness

Unter Idealen Bedingungen ist TCP Fair, aber nur wenn alle beteiligten die selbe RTT haben und jeder nur eine bestimmte Anzahl an Sockets hat.
