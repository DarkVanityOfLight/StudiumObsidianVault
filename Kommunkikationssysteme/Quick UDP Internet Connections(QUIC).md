

QUIC ist ein [Application Layer](Application%20Layer.md) Protokoll basierend auf UDP, es wird verwendet um die Performance von HTTP zu verbessern.

Während der Herkömmliche HTTPS Verbindungsaufbau 2 Handshakes benötigt(TCP + TLS) braucht QUIC nur einen.

## Zuverlässigkeit

Der Sender packt einen oder mehr Frames in ein QUIC Paket, der Empfänger bestätigt alle Pakete die er erhält und verarbeitet.
QUIC Pakete die verloren gegangen sind werden nicht erneut übertragen, sondern die Daten die benötigt werden, werden in einem neuen Frame gesendet. Dafür sollten die Endpoints die Neuübertragung über die Übertragung von neuen Daten stellen.

## Congestion Control
Congestion Control passiert beim Sender, dabei kann der Sender den Algorithmus wählen den er verwendet, ACK Frames zählen nicht als "bytes in flight" werden also auch nicht durch Congestion Control beeinflusst.
Der Verlust von ACK Paketen kann von QUIC jedoch erkannt werden und die Congestion Control angepasst werden. QUIC endpoints koennen Explicit Congestion Notification(ECN) verwenden um congestion zu erkennen und zu behandeln.


## Sicherheit

QUIC verwendet einen Diffie-Hellman basierten Verbindungs Aufbau und ist darauf fokussiert mit 0-RTTs eine Sichere Datenübertragung bereitzustellen. Dies wird durch einen sogennante "Zwischenschluessel" oder "intermediat cryptographic key" ermöglicht, der Server Antwortet irgendwann mit seinem Teil des Schlüssels, ab dem Punkt wechseln Client und Server zu einem stärkeren Schlüssels.

![quicsec](quicsec.png)

Dies Funktioniert aber nur wenn vorher schon mal eine Verbindung bestanden hat und ein Secret aus dieser Verbindung gespeichert wurde.




