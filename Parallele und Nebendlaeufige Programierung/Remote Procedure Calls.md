
__RPC__ rufen eine Funktion auf einen anderem Computer auf, für den Programmierer sollte es wenig Unterschied machen, ob die Funktion lokal oder auf einem anderen Rechner ausgeführt wird.

Gängige Anwendungen sind:
- Cloud Computing
- Datenbankberechnungen
- Online Banking

## RPC Schichten

1. Der Client schickt eine Anfrage zum Client Stub
2. Der Client Stub erzeugt eine Nachricht aus der Anfrage
3. Die Nachricht wird durch RPC Transport (z.B. HTTP) gesendet
4. Der Server Stub entimmt die Anfrage aus der Nachricht und gibt die Anfrage an den Server weiter
5. Der Server beantwortet die Anfrage 
6. Die Antwort wird analog zum Client weitergeleitet

> Ein Stub ist ein kurzzeitiger lokaler Ersatz fuer einen Dienst, der auf einem anderen Computer angeboten wird. Er bearbeitet Nachrichten. Der Server Stub wird auch als Skeleton bezeichnet.


