
Bisheriges Routing mit [Distance Vector Alogrithm](Distance%20Vector%20Alogrithm.md) und [Dijkstra's Link State Routing Algorithm](Dijkstra's%20Link%20State%20Routing%20Algorithm.md) war idealisiert, alle Router waren identisch und Netzwerke waren "flach", dies entspricht nicht der Wirklichkeit.

Außerdem gibt es Billionen von Zielen, wir können nicht alle in unserer Routing Tabelle speichern, und das austauschen von Tabellen würde die Links zusätzlich belasten.

Deswegen werden Router in Autonome Systeme(AS) oder Domains zusammengefasst.
## Intra-AS

Intra-AS ist das Routing in der selben AS, dafuer müssen alle Router das selbe Intra-Domain Protokoll haben und nur Gateway Router haben eine Verbindung zu anderen Routern in anderen AS.

Intra-AS Routing Algorithmen sind:

Routing Information Protocol RIP
Enhanced Interior Gateway Routing Protocol EIGRP

Open Shortest Path First OSPF


## Inter-AS
Beschreibt das routing zwischen AS, Gateways sind dafür zuständig inter-Domain Routing auszuführen. Damit das Funktioniert müssen alle Router im Intra-AS wissen über welchen Gateway Router welche Domains erreichbar sind.

Das am weitesten verwendete Inter-AS Protokoll ist das Border Gateway Protocol(BGP). Jedes Subnetz zeigt an "I am here, here is who I can reach, and how"

eBGP wird dafür genutzt um Erreichbarkeit Informationen von Benachbarten AS zu erhalten.

iBGP wird genutzt um Erreichbarkeitsinformationen im AS-Netz zu verteilen.

In einer BGP Sitzung werden BGP-Nachrichten ueber eine halbpermanente TCP-Verbindung ausgetauscht.
