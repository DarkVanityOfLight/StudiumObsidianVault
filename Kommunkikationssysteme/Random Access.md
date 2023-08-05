
Bei Random Access Protocols schickt jede Node ihr Paket mit der vollen Kanal Datenrate $R$, es gibt keine Koordination zwischen den Nodes, wenn zwei oder mehr Nodes gleichzeitig Daten übertragen kommt es zur Kollision, das Protokoll spezifiziert wie man Kollisionen Entdeckt und wie man mit ihnen umgeht. Beispiele dafür sind ALOHA, slotted ALOHA, CSMA, CSMA/CD, CSMA/CA.

![ramac](ramac.png)

## Slotted ALOHA

Alle Frames haben die selbe groeße, es gibt unterschiedliche Slots die immer genau groß genug sind um einen Frame zu übertragen, die Node überträgt immer zu beginn des Slots, dafür müssen alle Nodes Synchronisiert sein. Falls 2 oder mehr Nodes übertragen merken alle die Kollision.

### Ablauf

Eine Node überträgt einen Frame in nächsten Slot.

Falls es keine Kollision gibt kann die Node den nächsten Frame im nächsten Slot senden.
Falls es jedoch zur Kollision kommt überträgt die Node im nächsten Slot mit der Wahrscheinlichkeit $p$ bis es Funktioniert, da es sonnst zur selben Kollision erneut kommen würde.

### Vorteile
Eine einzelne Node kann immer mit der vollen Bandbreite des Kanals senden.
Nur die Slots müssen zwischen den Nodes synchronisiert werden.
Das Protokoll ist einfach.

### Nachteile
Kollsionen verschwenden Slots und es kommt zu unbenutzten Slots. 
Nodes könnten Kollisionen schneller erkennen als es braucht um das Paket zu senden und die Clocks müssen synchronisiert werden.


## Effizienz

$N$ Nodes senden in jedem Slot mit der Wahrscheinlichkeit $p$:

Die Wahrscheinlichkeit das eine Node in einem Slot erfolgreich uebertraegt ist $p(1-p)^{N-1}$
Die Wahrscheinlichkeit das irgendeine Node in einem Slot erfolgreich uebertraegt: $Np(1-p)^{N-1}$


$$\begin{align}
P(p) &= Np(1-p)^{N-1}\\
P'(p) &= -N(N p -1)(1-p)^{N-2}
\end{align}$$
Jetzt suchen wir nach den Maxima

$$\begin{align*}
-N(N p -1)(1-p)^{N-2} &= 0\\
-(-p +1)^{N-2} (N p -1) &= -N(N p -1)(1-p)^{N-2}\\
-(-p +1 )^{N-2} (N p -1) &= 0 | \cdot -(-p +1 )^{N-2}\\
Np-1 &= 0\\
Np &= 1\\
p &= \frac{1}{N}\\

\end{align*}$$
Wenn wir jetzt $N$ gegen unendlich Streben lassen erhalten wir die Maximale Effizienz

$$
\begin{align*}
P(p) =& Np(1-p)^{N-1} | p = \frac{1}{N}\\
&N \frac{1}{N}(1- \frac{1}{N})^{N-1}\\
&\frac{\lim_{N\to\infty}\left( 1 - \frac{1}{N}\right)^{N}}{\lim_{N\to\infty}\left(1 - \frac{1}{N}\right)^1}\\\\
&\lim_{N\to\infty}\left( 1 - \frac{1}{N}\right)^{N} = \frac{1}{e}

\end{align*}
$$

Der Channel wird also nur ca $37\%$ der Zeit wirklich genutzt.

## Carrier Sense Multiple Access(CSMA)

Die einfachste Form von CSMA sieht folgendermaßen aus:
Falls der Kanal leer ist, sende den Frame.
Falls etwas auf dem Kanal liegt, warte.

Es gibt unterschiedliche Arten von CSMA

1-persistent
Falls der Kanal leer ist, sende den Frame mit einer Wahrscheinlichkeit von $1$.
Falls etwas auf dem Kanal liegt, warte.

p-persistent
Falls der Kanal leer ist, sende den Frame mit einer Wahrscheinlichkeit $p$ und warte auf den nächsten Slot mit einer Wahrscheinlichkeit von $1-p$
Falls etwas auf dem Kanal liegt, warte auf den nächsten Slot.

