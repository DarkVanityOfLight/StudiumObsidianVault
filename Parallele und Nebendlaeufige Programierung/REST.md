
Representational State Transfer ist eine Architektur für verteilte hypermedia Systeme und ein Prinzip zur Softwareentwicklung solcher Systeme.



## Stateless

Die Anfragen eines Clients muss alle Informationen enthalten, die notwendig sind, sodass der Server die Anfrage bearbeiten kann. Dadurch skaliert das System besser auf viele Clients, hat erhöhte Fehlertoleranz und es ist einfacher zu debuggen, allerdings müssen Daten eventuell wiederholt übertragen werden.


## Caching

Antworten können als `cacheable` oder `non-cacheable` deklariert werden, die clients speichern dann Antworten die cacheable sind, so können diese später bei äquivalenten Anfragen genutzt werden. Dies steigert die Effizienz, allerdings muss die Zeitspanne die eine Antwort gecached wird effizient gewählt sein.

## Einheitliches Interface

Verschiedene Anwendungen und Ressourcen sollen über dasselbe Interface verfügbar sein, es sollte gelten:
- Es werden einheitliche Objektrepräsentationen in der Kommunikation genutzt
- Die interne Repräsentation der Ressourcen des Servers ist nicht notwendigerweise die Repräsentation, die gesendet wird.
- Clients haben genug Information durch eine Repräsentation, um die entsprechende Ressource zu manipulieren
- Nachrichten sollen die Informationen enthalten, wie sie zu verarbeiten sind
- Clients entdecken weitere Informationen über Hyperlinks in Antworten.
## Mehrschichtige Systeme

Die Systeme sollen mehrere Schichten haben, um sie übersichtlicher zu gestalten.

Der Client erhält meist nur eine Schnittstelle und kennt die Organisation in Schichten nicht.