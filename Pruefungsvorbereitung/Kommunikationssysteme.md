
## ISO/OSI Modell
- [Application Layer](Application%20Layer.md)
- (Presentation Layer)
- (Session Layer)
- [Transport Layer](Transport%20Layer.md)
- [Network Layer](Network%20Layer.md)
- [Link Layer](Link%20Layer.md)
- [Physical Layer](Physical%20Layer.md)

## Introduction

### Circuit Switching

Time Division Multiplexing(TDM) Jeder User hat einen Zeitslot

Frequency Division Multiplexing(FDM) Jeder User eine Frequenz.

Gegeben ist ein $1 \frac{Gb}{s}$ link. Jeder der $N$ Nutzer verwendet $100\frac{Mb}{s}$ wenn er aktiv ist, jeder Nutzer ist aktiv $10\%$ der Zeit

Wie viele Nutzer können das System Verwenden.
Wenn 
$$\frac{1\frac{Gb}{s}}{100\frac{Mb}{s}} = 10$$


### Packet Switching

Daten werden als Pakete durch das Netz geschickt, jedes Paket verwendet die volle Bandbreite

#### Store and Forward
Pakete wandern einen Hop und werden erst weitergesendet wenn das gesamte Paket angekommen ist

Gegeben ist ein $1 \frac{Gb}{s}$ link. Jeder der $N$ Nutzer verwendet $100\frac{Mb}{s}$ wenn er aktiv ist, jeder Nutzer ist aktiv $10\%$ der Zeit

Wie viele Nutzer können das System Verwenden.

Bei $35$ Benutzern ist die Wahrscheinlichkeit, dass mehr als $10$ Benutzer gleichzeitig aktiv sind, kleiner als $0,0004$.
$$\sum\limits^{35}_{i=11} \left(35 \atop i\right)0.1^{i} \cdot 0.9^{35 -i}$$

### Transition Delay

$$d_{nodal} = d_{proc} + d_{queue} + d_{trans} + d_{prop}$$

$L$ Paket Länge in bits
$R$ Link Übertragungsrate in bps
$$d_{trans} = \frac{L}{R}$$
$d$ Länge des Links
$v$ Ausbreitungsgeschwindigkeit
$$d_{prop} = \frac{d}{v}$$


## Physical Layer

Die Physische Schicht definiert die Spezifikationen für die Aktivierung, Aufrechterhaltung und Deaktivierung der physischen Verbindungen zwischen Endsystemen

### Nyquist's Theorem

In einem ungestörten Kanal mit einer Bandbreite $H$ und $V$ diskreten Signalleveln ist die Maximale  Datenübertragungsrate:
$$2\cdot H\cdot \log_{2} V$$
### Shannon's Theorem

In einem Kanal mit einer Bandbreite $H$ $V$ diskreten Signalleveln und einer Signal-to-Noise Ration $\frac{S}{N}$ ist die Maximale Datenübertragung:

$$H \cdot \log_{2}(1 + \frac{S}{N})$$

### Modulationstechniken

Zuerst wird ein Digitales Signal in ein Analoges Signal übersetzt, von diesem wird dann die Mittenfrequenz auf die Trägerfrequenz verschoben.

#### Amplitude Shift Keying(ASK)

ASK ist sehr simple und benötigt nur wenig Bandweite ist dafür deutlich anfälliger für Interferenzen.

![ask](ask.png)

#### Frequency Shift Keying(FSK)

Benötigt eine grössere Bandbreite da die Bandbreite von der Distanz der Trägerwellen-Frequenzen abhängt.

![fsk](fsk.png)


#### Phase Shift Keying(PSK)
Phase Shift Keying ist komplexer aber dafür auch nicht so anfällig für Interferenzen.

![[psk.png]]

#### Quadrature PSK
2 Bits -> 1 Symbol, unterschiedliche Phasenverschiebung = unterschiedliche Bitfolge
#### Quadratur AM QAM
ASK + PSK, dadurch koennen $n$ bits auf ein Symbol kodiert werden.


### Encodings

#### Non-Return To Zero(NRZ)
1 = Hohe Spannung
0 = Niedrige Spannung

Baseline Drift und nicht Selbsttacktend

#### Non-Return To Zero Inverted(NRZ-I)

1 = Spannungsänderung

Kein Baseline drift bei aufeinanderfolgenden 1en jedoch bei 0len und nicht Selbsttacktend

#### Manchester

2 Signale = 1 Bit
Erster Teil das zu übertragende Bit, zweiter das Invertierte Bit

kein Baseline drift, Selbsttacktend, $1 Baud = 0.5 bit$

#### 4b5b
4bit Sequenz -> 5bit Sequenz
Niemals mehr als 3 Konsekutive Nullen
Darstellung durch NRZ-I -> keine aufeinanderfolgenden 1en,
Selbsttacktend, $1baud = 0.8 bit$

### Multiplexing
In 4 Dimensionen
- Raum $s_i$
- Zeit $t$
- Frequenz $f$
- Code $c$

#### Frequenzmultiplexing

Ein Kanal bekommt ein bestimmtes Band des Spektrums für die gesamte Zeit. 

##### Vorteile:
- Keine Dynamische Koordination nötig
- Funktioniert auch bei Analogen Signalen

##### Nachteile:
- Bandbreite wird verschwendet wenn Verkehr ungleich verteilt ist
- Nicht sehr flexibel
- Es werden Guard Spaces benötigt

### Zeitmultiplexing
Ein Kanal bekommt das gesamte Frequenz Spektrum für eine bestimmte Zeit.

##### Vorteile:
- Nur ein Träger im Medium auf einmal
- Auch bei vielen Nutzern wird das Medium noch Effektiv verwendet.

##### Nachteile:
- Eine Genaue Synchronisation der Zeit ist benötigt.

### Zeit und Frequenzmultiplexing
Zeit und Frequenz Multiplexing kombiniert die beiden Methoden zu einer neuen. Dabei bekommt ein Kanal ein gewisses Frequenz band für eine bestimmte Zeit.


##### Vorteile
- Höheres Multiplexing Level
- Mehr Schutz gegen Abhören
- Schutz gegen einzelne Interferenzen

##### Nachteile
- Viel Koordination benötigt


