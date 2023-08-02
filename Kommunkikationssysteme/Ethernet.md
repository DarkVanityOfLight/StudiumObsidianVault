

Ein Ethernet Frame setzt sich folgendermaßen zusammen:

![eth](eth.png)

Die Preamble wird dazu genutzt um die Empfaenger Clock Rate zu synchronisieren, sie besteht aus 7 bits $10101010$ gefolgt von einem Byte $10101011$

In den Adress Feldern steht die 6 Byte Quell und Zieladresse, falls der Adapter ein Paket mit passender Zieladresse oder Broadcastadresse erhält wird das Paket in die [Network Layer](Network%20Layer) weiter geschickt, ansonsten wird der Frame fallen gelassen.

Der Typ zeigt an welches Protokoll verwendet wird, meistens ist dies IP aber es gibt auch andere. 

Der CRC Teil besteht aus der [CRC](Fehlererkennung.md#CRC)-Checksumme, sollte ein Fehler entdeckt werden wird das Paket gedroppt.

Das Protokoll das von Ethernet verwendet wird ist unslotted [CSMA/CD](Random%20Access.md#CSMA%20with%20Collision%20Detection(CSMA/CD)) mit Exponentiellen Back-off. 

Außerdem ist Ethernet Verbindungslos, das heißt es gibt keine Handshakes.
Da NICs keine ACK or NAKs senden werden gedroppte Pakete nur erneut gesendet wenn dies auf einer höheren Layer implementiert wurde.