Non-persistent
Falls der Kanal leer ist, sende den Frame.
Falls etwas auf dem Kanal liegt, warte eine Zufällige Zeit und probiere erneut.

Obwohl wir erst Testen ob der Kanal frei ist kann es zu Kollisionen kommen, da es ein Propagation Delay gibt kann es passieren das sich zwei Nodes nicht hören obwohl beide ihre Übertragung gestartet haben, sollte es zu einer Kollision kommen ist die gesamte Zeit der Übertragung verschwendet, deswegen gibt es CSMA/CD

### CSMA with Collision Detection(CSMA/CD)

Bei CSMA/CD wir die Kollision entdeckt und die Übertragung direkt abgebrochen, so kommt es zu weniger Verschwendung des Kanals.

Die Entdeckung dieser Kollision ist relativ simple in Verkabelten Systemen, jedoch schwerer in Kabellosen Systemen, da der Empfänger während des Sendens abgeschaltet wird.

1. Der Adapter Empfängt ein Datagram von der [[Network Layer]] und erstellt den Frame
2. Der Adapter testet den Kanal
	- Falls der Kanal leer ist sender er
	- Sonst wird gewartet bis der Kanal leer ist
3. Wenn der Adapter den gesamten Frame ohne Kollision hübertraegt ist er fertig
4. Wenn der Adapter eine andere Übertragung bemerkt bricht er die Übertragung ab und schickt ein Störsignal
5. Nach dem Abbrechen geht der Adapter in den "Expotentiellen Backoff"
	- Nach der $m$ten Kollision waehlt der Adapter $K$ zufaellig aus $\lbrace0, 1, 2...2^{m}-1\rbrace$ und wartet $K\cdot 512$ bit Zeiten und geht danach zu Schritt 2
	- Mehr Kollisionen führen zu einem höherem Back off Intervall

Bei Ethernet besteht das Störsignal aus 48 Bits. Gehen wir von einer Datenrate von $100 \frac{Mbit}{s}$ aus ist unsere Bit Zeit $0.01\mu$, damit ist für $K=1023$ die Warte Zeit ca. $5ms$

### Effizienz

Sei $t_{prop}$ das Maximale Propagation Delay zwischen zwei Nodes in LAN und $t_{trans}$ die Zeit zum übertragen eines Max-Size Frames. Dann gilt

$$\text{Effizienz} = \frac{1}{1+5 \frac{t_{prop}}{t_{trans}}}$$

Die Effizienz geht gegen $1$ wenn:
- $t_{prop}$ gegen $0$ geht
- $t_{trans}$ gegen $\infty$ geht


## CSMA with Collision Avioadance (CSMA/CA 802.11)

In Kabellosen Netzwerken ist es deutlich schwerer eine Kollision zu entdecken da das Signal deutlich schwächer oder auch gar nicht ankommen könnte. 

Auch kann es sein das unnötig gewartet wird:

B sendet an A, C möchte an ein anderes Terminal D senden.
C muss warten da C merkt, dass das Medium in Verwendung ist.
Aber A ist außerhalb der Funkreichweite von C, daher ist das Warten nicht notwendig. C ist "exposed" gegenüber B.

Deswegen gibt es 802.11, beim Sender sieht das folgendermaßen aus:

1. Falls der Kanal für DIFS leer ist, sende den gesamten Frame
2. Sollte der Kanal belegt sein, warte eine zufällige Zeit. Ein Timer zählt herunter wenn der Kanal leer ist, sollte dieser auslaufen übertrage das Paket, falls wir kein ACK zurückerhalten erhöhe das Backoff Intervall und wiederhole 2.

und beim Empfänger:

Falls der Frame als OK empfangen wurde:
Sende ACK nach SIFS.

Aber wir können noch weiter gehen:

Die Idee ist das der Sender den Kanal reserviert mit der Hilfe von kleinen Reservierpacketen.


Der Sender schickt erst ein kleines "request-to-send"(RTS) Paket zum Access Point mit der Hilfe von CSMA
Sollte so ein RTS Paket Kollidieren ist das nicht schlimm da sie sehr kurz sind.
Der Access Point broadcasted dann ein "clear-to-send"(CTS) als Antwort auf RTS.
Das CTS wird von allen Nodes gehört und der Sender übertragt seine Date während die anderen warten ^f3976f