### Code Multiplexing
Jeder Kanal hat einen bestimmten Code und alle Kanäle benutzen das selbe Spektrum und senden zur gleichen Zeit.

##### Vorteile
- Sehr effektive Nutzung der Bandbreite
- Benötigt keine Synchronisation oder Koordination
- Guter Schutz gegen Interferenzen und Abhören

##### Nachteile
- Geringe Datenraten
- Komplexe Signal Regeneration 

## Link Layer

Hosts sind sogenannte Nodes, Kommunikationskanäle zwischen den Nodes nennt man Links. Die Link-Layer hat die Verantwortung dafür das die Daten von einer Node zu einer anderen Physisch benachbarten Node über einen Link Transportiert werden.
Ein Paket auf der Link Layer nennt man __Frame__.
Im Frame wird ein Header und ein Trailer hinzugefügt.

### CRC
Die Daten+$r$ nullen werden durch einen Generator der groesse $r+1$ geteilt und der Rest der länge $r$ an die Daten angehängt. Um zu ueberpruefen ob die Daten valide sind wird erneut durch den Generator geteilt.

### Multiple Access Links
Man unterscheidet zwischen Point-to-Point Links wie z.b. eine direkte Kabelverbindung zwischen zwei Hosts und Broadcast Links, wie zb. ein geteiltes Kabel mit mehreren Hosts.

### Multiple Access Protocolls
Wenn sich mehrere Nodes einen Brodcast Channel teilen kann es bei gleichzeitiger Übertragung zu einer Interferenz kommen, daraus folgt eine Kollision. MAPs legen die Regelen fest wer gerade senden darf.

#### Taking Turns

##### Polling
Ein Master informiert die Nodes wer gerade Senden darf.
- Einzelner Fehlerpunkt(Master)
- Extra Overhead
- Hohe Latency

##### Token Passing
Ein Token wird herumgereicht, der Token Besitzer darf Senden.
- Einzelner Fehlerpunkt(Token)
- Extra Overhead
- Hohe Latency

#### Random Access
Jeder darf jederzeit mit der vollen Bandbreite senden, kommt es zur Kollision gibt es Regeln wie man damit umgeht.

##### Slotted ALOHA
Alle Frames haben die selbe groesse, es gibt unterschiedliche Slots mit der genauen Frame groesse. Nodes übertragen zu beginn des Slots.
Alle Nodes müssen Synchronisiert sein, sollten mehr als 2 Nodes übertragen kommt es zur Kollision.

Kommt es zur Kollision sendet die Node im Nächsten Slot mit der Wahrscheinlichkeit $p$.

###### Vorteile
Eine einzelne Node kann immer mit der vollen Bandbreite des Kanals senden.
Nur die Slots müssen zwischen den Nodes synchronisiert werden.
Das Protokoll ist einfach.
###### Nachteile
Kollsionen verschwenden Slots und es kommt zu unbenutzten Slots. 
Nodes könnten Kollisionen schneller erkennen als es braucht um das Paket zu senden und die Clocks müssen synchronisiert werden.

###### Effizienz
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
##### Carrier Sense Multiple Access(CSMA)
Die einfachste Form von CSMA sieht folgendermassen aus:

Falls der Kanal leer ist, sende den Frame, sollte etwas auf dem Kanal liegen warte.

__1-persistent__
Falls der Kanal leer ist, sende den Frame mit einer Wahrscheinlichkeit von $1$.
Falls etwas auf dem Kanal liegt, warte.

__p-persistent__
Falls der Kanal leer ist, sende den Frame mit einer Wahrscheinlichkeit $p$ und warte auf den nächsten Slot mit einer Wahrscheinlichkeit von
$1-p$
Falls etwas auf dem Kanal liegt, warte auf den nächsten Slot.

__Non-persistent__
Falls der Kanal leer ist, sende den Frame.
Falls etwas auf dem Kanal liegt, warte eine Zufällige Zeit und probiere erneut.

Obwohl wir erst Testen ob der Kanal frei ist kann es zu Kollisionen kommen da es ein Propagation Delay gibt.
###### Collision Detection
Sobald eine Kollision entdeckt wird wird die Übertragung abgebrochen und ein Störsignal wird gesendet. Nach dem Abbruch geht der Adapter in den "Exponentiellen Backoff":
Nach der $m$-ten Kollision wählt $K$ Zufällig aus $\lbrace 0, 1, 2\dots 2^{m}-1\rbrace$ und wartet $K \cdot 512$ bit Zeiten.

Sei $t_{prop}$ das Maximale Propagation Delay zwischen zwei Nodes in LAN und $t_{trans}$ die Zeit zum übertragen eines Max-Size Frames. Dann gilt

$$\text{Effizienz} = \frac{1}{1+5 \frac{t_{prop}}{t_{trans}}}$$

Die Effizienz geht gegen $1$ wenn:
- $t_{prop}$ gegen $0$ geht
- $t_{trans}$ gegen $\infty$ geht

###### Collision Avoidance

In Kabellosen Netzwerken ist es deutlich schwerer eine Kollision zu entdecken da das Signal deutlich schwächer oder gar nicht ankommen könnte.

Auch kann es sein das unnötig gewartet wird:
$B$ sendet an $A$, $C$ möchte an ein anderes Terminal $D$ senden.
$C$ muss warten da $C$ merkt, dass das Medium in Verwendung ist.
Aber $A$ ist außerhalb der Funkreichweite von $C$, daher ist das Warten nicht notwendig. $C$ ist "exposed" gegenüber $B$.

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
Das CTS wird von allen Nodes gehört und der Sender übertragt seine Date während die anderen warten

### Adressierung

Auf der Link Ebene wird die MAC(Medium Access Control) Adresse verwendet um Hosts zu identifizieren. Jede NIC(Network Interface Card) hat eine MAC Adresse

### Ethernet Frame

Ein Ethernet Frame hat eine Präambel aus 7 Bytes $10101010$, gefolgt von einem Byte $10101011$ dies wird genutzt um die Empfänger clock zu Synchronisieren.

Daraufhin folgt die Ziel, dann die Quell Adresse. Als nächstes kommt ein Typ Feld das anzeigt welches höher Levelige Protokoll verwendet wird(z.B. IP). Dann kommt die Payload(die Daten) und zum Schluss die CRC-Checksumme.

