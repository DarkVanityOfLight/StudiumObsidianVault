Das IP-Datagramm-Format ist die Struktur, die für die Verpackung von IP-Paketen verwendet wird, um sie im Internet zu übertragen. Es ist Teil der Netzwerkschicht des TCP/IP-Protokollstapels und ermöglicht die Zustellung von Datenpaketen von einem Quellgerät zu einem Zielgerät.

Das IP-Datagramm besteht aus folgenden Feldern:

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


Da Netzwerk Links eine Maximum Transmission Unit(MTU), also der groesst mögliche [Link Layer](Link%20Layer.md) Level Frame, haben, werden grosse IP Datagramme im Netzwerk Fragmentiert. Aus einem Datagramm werden also mehrere, diese werden an der Zieladresse wieder zusammengesetzt, dazu werden IP-Header bits verwendet um die einzelnen Fragmente zu identifizieren.


## IP/V4

Eine IP Adresse ist ein 32-Bitstring der jedem Host oder Router Interface zugewiesen wird. Das Interface ist die Verbindung zwischen dem Host/Router und dem Physischem Link.

IP Adressen haben einen Subnetzteil, Geräte im selben Netzwerk haben die selben höheren Bits, der Host Part sind dann die übrigen kleineren Bits. Ein Subnetz sind Geräte die zusammen an einem Physikalischen Link sitzen und sich so ohne einen Router erreichen können. Alle Hosts in einem Subnetz sind in einer Broadcast Domain.


## Classless InterDomain Routing(CIDR)

Das Subnetz ist durch einen Teil der Adresse von beliebiger länge gewählt das Adress Format ist: a.b.c.d/x wobei x die Anzahl an Bits ist die das Subnetz identifizieren.

---

Ein Host bekommt eine IP adresse entweder indem sie ihm vom System-Admin zugewiesen wird oder durch DHCP Dynamic Host Configuration Protocol. Bei DHCP wird die IP Adresse von einem Server dynamisch Zugewiesen, es ist kein Konfiguration notwendig.



## IP/V6

Heutzutage reicht der 32-bit IPv4 Space nicht mehr aus, deswegen gibt es IPv6, weitere Motivationen sind das verschnellen von Verarbeitung und Forwarding durch einen festen Header der länge 40bytes.

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



### Adress Architektur

##### Unciast

Schicke die Nachricht an ein bestimmtes Interface
##### Multicast

Schicke die Nachricht an mehrere Interfaces

##### Anycast

Schicke die Nachricht an das "nächste" Interface das durch die Adresse identifiziert wid.