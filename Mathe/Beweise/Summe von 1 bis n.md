Turm verschieben(Ziel, Hilfsplatz, Startplatz)
    Wenn wir nur 1 Scheibe auf dem Startplatz haben verschiebe sie auf den Zielplatz, Zurückgeben
    Turm mit -1 Scheiben verschieben (Hilfsplatz, Zielplatz, Startplatz)
    Bewegung von letzter Scheibe von Startplatz auf Zielplatz
    Turm mit -1 Scheiben verschieben(Zielplatz, Startplatz, Hilfsplatz)
$$\sum_{k=1}^nk = 1+2+...+n= {n(n+1) \over 2}$$

Induktionsanfang:
$$A(1): \sum_{k=1}^{1}k=1={1\cdot (2+1) \over 2}$$
Induktionsvoraussetzung: Für ein $n \in N$ gelte A(n)
Induktionsschritt: Zu zeigen: $A(n+1)$ wahr
$$\begin{align}
\sum_{k=1}^{n+1}k &=\sum_{k=1}^{n}k+(n+1)\\
&={n(n+1)\over 2} + (n+1) = {n(n+1)+2(n+1) \over 2} \\
&={(n+1) \cdot (n+2) \over 2}\\
q.e.d \blacksquare
\end{align}$$
