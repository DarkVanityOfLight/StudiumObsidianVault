
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
Bei Ethernet steht die Quell und Ziel MAC(Medium Access Controll) Adresse im header und im Trailer findet man eine Frame Check Sequenz(FCS) durch z.b. CRC.

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

##### CSMA
###### Collision Detection
###### Collision Avoidance