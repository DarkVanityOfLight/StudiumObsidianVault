
Jeder [Prozess](Prozess.md) hat eine [Uhr](Uhren.md) in der Form eines Counters. Der Counter gibt eine untere Schranke für die Anzahl an Ereignissen an, von denen der Prozess weiß:

- Lokale Ereignisse, die den Prozess betreffen
- Ereignisse von anderen Prozessen von denen der Prozess über Nachrichten lernt

## Algorithmus

Gegeben seien Prozesse $p_i = (E_i, \leq_i, \alpha_i)$
Nenne Ereignisse in $E_i\quad e_ij$
Jeder Prozess hat Uhr $c_i$
Wenn $p_i$ eine Nachricht sendet, enthält die Nachricht $c_i$
Jedes Ereignis $e_ij$ bekommt einen Zeitstempel $c_i(e_ij)$ zugeordnet
fuer Ereignis $e_ij$ erhoehe $c_i$ und nehme neues $c_i$ als $c_i(e_ij)$

Erhoehung:
-  $e_{ij}$ internes oder Sendeereignis: erhoehe $c_i$ um 1
- $e_ij$ Empfangsereignis mit Uhr $c_k$: Setze $c_i$ auf $\max\lbrace c_i, c_k\rbrace + 1$

