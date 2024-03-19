Jeder [Prozess](Prozess.md) $p_i$ hat einen [[Vektor]] $v_i$ als Uhr.
Die Dimension des Vektors ist $n=\text{Anzahl an Prozessen}$ 
$v_i[j]$: Counter des Prozesses $i$ nach Wissen Prozess $p_i$

Zeitstempel von Ereignissen sind auch Vektoren.

## Operationen

$$\max\lbrace v_i, v_k\rbrace =_{df} (\max\lbrace v_i[1], v_k[1]\rbrace \dots \max\lbrace v_i[n], v_k[n]\rbrace)$$

$$v_i = v_k \iff \forall j.(1\leq j\leq n \implies v_i[j] = v_k[j])$$
$$v_i\not = v_k \iff \exists j. (1\leq j\leq n \land v_i[j] \not = v_k[j])$$
$$v_i < v_k \iff v_i \not = v_k \land \forall j. (1\leq j\leq n \implies v_i[j]\leq v_k[j])$$
$$v_i \leq v_k \iff v_i = v_k \lor v_i < v_k$$

$$v_i\not < v_k \iff v_i = v_k \lor \exists j. (1\leq j\leq n \land v_i[j] > v_k[j])$$

## Als Partielle Ordnung

$\leq$ ist eine [Partielle Ordnung](Partielle%20Ordnung.md) auf $\mathbb Z^n$

## Algorithmus

Initialisiere $v_i$ als Nullvektor der Dimension $n$
Bei jedem [Ereignis](Ereignis.md) $e_{ij}$, erhöhe $v_i[i]$ um $1$
Interne Ereignisse sowie Sendeereeignisse $e_{ij}: v_i(e_{ij})$ momentaner Wert von $v_i$
Jede Nachricht enthält Zeitstempel $v_k(e_{kn})$ des Sendeereignisses $e_{kn}$

Empfängt $p_i$ eine Nachricht mit Zeitstempel $v_k(e_{kn})$
- $v_i = \max\lbrace v_k(e_{kn}), v_i\rbrace$ nach Erhöhung von $v_i[i]$ um $1$
- $v_i(e_{ij})$ des Empfangsereignisses $e_{ij}: v(e_{ij})$ momentaner Wert von $v_i$
