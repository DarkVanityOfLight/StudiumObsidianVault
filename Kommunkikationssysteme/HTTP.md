

Eine HTTP Verbindung läuft folgendermaßen ab:
Der Client initiiert eine [TCP](Transmission%20Controll%20Protocol(TCP).md) Verbindung zum Server auf Port 80, der Server akzeptiert die Verbindung und die HTTP Nachrichten werden ausgetauscht, danach wird die Verbindung wieder geschlossen.

## Non-Persistent HTTP

Bei Non-Persistent HTTP wird eine TCP Verbindung geöffnet, ein Objekt wird gesendet und die Verbindung wird wieder geschlossen.
Sollten wir mehrere Sachen Downloaden müssen, benötigen wir mehrere Verbindungen.

Wir benötigen eine RTT um die TCP Verbindung aufzubauen, eine RTT für die HTTP Request und die ersten Bytes der Antwort, plus die Zeit die es benötigt die Datei zu übertragen.

$$n \cdot (2RTT + FTT_{n})$$
wobei $n$ die Anzahl an Objekten ist die gesendet werden müssen
## Persistent HTTP

Eine TCP Verbindung wird geöffnet und es werden mehrere Objekte über eine einzelne TCP Verbindung gesendet. Danach wird die Verbindung wieder geschlossen.

Wir benötigen eine RTT um die TCP Verbindung aufzubauen, eine RTT für die HTTP Request und die ersten Bytes der Antwort, plus die Zeit die es benötigt die Dateien zu übertragen.
(ohne Pipelining)
$$RTT + n\cdot(RTT + FTT_{n})$$
wobei $n$ die Anzahl an Objekten ist die gesendet werden müssen.
## Pipelining

Wenn kein Pipelining implementiert ist, wird eine neue Request immer nur dann gestartet wenn wir die vorherige Antwort Empfangen haben, dadurch benötigen wir eine RTT für jedes Objekt.

Verwenden wir Pipelining müssen wir nicht auf vorherige HTTP Requests warten, dadurch ist es möglich alle Objekte in einer RTT zu erhalten

$$RTT_{tcp} + RTT_{req} + FTT_{0}+ RTT_{add} + \max\lbrace FTT_{1}, FTT_{2}, ...\rbrace$$