### Topology
Netzwerke auf der Link Layer sind entweder auf einem Bus(alle verwenden den selben Link -> Eine Kollisionsdomain) oder sie sind Switched(Unterschiedliche Kollisionsdomains)

### Switches

Ein Switch ist ein Link Layer Device, er uebernimmt eine Aktive Rolle im Netzwerk indem er Frames speichert und weiterleitet, empfangene Frames werden nur an die Ziel Links gesendet und das mit der Hilfe von CSMA/CD. Damit sind sie für Hosts "durchsichtig". Außerdem sind sie "selbst-lernend" und "Plug-and-Play", sie müssen also nicht konfiguriert werden.

Jeder Switch hat eine "Switch Table", in dieser steht die MAC Adresse des Hosts und auf welchem Link er zu erreichen ist.
Wen ein Switch einen Frame erhaehlt merkt er sich auf welchem Interface er diesen Host erreicht. Sollte er nicht wissen auf welchem Interface ein Host zu erreichen ist wird das Paket an alle Links außer dem Link gesendet von dem es kommt.

### WLAN

#### Vorteile

- Sehr flexibel mit der Empfangsreichweite
- Es können große Flächen abgedeckt werden da Radiowellen durch Wände gehen
- Keine Kabel :D

#### Nachteile

- Geringere Bandbreite
- Viele unterschiedliche Protokolle
- Unterschiede zwischen Ländern, wegen belegten Frequenzbändern


#### Funktionen und Layer

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

#### MAC Layer

