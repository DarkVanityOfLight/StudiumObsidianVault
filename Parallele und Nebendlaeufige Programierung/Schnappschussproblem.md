
Das Schnappsuchssproblem besteht darin, ein Verfahren zur Ermittlung eines [Konsistenter Schnitt](Schnitte.md#Konsistenter%20Schnitt) und dessen [globalen Zustands](Globaler%20Systemzustand.md) während der Ausführung eines verteilten Systems anzugeben.


## Sicherungspunkte
Dazu setzt jeder [Prozess](Prozess.md) $p_i, 1\leq i\leq n$ hin und wieder einen lokalen Sicherungspunkt $z_{ij} = (p_i(e_i), n_i(e_i))$
- $p_i(e_i)$ lokaler Zustand
- $n_i(e_i)$ Menge gesendeter und empfangener Nachrichten

Weise Zeitstempel $v_i(z_{ij})$ zu; erhöhe davor $i$-te Komponente um $1$(d.h. Zeitstempel berechnen ist ein Ereignis)


## Nachrichten

Definiere $next(p_i)$ als $p_{i+1}$ falls $i< n$ und $p_1$ falls $i=n$
Unmittelbar nach Aufzeichnung von $z_{ij}$ sendet $p_i$ eine Nachricht an den Prozess $next(p_i)$, die den Zeitstempel $v_i(z_{ij})$ enthält.

Bei Empfang einer Nachricht mit dem Zeitstempel $v_k(z_{km})$ eines lokalen Sicherungspunktes bildet $p_i$ (nach dem Inkrementieren der i-ten Komponente der [Vektor Uhr](Vektor%20Uhren.md) $v_i$) das komponentenweise Maximum von $v_i$ und dem empfangenen Zeitstempel $v_k(z_{kn})$. Dies ist der neue Wert von $v_i$ und der Zeitstempel des Empfangsereignisses $e_{ij}$


## Lösung des Schnappschussproblem

Wähle beliebigen lokaler Sicherungspunkt $z_{ij}$
Finde anhand der Zeitstempel sukzessive vorangehende lokale Sicherungspunkte der anderen Prozesse
Die Vereinigung der lokalen Sicherungspunkte abzüglich der gesendeten Nachrichten, die bereits empfangen wurden, ergeben einen zulässigen globalen Zustand.