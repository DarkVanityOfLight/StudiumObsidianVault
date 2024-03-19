$n$ [Prozesse](Prozess.md), mit maximal $f<\frac{n}{3}$ [Crashes](Crashes.md), in einem System mit (partiell) [Synchroner Kommunikation](Kommunikationsmodelle.md#Synchrone%20Kommunikation). Jeder Prozess $p_i$ hat einen lokalen Wert $v_i$

Ein Konsens Algorithmus bestimmt einen Wert $v$ sodass:
- __Agreement__ Alle korrekten Prozesse einigen sich auf $v$
- __Termination__ Der Algorithmus terminiert in endlicher Zeit
- __Validity__ Der Wert $v$ muss ein Wert sein, den ein Prozess in einer Nachricht gesendet hat(oder es muss der lokale Wert eines Prozesses sein)

