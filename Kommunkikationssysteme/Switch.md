
Ein Switch ist ein "Link Layer Device" er übernimmt eine Aktive Rolle indem er Frames speichert und weiterleitet, empfangene Frames werden nur an die Ziel Links geschickt und das mit der Hilfe von [CSMA/CD](Random%20Access.md#CSMA%20with%20Collision%20Detection(CSMA/CD)). Damit sind sie für Hosts "durchsichtig"(Hosts wissen nichts vom Switch). Außerdem sind sie "selbst-lernend" und "Plug-and-Play", sie müssen also nicht konfiguriert werden.

Jeder Switch hat eine "Switch Table", in dieser steht die MAC Adresse des Hosts und auf welchem Link er zu erreichen ist.

Wenn ein Switch einen Frame erhält merkt er sich auf welchem Interface er diesen Host erreicht.

Ein Switch tut also folgendes:

Wenn ein Switch einen Frame erhaelt:

1. Speicher das Sender MAC/Link paar in die Switch Tabelle
2. Suche in der Switch Tabelle nach der Zieladdresse
Falls die Zieladresse gefunden wurde
	- Falls die Zieladresse auf dem Link der Sendeadresse ist, droppe den Frame
	- Sonst sende den Frame auf dem Interface des Eintrags
Sonst flood(Schicke den Frame auf alle Interfaces außer dem Ankunfts Interface)
