
Die Transport schicht dient dazu  logische Verbindungen zwischen Prozessen auf verschiedenen Hosts aufzubauen.
Der Sender teilt Anwendungsnachrichten in Segmente auf und gibt diese an die [Network Layer](Network%20Layer.md) weiter, der Empfänger baut die Pakete wieder zusammen und gibt sie an die [[Application Layer]] weiter.
Es gibt zwei Transport Protokolle für Internet Anwendungen: TCP und UDP.

Im gegensatz zur [Network Layer](Network%20Layer.md) ist die Transport Layer nicht für die Kommunikation zwischen Hosts sonder für die Kommunikation zwischen Prozessen zuständig. Sie benötigt und verbessert [Network Layer](Network%20Layer.md) Services.

## Transmission Control Protocol(TCP)
- Zuverlässige Zustellung in der Reihenfolge der Absendung
- Staukontrolle(Congestion Controll): TCP passt die Datenübertragungsrate an, um Staus in einem Netzwerk zu vermeiden und die Netzwerkleistung zu Optimieren.
- Flusskontrolle(Flow Controll): TCP reguliert den Datenfluss zwischen Sender und Empfänger, um eine Überlastung des Empfängers zu verhindern.
- Verbindungsaufbau: Bevor der eigentliche Datenaustauasch beginnt, etabliert TCP eine zuverlässige Verbindung zwischen Sender und Empfänger.

## User Datagram Protocol
- Keine Garantie über die Reihenfolge und Zustellung von Paketen


## Multiplexing/Demultiplexing

Der Sender verarbeitet die Daten von mehreren Sockets und fügt den Transport Header hinzu der später zum Demultiplexing verwendet wird.

Der Empfänger benutzt den Transport Header um Segmente an die richtigen Sockets weiterzuleiten.

Der Host erhält ein IP Datagram, jedes Datagram hat eine Quell und eine Ziel Adresse. Jedes Datagram hat außerdem ein Transport-Layer Segment,jedes dieser Segemente hat eine Ziel und eine Quell Port Nummer. Der Host benutzt die IP Adresse und die Port Nummer um ein Segment zum Richtigen Socket zu senden.

UDP benötigt also nur die Ziel Adresse und der Ziel Port.

Im Gegensatz dazu werden TCP Sockets durch ein 4er Tupel identifiziert, die Quell IP, der Quell Port, die Ziel IP und der Ziel Port. Der Empfänger benutzt alle 4 dieser Werte um den Ziel Socket zu bestimmen. Da wir alle 4 dieser Werte benötigen muss der Server auf eingehende Verbindungen warten, der Server verwendet dafür einen Listening Socket, jede Verbindung die dieser erhält wird auf einen neuen Socket gelegt sodass der Listening Socket niemals Daten verschickt/empfängt.




