

Dijkstra's Link-State Routing Algorithmus ist eine zentralisierter Ansatz, bei dem die Netzwerktopologie und die Verbindungskosten allen Knoten bekannt sind. Dies wird durch "Link-State-Broadcast" erreicht, wodurch alle Knoten dieselben Informationen haben.

Der Algorithmus berechnet die Pfade mit den geringsten Kosten von einem Knoten zu allen anderen Knoten und erstellt eine Routingtable für diese Kosten. Der Prozess ist iterativ: Nach $k$ Iterationen kennt man den Pfad mit den geringsten Kosten zu $k$ Zielen

## Notation

$c(x, y)$ ist ein Direkter Link von $x$ nach $y$.
$c(x, y) = \infty$ sollten sie keine Direkten Nachbarn sein.

$D(v)$ Aktuelle Schätzung der Kosten des Pfades mit den geringsten Kosten von der quelle zur Zieldestination $v$

$p(v)$ Vorgängerknoten entlang des Pfades von der Quelle zu $v$.

$N'$ Die Menge von Knoten, deren Pfad mit den geringsten Kosten definitiv bekannt ist.

```python
N' = {u}
forall nodes v
	if v adjacent to u
		 then D(v) = c_u,v
    else D(v) = infty

Loop
	find w not in N' such that D(w) is a minimum
	add w to N'
	update D(v) 
		for all v adjacent to w and not in N':
			D(v) = min(D(v), D(w) + c_wv)
	/*
	New least path cost to v is either old least
	path to v or known least cost path to w
	direct cost from w to v
	*/
untill all nodes in N'
```

In jeder der $n$ Iterationen müssen wir alle Knoten $w$ die nicht in $N$ sind betrachten, wir erhalte $n(n+1)/2$  Vergleiche daher läuft der Algorithmus in $O(n^{2})$, es ist jedoch möglich den Algorithmus in $O(n\log n)$ zu implementieren.

Wir benötigen auch $O(n^{2})$ Nachrichten da jeder Router seinen Verbindungsstatus-Informationen an die anderen $n$ Router senden muss.