Die Mac Layer besteht aus einem Asynchronen Daten Service der Pakete auf einer "best-effort" Basis austauscht, er muss Broad und Multicast unterstützen und wird durch DCF(Distriubuted Coordination Function) implementiert. Außerdem muss er DCF [CSMA/CA](Random%20Access.md#CSMA%20with%20Collision%20Avioadance%20(CSMA/CA%20802.11))unterstützen oder optional DCF CSMA/CA mit [RTS/CTS](Random%20Access.md#^f3976f).

Ausserdem kann ein "time-bounded service" implementiert sein, dieser verteilt Pakete auf einer "master-slave" Basis und wirt durch PCF(Point Coordination Function) implementiert.


##### Prioritäten
Prioritäten werden durch unterschiedliche Zwischen Frame Spaces definiert, die Prioritäten sind nicht garantiert.

- SIFS(Short Inter Frame Spacing)
	- Höchste Priorität, reserviert für ACK, CTS und Polling Responses
- PIFS(PCF Inter Frame Spacing)
	- Mittlere Priorität für Zeitgebundene Services mit PCF
- DIFS(DCF Inter Frame Spacing)
	- Geringste Priorität, für Asynchrone Daten Services

![prio](prio.png)


#### DCF CSMA/CA

Wenn eine Station zum Senden bereit ist wird das Medium abgetastet. Sollte das Medium für die Zeit eines IFS frei sein kann die Station senden.

Sollte das Medium nicht frei sein muss der Sender für eine freies IFS warten plus eine zufällige back-off Zeit, sollte eine andere Station während der Back-off Zeit senden wird der back-off Timer gestoppt.

Beim Senden von Unicast Paketen passiert folgendess:

1. Die Sation wartet fuer DIFS bevor sie sendet
2. Der Empfänger bestätigt nachdem er für SIFS gewartet hat wenn das Paket korrekt empfangen wurde

![retrans](retrans.png)



#### DCF CSMA/CA mit RTS/CTS

Beim Senden von Unicast Paketen:

1. Warte auf DIFS -> Die Station kann RTS mit NAV senden
2. Bestätigung durch CTS nach SIFS
3. Der Sender kann jetzt seine Daten senden, er bekommt ACK zurück


> Network Allocation Vector(NAV)
> Parameter der die Zeit bestimmt wie lange das Datenpaket das Medium braucht


![dcfcsmarts](dcfcsmarts.png)


#### Point Coordination Function(PCF)

Es handelt sich um einen Mechanismus, der in drahtlosen lokalen Netzwerken (WLANs) in Zusammenarbeit mit der "Distributed Coordination Function" (DCF) gemäß dem IEEE 802.11-Standard eingesetzt wird.

Im PCF-Modus fungiert ein Zugriffspunkt im WLAN-Netzwerk als Punkt-Koordinator. Der Punkt-Koordinator plant und verwaltet den Zugriff auf das drahtlose Medium für alle Stationen (Client-Geräte) innerhalb seines Abdeckungsbereichs. Dadurch können zeitkritische Datenverkehr, wie Sprache oder Video, priorisiert und effizienter bedient werden.

Der PCF-Modus wechselt sich mit dem DCF-Modus ab. Während der konfliktfreien PCF-Periode fragt der Punkt-Koordinator die Stationen (Client-Geräte) ab, um Daten zu senden und kontrolliert den Zugriff auf das Medium. Nach der PCF-Periode wechselt das Netzwerk wieder in den DCF-Modus, in dem die Stationen um den Zugriff auf das Medium mit dem CSMA/CA (Carrier Sense Multiple Access with Collision Avoidance) Protokoll konkurrieren.

## Network Layer

Die Netzwerkschicht ermöglicht den Transport von Segmenten vom Sender zum empfangenden Host zwischen verschiedenen Netzwerken. Der Sender kapselt dabei Segmente in __Datagramme__ und übergibt diese der Link Layer. Router prüfen die Header-Felder aller IP-Datagramme die durch sie hindurchgehen und leiten die Datagramme von den Eingangs zu den Ausgangsports weiter, um sie entlang des End-zu-End Pfads zu übertragen.

### Forwarding
Das Bewegen von Paketen von einem Eingangslink eines Routers zum entsprechenden Ausgangslink des Routers.

### Routing
Die Bestimmung der Route, die Pakete von der Quelle zum Ziel nehmen sollen

### Datagrammnetzwerk
Ein Datagrammnetzwerk bietet einen verbindungslosen Dienst auf Netzwerk Schicht Ebene. Die Pakete werden unter der Verwendung der Ziel-Host-Adresse weitergeleitet und Pakete zwischen der selben Quelle und Ziel können unterschiedliche Pfade nehmen.

#### IP
In Datagrammnetzwerken wird zur Adressierung die IP verwendet, eine IPv4 besteht aus einem 32-Bit identifier der zu einem bestimmten Interface gehört. Eine IP Adresse besteht aus einem Subnet und einem Host Teil. Geräte die sich im selben Netz befinden und sich so ohne einen Router erreichen können besitzen die selben Subnetz Bits und befinden sich in einer Broadcast Domain.

##### Classless InterDomain Routing(CIDR)
Die Subnetz Bits sind ein Teil der IP von beliebiger länge und werden folgendermaßen angezeigt: $a.b.c.d/x$ wobei $x$ die Anzahl an Bits ist die das Subnetz identifizieren.


##### Longest Prefix Matching
Wenn ein Router in seine Forwading Table für eine bestimmte Adresse schaut, benutzt er das Längste Adress Prefix das die Adresse beinhaelt.

---
Ein IP-Datagramm besteht aus folgenden Feldern:

1. Version: Gibt die Version des IP-Protokolls an (normalerweise IPv4 oder IPv6).
    
2. Header Length (HLEN): Gibt die Länge des IP-Header in 32-Bit-Wörtern an. Dieses Feld bestimmt die Länge des Header-Bereichs und ist wichtig, um die Nutzdaten (Payload) zu lokalisieren.
    
3. Type of Service (TOS): Dient zur Kennzeichnung des Diensttyps oder der Priorität des Pakets, um es entsprechend zu behandeln.
    
4. Total Length: Gibt die Gesamtlänge des IP-Datagramms in Bytes an, einschließlich Header und Nutzdaten.
    
5. Identification: Eine eindeutige Identifikationsnummer, die zur Fragmentierung und Reassemblierung von Paketen verwendet wird.
    
6. Flags: Steuert die Fragmentierung und Reassemblierung des Pakets. Das Feld enthält Informationen über das Fragmentierungsverhalten.
    
7. Fragment Offset: Zeigt die Position des aktuellen Fragments im ursprünglichen unfragmentierten IP-Datagramm an.
    
8. Time to Live (TTL): Legt eine Obergrenze für die Anzahl der Router fest, die das Paket durchlaufen darf, bevor es verworfen wird, um Endlosschleifen zu vermeiden.
    
9. Protocol: Gibt an, welches Protokoll in der Nutzdaten (z. B. TCP, UDP, ICMP) verwendet wird.
    
10. Header Checksum: Eine Prüfsumme, die zur Überprüfung der Integrität des IP-Headers verwendet wird.
    
11. Source IP Address: Die IP-Adresse des Absenders des Pakets.
    
12. Destination IP Address: Die IP-Adresse des Empfängers des Pakets.
    
13. Options: Ein optionales Feld, das zusätzliche Informationen oder Parameter enthalten kann, aber in der Regel selten verwendet wird.
    
14. Payload (Data): Die Nutzdaten des Pakets, die von den höheren Schichten (z. B. Transport- oder Anwendungsschicht) gesendet werden.


Da Netzwerk Links eine Maximum Transmission Unit(MTU), also der groesst moegliche Link Layer Level Frame, haben, werden grosse IP Datagramme im Netzwerk Fragmentiert und an der Zieladresse wieder zusammengesetzt, dazu werden IP-Header bits verwendet um die einzelnen Fragmente zu identifizieren.


Ein Host bekommt eine IP adresse entweder indem sie ihm vom System-Admin zugewiesen wird oder durch DHCP Dynamic Host Configuration Protocol. Bei DHCP wird die IP Adresse von einem Server dynamisch Zugewiesen, es ist kein Konfiguration notwendig.
##### Dynamic Host Configuration Protocol

Bei DHCP erhält der Host dynamisch eine IP von einem Netzwerk Server wenn der Host dem Netzwerk "joined". Dadurch kann eine Adresse neu genutzt werden sollte der Nutzer das Netzwerk verlassen.


Der Host Broadcasted eine DHCP discover msg
Der DHCP Server antwortet mit einer DHCP offer msg
Der Host fragt nach einer IP Adresse mit einer DHCP request msg
Der DHCP Server antwortet mit der Adresse und einer DHCP ack msg


##### Adress Resolution Protocol
Um die Zuordnung von IP-MAC Adresse zu ermöglichen gibt es das sogenannte ARP Protokoll:

$A$ fragt "who has IP $B$", tell IP $A$ with MAC $A$. Wird an die Broadcast Adresse gesendet.
$B$ antwortet "IP $B$ is at MAC $B$"
MAC $B$, IP $B$ wird in die ARP Tabelle von $A$ geschrieben.
Alle speichern in ihre ARP Tabelle IP $A$, MAC $A$


##### Internet Control Message Protocol

ICMP wird von Hosts und Routern verwendet um auf Netzwerk Ebene zu Kommunizieren, zb. um Fehler zu melden oder Pings. Es ist quasi eine Netzwerkschicht "ueber" IP, da ICMP Nachrichten in IP Datagrammen Transportiert werden. ICMP Nachrichten bestehen aus einem Typ, einem Code und die ersten 8 bytes des IP Datagramms das Fehler verursacht.

###### Traceroute
Die Quelle sendet eine Menge von UDP Segmenten zum Empfänger. Die erste Menge hat eine Time to Live(TTL) von 1, die zweite 2 usw. Die n-te Menge von Datagrammen erreicht den n-ten Router, der Router schickt eine ICMP Nachricht(Typ 11, code 0, TTL expired). Die Nachricht kann den Routernamen und die IP-Adresse beinhalten, an der Quelle angekommen wird die Round Trip Time(RTT) aufgeschrieben. Irgendwann erreicht ein UPD Segment den Ziel Host, dieser schickt ICMP port unreachable(Typ 3, Code 3) zurück und die Quelle stopt.


#### IPv6

Da heutzutage die 32-Bit IP-v4 Adressen nicht mehr ausreichen gibt es IPv6, weitere Motivationen sind das verschnellen von Verarbeitung und Forwarding durch einen festen Header der länge 40bytes.

Null Segmente können in einer IPv6 Adresse durch ein "::" dargestellt werden und führende nullen können weggelassen werden.

Ein IPv6 Datagram sieht so aus:
1. Version: Gibt die Version des IP-Protokolls an, in diesem Fall immer "6" für IPv6.
    
2. Traffic Class: Dient zur Kennzeichnung des Datenverkehrs, um Pakete mit unterschiedlichen Prioritäten oder Dienstqualitäten zu unterscheiden.
    
3. Flow Label: Ein Feld, das verwendet wird, um den Datenverkehr zu identifizieren, der einer bestimmten Datenstromklasse (Flow) angehört. Es ermöglicht die Behandlung von Datenströmen mit speziellen Anforderungen, z. B. für multimediale Echtzeitdienste.
    
4. Payload Length: Gibt die Gesamtlänge des Nutzdatenbereichs in Bytes an.
    
5. Next Header: Gibt den Typ des nächsten Headers im Paket an, z. B. TCP, UDP, ICMPv6 usw.
    
6. Hop Limit: Ähnlich zum TTL in IPv4, legt das Hop Limit die maximale Anzahl von Routern fest, die das Paket durchlaufen darf, bevor es verworfen wird, um Endlosschleifen zu vermeiden.
    
7. Source Address: Die IPv6-Adresse des Absenders des Pakets.
    
8. Destination Address: Die IPv6-Adresse des Empfängers des Pakets.
    
9. Optionale Erweiterungsheader: IPv6 unterstützt mehrere optionale Erweiterungsheader, die zusätzliche Informationen oder Funktionen enthalten können. Einige dieser Header sind Hop-by-Hop Options Header, Routing Header, Fragment Header und Authentication Header.
    
10. Nutzdaten (Data): Die eigentlichen Daten, die von der höheren Schicht (z. B. der Transport- oder Anwendungsschicht) gesendet werden.

##### Unicast
Schicke die Nachricht an ein bestimmtes Interface

##### Multicast
Schicke die Nachricht an mehrere Interfaces

##### Anycast
Schicke die Nachricht an das "nächste" Interface das durch die Adresse identifiziert wid.

##### Neighbour Discovery Protocol(NDP)
Anstelle von ARP verwendet IPv6 das NDP. Dabei werden ICMPv6 Nachrichten Mithilfe von Multicast augestauscht, in ICMPv6 gibt es fuenf neue Nachrichten:

- Neighbor Solicitation 
- Neighbor Advertisement
- Router Solicitation 
- Router Advertisement 
- Redirect

##### Stateless Address Configuration(SLAC)
1. Der Host gibt sich selbst eine Link-Local Adresse
2. Er schickt eine Neighbor Solicitation Nachricht mit seiner Link-Local Adresse
3. Falls er eine Neighbor Advertisement Nachricht erhält gibt er sich eine neue Adresse und wiederholt Schritt 2. Falls er keine Antwort erhält geht der Host davon aus das seine Adresse valid ist.
4. Der Host sendet eine Router Solicitation Nachricht mit seiner Link Local Adresse um eine globale IPv6 Adresse zu erhalten(Optional)
5. Wiederhole Schritt 2 und 3(DAD) für die globale IPv6

### Virtual Circuits(VC)
Der Quelle-Ziel Pfad verhält sich ähnlich wie eine Telefonverbindung, sowohl im Bezug auf Leistungsfähigkeit als auch die Netzwerkaktionen entland des Quelle-Ziel-Pfads.

Bevor Daten gesendet werden, muss es einen Verbindungs auf und abbau, geben, jedes gesendete Paket trägt eine VC-Kennung anstatt der Ziel-Host Adresse. Jeder Router auf dem Pfad verwaltet den "Zustand" für jede durchlaufende Verbindung. Link und Routerressourcen können für VC zugewiesen werden.
Ein VC besteht aus
1. Einem Pfad zwischen Quelle und Ziel
2. VC Nummern für jeden Link auf dem Pfad
3. Einträge in die Forwarding Tables für jeden Router auf dem Pfad

### Routing Algorithm

Man unterscheidet Routing Algorithmen auf 2 Achsen. Die eine Achse geht von Global - Decenetralized, die andere von Statisch nach Dynamisch.

Global bedeutet das alle Router die gesamte Netzwerk Topology und Link kosten haben, die Algorithmen in dieser Kategorie nennt man Link state Algorithms

Bei Decentraliced gibt es einen Iterativen Prozess bei dem Informationen mit dem Nachbarn ausgetauscht werden, Router wissen zuerst nur die Link Kosten zu ihren Nachbarn. Daraus ergeben sich Distance Vector Algorithmen.

Der Unterschied zwischen Dynamic und Static liegt darin wie schnell sich Routen und ihre kosten aendern.

### Dijkstra's Link State Algorithm

Der Algorithmus berechnet die Pfade mit den geringsten Kosten von einem Knoten zu allen anderen Knoten und erstellt eine Routingtable für diese Kosten. Der Prozess ist iterativ: Nach $k$ Iterationen kennt man den Pfad mit den geringsten Kosten zu $k$ Zielen

$c(x, y)$ ist ein Direkter Link von $x$ nach $y$.
$c(x, y) = \infty$ sollten sie keine Direkten Nachbarn sein.

$D(v)$ Aktuelle Schätzung der Kosten des Pfades mit den geringsten Kosten von der quelle zur Zieldestination $v$

$p(v)$ Vorgängerknoten entlang des Pfades von der Quelle zu $v$.

$N'$ Die Menge von Knoten, deren Pfad mit den geringsten Kosten definitiv bekannt ist.

```python
N' = {u}
forall nodes v
	if v adjacent to u
		 then D(v) = c_u,v
    else D(v) = infty

Loop
	find w not in N' such that D(w) is a minimum
	add w to N'
	update D(v) 
		for all v adjacent to w and not in N':
			D(v) = min(D(v), D(w) + c_wv)
	/*
	New least path cost to v is either old least
	path to v or known least cost path to w
	direct cost from w to v
	*/
untill all nodes in N'
```

In jeder der $n$ Iterationen müssen wir alle Knoten $w$ die nicht in $N$ sind betrachten, wir erhalte $n(n+1)/2$  Vergleiche daher läuft der Algorithmus in $O(n^{2})$, es ist jedoch möglich den Algorithmus in $O(n\log n)$ zu implementieren.

Wir benötigen auch $O(n^{2})$ Nachrichten da jeder Router seinen Verbindungsstatus-Informationen an die anderen $n$ Router senden muss.


### Distance Vector Algorithm

Der Distance Vector Algorithmus basiert auf der Bellman-Ford(BF) Gleichung:

Sei $D_{x}(y)$ die Kosten des Pfades mit den geringsten Kosten von $x$ nach $y$.
Dann gilt:
$D_{x}(y) = \min_{v}\lbrace c_{x,v} + D_{v}(y)\rbrace$ 

Als Beispiel:
Nehmen wir an das die Nachbarn von $u$, $x, v, w$ und das Ziel $z$:
$D_{v}(z) = 5; D_{w}(z) = 3; D_{x}(z) = 3$ 
dann besagt die Bellman-Ford Gleichung
$D_{u}(z) = \min\lbrace c_{u,v} + D_{v}(z), c_{u,x} + D_{x}(z), c_{u,w} + D_{w}(z)\rbrace = \min\lbrace 2 + 5, 1+ 3, 5 + 3\rbrace = 4$
Der Knoten mit dem kleinsten $(x)$ ist dann der nächste Hop auf dem Pfad mit den Geringsten Kosten nach $z$.

---

Die Schlüsselidee für den Distance Vector Algorithmus ist jetzt das von Zeit zu Zein jeder Knoten seinen eigenen Distance Vector an die Nachbarn schickt.

Wenn $x$ einen neuen DV irgendeines Nachbarn erhält errechnet er seinen eigenen DV neu mithilfe der BF Gleichung. 

Unter echten Bedingungen Konvergiert $D_{x}(y)$ in die Richtung der echten geringsten Kosten $d_{x}(y)$.

Jeder Knoten tut also folgendes:

Warte auf eine aenderung der lokalen Kosten oder eine Nachricht des Nachbarn

Berechne den DV neu mithilfe des erhaltenen DV des Nachbarn. 

Sollte der DV zu irgendeinem Ziel sich verändert haben, schicke das an die Nachbarn

??? Poisoned Reverse

#### Good news travels fast
Sollten sich die Link kosten verringern:

$y$ Updated seinen DV und sendet ihn an die Nachbarn
$z$ erhaelt die Nachricht von $y$ und updated seine eigene Tabelle und berechnet die kosten nach $x$ neu und schickt diese an seine Nachbarn
$y$ erhält $z$'s Update und updated seine Tabelle, aber $y$'s kosten ändern sich nicht daher wird keine Nachricht versendet.

#### Bad news travels slow

Wenn die Link kosten sich erhöhen kann es zum count-to-infinity Probelm kommen:

$Y$ sieht, dass die direkte Verbindung zu $X$ einen neuen Kostenwert von $60$ hat, aber $Z$ hat mitgeteilt, dass es einen Pfad mit einem Kostenwert von $5$ gibt. Also berechnet $Y$: "Mein neuer Kostenwert für $X$ wird $6$ sein, über $Z$" und benachrichtigt Z über den neuen Kostenwert von $6$ für $X$.

$Z$ erfährt, dass der Pfad zu $X$ über $Y$ einen neuen Kostenwert von 6 hat, also berechnet $Z$: "Mein neuer Kostenwert für $X$ wird 7 sein, über $Y$" und benachrichtigt $Y$ über den neuen Kostenwert von 7 für $X$.

$Y$ erfährt, dass der Pfad zu $X$ über $Z$ einen neuen Kostenwert von $7$ hat, also berechnet $Y$: "Mein neuer Kostenwert für $X$ wird $8$ sein, über $Z$" und benachrichtigt $Z$ über den neuen Kostenwert von $8$ für $X$.

$Z$ erfährt, dass der Pfad zu $X$ über $Y$ einen neuen Kostenwert von $8$ hat, also berechnet $Z$: "Mein neuer Kostenwert für $X$ wird $9$ sein, über $Y$" und benachrichtigt $Y$ über den neuen Kostenwert von $9$ für $X$.

### Routing

Da es Billionen von Zielen gibt und nicht immer ideale Netzwerkbedingungen gelten ist es nicht möglich alle Ziele in unserer Routing Tabelle zu speichern und das austauschen von Tabellen würde Links zusätzlich belasten.
Deswegen werden Router in Autonome Systeme(AS) oder Domains Zusammengefasst.
#### Intra-AS
Intra-AS ist das Routing in der selben AS, dafuer müssen alle Router das selbe Intra-Domain Protokoll haben und nur Gateway Router haben eine Verbindung zu anderen Routern in anderen AS.

Intra-AS Routing Algorithmen sind:

Routing Information Protocol RIP
Enhanced Interior Gateway Routing Protocol EIGRP

Open Shortest Path First OSPF


##### OSPF
Klassisches Link-State-Verfahren 
- Jeder Router überschwemmt OSPF-Link-State-Anzeigen (direkt über IP statt TCP/UDP) an alle anderen Router im gesamten AS 
- Mehrere Link-Kosten-Metriken möglich: Bandbreite, Verzögerung 
- Jeder Router hat die volle Topologie und verwendet den Dijkstra-Algorithmus, um die Weiterleitungstabelle zu berechnen
- Sicherheit: Alle OSPF-Nachrichten sind authentifiziert (um böswillige Eingriffe zu verhindern)

#### Inter-AS 
Beschreibt das Routing zwischen AS, Gateways sind dafür zuständig inter-Domain Routing auszuführen. Damit das Funktioniert müssen alle Router im Intra-AS wissen über welchen Gateway Router welche Domains erreichbar sind.

Das am weitesten verwendete Inter-AS Protokoll ist das Border Gateway Protocol(BGP). Jedes Subnetz zeigt an "I am here, here is who I can reach, and how"

eBGP wird dafür genutzt um Erreichbarkeit Informationen von Benachbarten AS zu erhalten.

iBGP wird genutzt um Erreichbarkeitsinformationen im AS-Netz zu verteilen.

In einer BGP Sitzung werden BGP-Nachrichten über eine halbpermanente TCP-Verbindung ausgetauscht.

## Transport Layer

Die Transport Schicht dient dazu logische Verbindungen zwischen Prozessen auf verschiedenen Hosts aufzubauen. Der Sender teilt Anwendungsnachrichten in __Segmente__ auf und gibt diese an die Network Layer weiter, der Empfänger baut die Pakete wieder zusammen und gibt sie an die Application Layer weiter.

Es gibt zwei Protokolle auf der Transport Schicht, Transmission Control Protocol(TCP) und User Datagram Protocol.

### Transmission Control Protocol(TCP)
TCP bietet einen zuverlässigen in-order byte Stream, dass heisst es gibt keine Nachrichten grenzen. Die Verbindung ist ausserdem Full Duplex, beide Seiten koennen gleichzeitig die Maximum Segment size(MSS) senden. Zur bestaetigung werden "cumulative ACKs" verwendet. Da TCP gepipelined ist wird die Menge von Daten die gesendet wird von Congestion und Flow Control kontrolliert. Vor dem Senden von Daten wird ein Handshake gemacht.

#### Sequenz Nummern und ACKs
Die Sequenznummer entspricht der Byte-Stream Nummer des ersten Bytes in den Daten des Segments, als Antwort erwartet der Sender nun die Sequenznummer des nächsten bytes und ein Cumulatitives ACK

#### Timeouts
Timeout werte müssen länger als die Round Trip Time(RTT) sein, da die RTT sich ständig ändert und schwer zu schätzen ist gibt es die SampleRTT, diese ist die Zeit zwischen uebertragung und ACK. Ein besserer Ansatz ist der Exponential Weighted Moving Average(EWMA):

$$EstimatedRTT = (1-\alpha) \cdot EstimatedRTT + \alpha \cdot SampleRTT$$

dabei verringert sich der Einfluss von früheren Übertragungen Exponentiell schnell.
Das Timeout Intervall wird dann meistens so gewählt:

$$TimeoutInterval = EstimatedRTT + 4\cdot DevRTT$$

$$DevRTT = (1- \beta) \cdot DevRTT + \beta \cdot |SampleRTT - EstimatedRTT|$$

#### TCP Fast Retransmit

Sollte der Sender 3 zusätzliche ACKs für die selben Daten erhalten, sendet er die noch nicht durch ACK bestätigten Segmente erneut

#### Flow Control
Sollte die Network Layer schneller Daten senden als die Application Layer sie verarbeitet tritt Flow Control in Kraft. Der Empfänger setzt die Buffer Size bei der Socket Erstellung und der Freie Bufferplatz wird im `rwnd` Feld des TCP Header mitgesendet. Der Sender passt dann seine Rate an unACKed("in-flight") Daten an die Empfangenen `rwnd` an.
Dadurch wird garantiert das der Buffer nicht überläuft. 

#### Congestion Control
Wenn zu viele Quellen zu viele Daten zu schnell senden kann es passieren das das Netzwerk dies nicht mehr verarbeiten kann. Sollte die passieren kommt es zu langen Wartezeiten in den Warteschlangen der Router und Paket loss, sollten die Router Schlangen voll sein.

Bei End-zu-End Congestion Kontrolle achten die Sender auf Paket Loss und Paket Delay und passen ihre Sende rate dementsprechend an, die Sende rate wird durch den `cwnd` Teil des Headers angegeben. Wir senden `cwnd` Bytes und warten eine RTT für die ACK, dann senden wir mehr Bytes.

$$TCP\;rate = \frac{cwnd}{RTT} \left[\frac{Byte}{sec}\right]$$
der Sender beschränkt also die Übertragung:
$$LastByteSent - LastByteAcked \leq \min\lbrace cwnd, rcvwnd \rbrace$$
dabei wird $cwnd$ Dynamisch angepasst, indem auf das Netzwerk geachtet wird. Sollte der Sender also ein Timeout oder 3 ACKs erhalten veringert er `cwnd`. Dies wird durch 3 unterschiedliche Mechanismen angepasst:
- Additive Increase, Multiplicative Decrease(AIMD)
- Slow start
- Conservative after timeout events

Sollte das `CongWin` kleiner als der `Threshold` sein sind wir in der [TCP Slow Start](#TCP%20Slow%20Start) Phase in der wir exponentiell wachsen.

Sobald `CongWin` ueber dem `Threshold` ist wechseln wir in die congestion-avoidance(CA) indem unser `CongWin` nur noch linear waechst.

Erhalten wir ein triple duplicate ACK, wird der `Threshold` auf `CongWin/2` gesetzt und `CongWin` auf 1 MSS bei Taheo und auf `Threshold` bei Reno gesetzt.

Sollte ein Timeout auftreten setzen wir `Threshold` auf `CongWin/2` und `CongWin` wird auf 1 MSS gesetzt.

##### TCP CUBIC

Sei $W_{max}$ die sende Rate bei der der Loss entdeckt wurde, da sich der Congestion state wahrscheinlich nicht stark geändert hat gehen wir anfangs schneller nach $W_{max}$, aber sobald wir in die näher kommen nähern wir uns langsamer.

![cubic](cubic.png)

Sollten wir $W_{max}$ erreichen machen wir kleinere Schritte nahe an $W_{max}$ und immer grössere Schritte wenn wir weiter weg von $W_{max}$ sind.
#### Durchsatz
Ignorieren wir die Slow Start Phase sieht unser Durchsatz folgendermaßen aus:

Sei $W$ die Window groesse in Bytes an dem Punk wenn unser Loss auftritt, die Durchschnittliche Window groesse ist dann $\frac{3}{4}W$ und der Durchsatz $\frac{3}{4}W$ pro $RTT$

$$\text{avg TCP thruput} = \frac{3}{4} \frac{W}{RTT} \frac{bytes}{sec}$$

#### Connection Management
Vor dem Senden von Daten muss erst eine Verbindung zwischen Sender und Empfaenger aufgebaut werden, dabei werden TCP Variablen wie Sequenz Nummern, Buffer und Flow Control Info initialisisert, dazu wird ein "Three way Handshake" verwendet:

Der Client sendet ein TCP SYN Segment zum Server und spezifiziert die start Sequenznummer.

Der Server Empfängt SYN und antwortet mit einem SYN+ACK Segment. Der Server erstellt einen Buffer und Spezifiert die Sequenznummer des Servers. 

Der Client erhält SYN+ACK und Antwortet mit einem ACK Segment das Daten enthalten kann.

Eine Verbindung wird durch folgende Sequenz geschlossen.

Der Client sendet ein TCP FIN Segment.

Der Server erhaelt das FIN Segment und Antwortet mit ACK, daraufhin schließt er die Verbindung und Antwortet mit FIN

Der Client erhält FIN und Antwortet mit ACK, der client geht in den "timed wait" State und Antwortet mit ACK auf alle FINs

Der Server erhaelt ein ACK.
Die Connection ist geschlossen.
#### Fairness
Unter Idealen Bedingungen ist TCP Fair, aber nur wenn alle beteiligten die selbe RTT haben und jeder nur eine bestimmte Anzahl an Sockets hat.
### User Datagram Protocol
Bei UDP koennen Segmente verloren gehen ohne das der Sender es mitbekommt, es gibt ausserdem keine Handshakes und jedes UDP wird unabhängig von den anderen verarbeitet.
UDP verwendet eine Checksum um die Integrität der Daten zu ueberpruefen. Dabei wird das Segment mit dem 1er Komplement aufaddiert und angehängt, der Empfänger Rechnet dies dann nach.

### Multiplexing/Demultiplexing
Der Sender verarbeitet die Daten von mehreren Sockets und fügt den Transport Header hinzu der später zum Demultiplexing verwendet wird.

Der Empfänger benutzt den Transport Header um Segmente an die richtigen Sockets weiterzuleiten.

Der Host erhält ein IP Datagram, jedes Datagram hat eine Quell und eine Ziel Adresse. Jedes Datagram hat außerdem ein Transport-Layer Segment,jedes dieser Segemente hat eine Ziel und eine Quell Port Nummer. Der Host benutzt die IP Adresse und die Port Nummer um ein Segment zum Richtigen Socket zu senden.

UDP benötigt also nur die Ziel Adresse und der Ziel Port.

Im Gegensatz dazu werden TCP Sockets durch ein 4er Tupel identifiziert, die Quell IP, der Quell Port, die Ziel IP und der Ziel Port. Der Empfänger benutzt alle 4 dieser Werte um den Ziel Socket zu bestimmen. Da wir alle 4 dieser Werte benötigen muss der Server auf eingehende Verbindungen warten, der Server verwendet dafür einen Listening Socket, jede Verbindung die dieser erhält wird auf einen neuen Socket gelegt sodass der Listening Socket niemals Daten verschickt/empfängt.

### Transport Layer Security(TLS)
TLS ist ein weit verbreitetes Sicherheitsprotokoll über der [Transport Layer](Transport%20Layer.md).

Die drei Ziele von TLS sind:
__Confidentially__ durch symmetrische Verschlüsselung
__Authentication__ durch public key cryptography
__Integrity__ durch kryptographisches Hashing

## Confidentially

Bob verschlüsselt seine Nachricht mit Alice Public key, Alice kann die Nachricht mit ihrem Private Key wieder entschlüsseln.

![conf](conf.png)
## Integrity

Alice unterschreibt ihre Nachricht indem sie sie mit einem Private key verschlüsselt. Bob kann mit Alice Public Key entschlüsseln und dadruch sichergehen das die nachricht valide ist(Genau umgekehrt zu Confidentially).
Da es relativ Aufwendig ist lange Nachrichten zu verschluesseln wird ein Hash angewand um einen "Fingerabdruck" von fester länge zu generieren.

![int](Kommunkikationssysteme/attachments/int.png)


## Authentication

Sogenannte Certification Authorities(CA) ordnen Public Keys zu gewissen Entitys E zu.

Diese Entity registriert ihren Public Key und identifiziert sich mit der CA. Die CA erstellt einen Certificat das die Identität von E mit E's public key identifiziert.

![auth](auth.png)

## Application Layer
### HTTP
Eine HTTP Verbindung läuft folgendermaßen ab:
Der Client initiiert eine [TCP](Transmission%20Controll%20Protocol(TCP).md) Verbindung zum Server auf Port 80, der Server akzeptiert die Verbindung und die HTTP Nachrichten werden ausgetauscht, danach wird die Verbindung wieder geschlossen.

#### Non-Persistent HTTP

Bei Non-Persistent HTTP wird eine TCP Verbindung geöffnet, ein Objekt wird gesendet und die Verbindung wird wieder geschlossen.
Sollten wir mehrere Sachen Downloaden müssen, benötigen wir mehrere Verbindungen.

Wir benötigen eine RTT um die TCP Verbindung aufzubauen, eine RTT für die HTTP Request und die ersten Bytes der Antwort, plus die Zeit die es benötigt die Datei zu übertragen.

$$n \cdot (2RTT + FTT_{n})$$
wobei $n$ die Anzahl an Objekten ist die gesendet werden müssen
#### Persistent HTTP

Eine TCP Verbindung wird geöffnet und es werden mehrere Objekte über eine einzelne TCP Verbindung gesendet. Danach wird die Verbindung wieder geschlossen.

Wir benötigen eine RTT um die TCP Verbindung aufzubauen, eine RTT für die HTTP Request und die ersten Bytes der Antwort, plus die Zeit die es benötigt die Dateien zu übertragen.
(ohne Pipelining)
$$RTT + n\cdot(RTT + FTT_{n})$$
wobei $n$ die Anzahl an Objekten ist die gesendet werden müssen.
#### Pipelining
Wenn kein Pipelining implementiert ist, wird eine neue Request immer nur dann gestartet wenn wir die vorherige Antwort Empfangen haben, dadurch benötigen wir eine RTT für jedes Objekt.

Verwenden wir Pipelining müssen wir nicht auf vorherige HTTP Requests warten, dadurch ist es möglich alle Objekte in einer RTT zu erhalten

$$RTT_{tcp} + RTT_{req} + FTT_{0}+ RTT_{add} + \max\lbrace FTT_{1}, FTT_{2}, ...\rbrace$$

### HTTPS
HTTPS steht für HTTP Secure, das heißt die Datenübertragung ist verschlüsselt. 

Wir müssen allerdings längere Ladezeiten durch Zertifikate in kauf nehmen