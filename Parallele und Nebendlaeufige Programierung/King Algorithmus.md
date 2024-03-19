
Der Algorithmus verlaeuft in __Phasen__ und mit [synchroner Kommunikation](Kommunikationsmodelle.md#Synchrone%20Kommunikation). In jeder der Phasen gibt es einen King, also ein Prozess, der die Führung übernimmt.
Welcher [Prozess](Prozess.md) in welcher Phase King ist, wird im Voraus bestimmt. Es gibt maximal $f+1$ Phasen($f < \frac{n}{3}$) und damit $f+1$ Kings. Jede der Phasen hat $3$ __Runden__.

Runde 1:
$p_i$ sendet $v_i$ an alle Prozesse (inklusive $p_i$) für alle $i$

Runde 2:
if($p_i$ einen Wert $y$ mindestens $n-f$ mal empfangen hat) then
	$p_i$ sendet $propose(y)$ an alle Prozesse
if($\exists z.$ sodass $p_i, propose(z)$ mehr als $f$ mal empfangen hat) then
	$p_i$ setzt $v_i = z$

Runde 3:
$k_j$ sendet eigenen lokalen Wert $w$
if($p_i, propose(z)$ weniger als $n-f$ mal empfangen hat) then
	$p_i$ setzt $v_i = w$
