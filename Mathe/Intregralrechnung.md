
Lassen wir ein Objekt im Schwerefeld der Erde fallen, dann unterliegt es(unter idealisierten Bedingungen d.h. ohne Reibung) einer konstanten Beschleunigung von $g=9.81 \frac{m}{s^{2}}$ d.h. wenn $f(x)$ die Position des Objektes zur Zeit $x$ und somit $f'(x)$ die Geschwindigkeit bezeichnet, dann gilt
$$f''(x) = g$$
Dies ist wieder eine Differenzialgleichung. Um deren Lösung zu finden müssen wir aus der [Ableitung](DIfferentialrechnung.md#^aee223) einer [Funktion](Mathe/Funktionen.md) den Funktionswert bestimmen. Diesen Prozess bezeichnet man als Integration. Da
$$(f'(x) - g\cdot x)' = f''(x) - g = 0$$
gilt, ist 
$$f'(x) - g\cdot x = c$$
konstant gleich $c\in\mathbb R$, d.h.

$$f'(x) = g\cdot x + c$$
Dabei ist $c = f'(0)$ die Geschwindigkeit des Objekts zur Zeit $x=0$. Ebenso gilt
$$(f(x) - g \cdot \frac{x^{2}}{2} - c \cdot x)' = 0$$
also
$$f(x) = g\cdot \frac{x^{2}}{2} + c\cdot x +d $$
mit einer Konstante $d\in\mathbb R$. Diese erhalten wir als die Position $d=f(0)$ des Objekts zur Zeit $x=0$.

Das Objekt hat nach $10$ Sekunden beispielsweise 
$$9.81 \frac{m}{s^{2}} \cdot \frac{(10s)^{2}}{2} = 490.5m$$
zurückgelegt.
Man kann also offenbar aus der Ableitung die Funktion bis auf eine Konstante (die ja beim Ableite weg fällt) bestimmen.
Diesen Prozess wollen wir im Folgenden genauer untersuchen. Insbesondere stellt sich die Frage, für welche Funktionen das Verfahren anwendbar ist.

