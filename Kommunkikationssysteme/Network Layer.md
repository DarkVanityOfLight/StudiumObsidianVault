

Die Netzwerkschicht ermöglicht den Transport von Segmenten vom Sender zum empfangenden Host. 
Der Sender kapselt dabei Segmente in __Datagramme__ und übergibt diese der [Link Layer](Link%20Layer.md). Der Empfänger liefert die Segmente an das Transportprotokoll der [Network Layer](Network%20Layer.md). Router prüfen die Header-Felder aller IP-Datagramme die durch sie hindurchgehen, und leiten die Datagramme von den Eingangs zu den Ausgangsports weiter, um sie entlang des End-zu-End-Pfads zu übertragen.

## Funktionen

__Forwarding__: Das Bewegen von Paketen von einem Eingangslink eines Routers zum entsprechenden Ausgangslink des Routers.

__Routing__: Bestimmung der Route, die Pakete von der Quelle zum Ziel nehmen sollen. Dafür werden Routing-Algorithmen verwendet

## Connection und Connection-Less Services

Ein Datagrammnetzwerk bietet einen verbindungslosen Dienst auf Network Layer ebene, im Gegensatz dazu bieten VC(Virtual Curcuit) Netzwerke einen verbindungsorientierten Dienst auf Network Layer Ebene.
Diese sind Analog zu den [[Transport Layer]] Diensten jedoch sind es Host-zu-Host Dienste und das Netzwerk bietet entweder das eine oder das andere.


## Virtual Circuits(VC)

Der Quelle-Ziel Pfad verhält sich ähnlich wie eine Telefonverbindung, sowohl im Bezug auf die Leistungsfähigkeit als auch die Netzwerkaktionen entlang des Quelle-Ziel-Pfads

Bevor Daten gesendet werden können muss es einen Verbindungs auf und abbau geben, jedes gesendete Paket trägt eine VC-Kennung anstatt der Ziel-Host Adresse. Jeder Router auf dem Pfad verwaltet den "Zustand" für jede durchlaufende Verbindung. Link und Routerressourcen können für VC zugewiesen werden.


Ein VC besteht aus
1. Einem Pfad zwischen Quelle und Ziel
2. VC Nummern für jeden Link auf dem Pfad
3. Einträge in die Forwarding Tables für jeden Router auf dem Pfad

Pakete gehören nicht zu Zieladressen sondern VC carries und VC Nummern, die VC Nummer kann sich an jedem Link ändern und neue VC Nummern bekommt man aus der Forwarding Table.

Singaling Protokolle werden verwendet um VC zu erstellen, sie zu erhalten und sie wieder zu zerstören, heutzutage werden sie eher nicht benutzt.

## Datagramm Netzwerke

Bei Datagramm Netzwerken gibt es keinen Verbindungsaufbau auf der [Network Layer](Network%20Layer.md). Der Router besitzt keinen Zustand über die End-zu-End Verbindungen und hat kein Konzept von netzwerkspezifischen Verbindung. Pakete werden unter der Verwendung der Ziel-Host-Adresse weitergeleitet und Pakete zwischen der selben Quelle und Ziel können unterschiedliche Pfade nehmen.

