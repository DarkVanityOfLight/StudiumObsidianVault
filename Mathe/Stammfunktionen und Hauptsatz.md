Wir wollen den Ableitungsprozess umkehren. Deshalb definieren wir:

Eine __Stammfunktion__ einer Funktion $f: [r, s]\to\mathbb R$ ist eine differenzierbare Funktion $F: [r, s]\to\mathbb R$ mit
$$F' = f$$
Die Funktion $f$ beschreibt als die Steigung der Stammfunktion $F$. Mit Hilfe des Riemannintegrals und des [Mittelwertsatzes der Integralrechnung](Mittelwertsatz%20der%20Integralrechnung.md) erhalten wir das folgende Existenz- und Eindeutigkeitsresultat für Stammfunktionen, den sogennanten __Hauptsatz der Differential- und Integralrechnung__. Er gibt uns außerdem eine Methode, um ein Integral mit Hilfe einer Stammfunktion zu berechnen:
Die Differenz der Funktionswerte einer Stammfunktion $F$ bei $r$ und $s$ gibt das Integral von $f$ zwischen $r$ und $s$, d.h. die Fläche unter dem Funktionsgraphen von $f$ zwischen $r$ und $s$.

> Sei $f: [r, s] \to\mathbb R$ stetig.
> Die Funktion $F: [r, s]\to\mathbb R$ mit $$F(x) = \int^{x}_{r} f(t)dt$$ ist eine Stammfunktion von $f$
> Sind $F$ und $G$ Stammfunktionen von $f$, so ist $F - G$ konstant.
> Für jede Stammfunktion $F$ von $f$ gilt: $$\int^{s}_{r}f(t)dt = F(s) - F(r)$$


---

Wir schreiben kurz
$$\int f\;dx$$
für jede Stammfunktion von $f$ und 
$$[F(x)]^{s}_{r} = F(s) - F(r)$$


## Eindeutigkeit

Die Stammfunktion ist nach dem Hauptsatz nur eindeutig bis auf eine Konstante.
Zum Beispiel sind also alle möglichen Stammfunktionen von $f(x) = 3x^{2}$ von der Form $F(x) = x^{3}+c$ mit einer beliebigen Konstanten $c\in\mathbb R$. Alle diese Funktionen kann man zum Integrieren von $f$ verwenden, z.B. ist
$$\begin{align*}
\int^{1}_{0} x^{2} dx &= F(1) -  F(0)\\
&= (1+c) - (0+c)\\
&= 1-0 = 1 
\end{align*}$$
denn $c$ kürzt sich in der Differenz.
