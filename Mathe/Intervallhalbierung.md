
Sei 

$$a_{1}= a\qquad b_{1} = b$$
Wir konstrurieren [Folgen](Mathe/Folgen.md) $(a_{n})$ und $(b_{n})$ induktiv. Sind $a_{n}$ und $b_{n}$ konstruriert, sei
$$
c = \frac{a_{n}+b_{n}}{2}
$$
Falls $f(c) = 0$ haben wir eine Nullstelle gefunden und stoppen.
Anderenfalls setze
$$a_{n+1} = c \qquad b_{n+1} = b_{n} \qquad \text{falls} f(c) < 0$$
und
$$a_{n+1} = a_{n} \qquad b_{n+1} =c \qquad \text{falls}f(c) > 0$$

Damit erhalten wir eine [monoton](Mathe/Folgen.md#Monotonie) wachsende Folge $(a_{n})$ die von oben durch $b$ beschränkt ist, und eine monoton fallende Folge $(b_n)$ die von unten durch $a$ beschränkt ist, denn
$$a\le a_{n} \le a_{n+1} \le b_{n+1} \le b_{n \le}b$$
