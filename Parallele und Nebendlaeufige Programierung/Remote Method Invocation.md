
__Remote Method Invocation__ ist die Objekt-orientierte Variante von [Remote Procedure Calls](Remote%20Procedure%20Calls.md) und existiert nur in Java, dabei geht es um die uebertragung von Java Objekten zwischen Maschinen.

## RMI Registry

Ein Java Remote Object Registry ist ein Namensdienst, der von RMI-Servern und RMI-Clients genutzt wird.
- RMI Server koennen entfernte Objekte zur Laufzeit an Namen binden
- RMI Clients, die auf berechtigten Knoten ausgefuehrt werden, koennen entfernte Objekte zur Laufzeit nachschlagen(lookup)
