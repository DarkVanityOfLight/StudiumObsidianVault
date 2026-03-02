
## Was ist ein algorithmisches Problem

### EIngabe
$$x,y \in \mathbb N$$
Es gibt viele möglichkeiten $x, y$ in verschiedenen [Positionssystemen](Positionssystem.md) darzustellen.

### Ausgabe

Gegeben Zahlen $x = x_{n-1} ... x_{0}$ und $y = y_{n-1} ... y_{0}$ zur Basis $B$,
gebe $x + y$ als Zahl zur Basis $B$ aus.



## Was ist ein Algorithmus

## Algorithmen beschreiben

$$\begin{align*}
&add(x_{n-1} ... x_{0}, y_{n-1}...y_{0})\\
&c_{o} \leftarrow 0\\
&for\; i = 0, ..., n-1\; do:\\
&\quad | (c_{i+1,}y_{i}) <- x_{i} + y_{i} +c_{i}\\
&y_{n} \leftarrow c_{n}\\
&return z_{n}...z_{0}
\end{align*}$$

## Qualität

WIe gut ist ein Algorithmus?
benutzt wenig Ressourcen (z.B.: Zeitbedarf, Speicherplatz, Energie, ...)

Fokus auf Zeitbedarf, Laufzeit

__Ansatz__: Zählen der elementaren Operationen
