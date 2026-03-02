

>[!Note] Siehe auch [Graph](Mathe/Graph.md)



## Ungerichtet

> [!IMPORTANT] Definition
> Ein ungerichteter Graph $G$ ist ein Paar $(V, E)$ wobei:
> - $V$ eine endliche Menge ist und
> - $E$ eine Menge $2$-elementiger Teilmengen von $V$ ist

$e = \lbrace u,v\rbrace \in E$ bedeutet $u$ und $v$ sind durch Kante $e$ verbunden;
$u$ und $v$ sind adjazent.
$u$ und $e$ sind inzident(symmetrisch: $v$ und $e$ sind inzident) 

Wir schreiben gelegentlich $\left( V\atop 2\right)$ für die Menge $2$-Elementiger Teilmengen von $V$.

Dann koennen wir die zweite Bedingung schreiben als $E\subseteq \left( V\atop 2\right)$

>[!WARNING] Wenn nicht anders angegeben, sei $n= |V|$ und $m = |E|$

## Gerichtet

>[!IMPORTANT] Definition
> Ein gerichteter Graph $G$ ist ein Paar $(V, E)$, wobei:
> - $V$ eine endliche Menge ist und
> - $E$ eine Menge geordneter Paare von $V$ ist


$e = (u, v) \in E$ bedeutet: Die Kante $e$ geht von $u$ nach $v$;
$u$ und $v$ sind adjazent;
$u$ und $e$ sind inzident;
$v$ und $e$ sind inzident

Wir können die zweite Bedingung auch schreiben als $E\subseteq V\times V$

Jeder ungerichtete Graph kann als ein gerichteter Graph dargestellt werden.

## Wege

> [!IMPORTANT] Definition
> Wir nennen eine Sequenz $v_0, \dots, v_k$ mit $k \geq 0$ einen Weg von $v_0$ nach $v_k$ in $G = (V, E)$, wenn:
> - $v_i \in V \forall 0 \leq i\leq k$, sowie
> - wenn $G$ ungerichtet ist: $\lbrace v_i, v_{i+1}\rbrace \in E \forall 0\leq i< k$
> -  wenn $G$ gerichtet ist: $(v_i, v_{i+1}) \in E\forall 0 \leq i < k$


Wir nennen $k$ die Länge des Weges.

## Pfad

Ein Weg $v_0, \dots, v_k$ ist einfach, auch genannt Pfad, wenn gilt:
alle Knoten $v_i$ sind paarweise verschieden, bis auf möglicherweise Anfangs und Endknoten.

Wenn $v_i = v_j$ für $0\leq i, j, \leq k$, dann gilt $i=j$ oder $\lbrace i,j\rbrace = \lbrace 0, k\rbrace$

## Zyklus

Ein Weg $v_0, \dots, v_k$ heißt geschlossen, wenn $v_0 = v_k$

>[!IMPORTANT] Definition
> Wenn $G$ ungerichtet ist, ist ein Zyklus ein geschlossener Pfad der Länge $k \geq 3$
> Wenn $G$ gerichtet ist, ist ein Zyklus ein geschlossener Pfad der Länge $k\geq 2$

Ein Graph $G$ heißt azyklisch, wenn er keinen Zyklus enthält.

## Erreichbarkeit 

Sei $G$ ein gegebener Graph.
Ein Knoten $v$ heißt erreichbar von $u$, wenn es einen Weg von $u$ nach $v$ in $G$ gibt. Wir schreiben $u\leadsto_G v$ 

Wenn es einen Weg von $u$ nach $v$ gibt, dann gibt es auch einen Pfad von $u$ nach $v$

In einem ungerichteten Graphen $G$ ist $\leadsto_G$ eine [Äquivalenzrelation](Äquivalenzrelationen.md).
D.h. für alle $u, v, w \in V$ gilt:

__Reflexiv__
$v\leadsto_G v$
__Symmetrisch__
wenn $u\leadsto_G v$, dann $v\leadsto_G u$
__Transitiv__
wenn $u\leadsto_G v$ und $v\leadsto_G w$, dann $u\leadsto_G w$

Jede Äquivalenzklasse der Erreichbarkeitsrelation $\leadsto_G$ heißt Zusammenhangskomponente. Insbesondere ist die Zusammenhangskomponente von $u$ die Menge $\lbrace v\in V| u\leadsto_G v\rbrace$
Ein Graph $G$ heißt __zusammenhängend__, wenn es nur eine Zusammenhangskomponente gibt. $u\leadsto_G v \forall u, v\in V$

>[!WARNING] In einem gerichteten Graphen ist $\leadsto_G$ keine Äquivalenzrelationu
### Zusammenhang

In einem gerichteten Graphen gibt es verschiedene Definitionen von Zusammenhang in gerichteten Graphen
#### Schwach

Wir vergessen die Richtung der Kanten von $G$

#### Stark

Wir definieren eine neue [Äquivalenzrelation](Äquivalenzrelationen.md) $u \leftrightsquigarrow_G v$  genau dann, wenn $u \leadsto_G v$ und $v\leadsto_G u$

Jede Äquivalenzklasse der Relation $\leftrightsquigarrow_G$ heißt starke Zusammenhangskomponente.

Die starke Zusammenhangskomponente von $u$ ist die Menge $\lbrace v\in V| u\leadsto_G v\land v\leadsto_G u\rbrace$

Ein Graph $G$ heisst stark zusammenhaengend, wenn es nur eine starke Zusammenhangskomponente gibt. $u\leadsto_G v\forall u, v\in V$

## Grad

>[!IMPORTANT] Definition
> In einem ungerichteten Graphen $G$ ist der Grad $\deg(u)$ eines Knoten $u$ die Anzahl zu $u$ inzidenter Kanten:
> $$\deg(u) = |\lbrace v\in V | \lbrace u,v\rbrace \in E\rbrace|$$
> In einem gerichteten Graphen $G$ unterscheiden wir zwischen Eingangs und Ausgangsgrad
> Der __Ausgangsgrad__ $\deg^+(u)$ ist die Anzahl von $u$ ausgehender Kanten: $\deg^+(u) = |\lbrace v\in V | (u, v)\in E\rbrace|$
> Der __Eingangsgrad__ $\deg^-(u)$ ist die Anzahl in $u$ eingehender Kanten $\deg^-(u) = |\lbrace v\in V | (v, u) \in E\rbrace|$

In einem ungerichteten Graphen $G$ gilt:

$2m = \sum_{v\in V} \deg(v)$
$m \leq \left(n\atop 2\right)\leq n^2$

In einem gerichteten Graphen $G$ gilt:
$m = \sum_{v\in V} \deg^+(v) = \sum_{v\in V}\deg^-(v)$
$m\leq n^2$

Wir nennen einen Graphen dicht besetzt, wenn $m= \Theta(n^2)$
Wir nennen einen Graphen dünn besetzt, wenn $m = O(n)$

## Schleifen

Schleifen sind Kanten der Form $(v, v)$

In der Regel betrachten wir Graphen ohne Schleifen.

---

Ein gewurzelter gerichteter [Baum](Baum.md) $T$ ist ein gerichteter Graph $(V, E)$ mit folgenden Bedingungen:

- Es gibt keine Schleifen d.h. $(v, v)\not\in E\forall v \in V$
- Es gibt genau einen Knoten $r\in V$ mit $\deg^-(r) = 0$
- Für alle $u\in V\setminus\lbrace r\rbrace$ gilt $\deg^-(u) = 1$
- Für alle $u\in V$ gilt $r\leadsto_T u$

## Teilgraph

>[!IMPORTANT] Definition
> $G' = (V', E')$ ist Teilgraph von $G = (V, E)$, wenn
> $V'\subseteq V$
> $E' \subseteq E$

## Spannbaum

>[!IMPORTANT] Defintion
> Sei $G$ ein ungerichteter Graph.
> Ein Baum $T = (V', E')$ sodass:
> $T$ ist Teilgraph von $G$
> $V' = V$
> heißt Spannbaum von G


## Darstellung

### Unsortierte Kantenfolge

Wir speichern eine Folge aller Kanten als Array oder Liste

$$(u_1, v_1), \dots, (u_m, v_m)$$
Der Speicherbedarf ist $\Theta(m)$ Speicherzellen

## Adjazensliste

Für jeden Knoten $u$ speichern wir eine List $L_u$ bzw Array $A_u$.
Für jede Kante $(u, v)$ fügen wir $v$ in $L_u$ bzw. $A_u$ ein.

Der Speicherbedarf ist $\Theta(n+m)$ Speicherzellen

## Adjazensmatrix

Wir speichern eine Matrix

$$A[u, v] = \begin{cases}1 : (u, v)\in E\\0\end{cases}$$

Der Speicherbedarf ist $n^2$ Bits

### Kanteninformationen

Gelegentlich wollen wir Zusatzinformationen zu den Kanten abspeichern.
Dann erhalten wir einen Gewichteten Graphen $G = (V, E, w)$
Ein Graph $G = (V, E)$ mit zusätzlicher Gewichtsfunktion $w: E\mapsto \mathbb Z$


## Breitensuche

Wir besuchen Knoten, die von $s$ erreichbar sind, 

Der Startknoten bildet das Level 0
Die Nachbarn von $s$, also alle Knoten $v$ mit $(s,v)\in E$ bilden das Level 1.
Die Knoten des Level $i \geq 2$ sind die Nachbarn von Level $i-1$ Knoten, die nicht schon besucht sind.

-> alle von $s$ erreichbaren Knoten werden sich in einem Level finden

__Algorithmus__

Zu jedem Knoten speichern wir einen Status: unentdeckt, entdeckt oder abgefertigt
anfangs ist nur $s$ entdeckt, alle anderen Knoten sind unentdeckt
wir speichern entdeckte Knoten in einer Queue $Q$, anfangs enthält sie nur $s$
Solange $Q$ nicht leer ist, machen wir folgendes:
wir entnehmen einen Knoten $u$ vom Anfang der Queue
für jeden unentdeckten Knoten $v$ mit $(u,v)\in E$ machen wir folgendes:
wir setzen $v$'s Status entdeckt
wir fügen $v$ ans Ende der Queue $Q$ ein
wir setzen $u$'s Status auf abgefertigt

-> Der Algorithmus endet, wenn $Q$ leer ist. Alle unentdeckten Knoten sind von $s$ nicht erreichbar.

Der Algorithmus läuft in $O(|V| + |E|) = O(n+m)$

## Tiefensuche

Sobald wir einen von $s$ erreichbaren Knoten $u$ entdecken, durchlaufen wir alle von $u$ erreichbare Knoten

__Algorithmus__

Zu jedem Knoten speichern wir einen Status, unentdeckt, entdeckt oder abgefertigt
anfangs sind alle Knoten unentdeckt
wir starten eine DFS von $s$

DFS von $u$:
	wir setzen $u$'s Status auf entdeckt
	für jeden unentdeckten Knoten $v$ mit $(u, v)\in E$ machen wir folgendes:
		wir starten rekursiv eine DFS von $v$
	wir setzen $u$'s Status auf abgefertigt


## Zusammenhangskomponenten entdecken

Wir starten mit einem beliebigen Startknote
Wir machen eine BFS oder DFS von $s$
-> liefert Zusammenhangskomponente von $s$

Solange es noch unentdeckte Knoten gibt:
Wiederhole die Graphtraversierung mit einem unentdeckten Knoten $s$
-> liefert weitere Zusammenhangskomponente

```
DFS-explore-complete(G):
	n = Anzahl an Knoten von G
	for u = 1 ..., n do
		state[u] = unentdeckt
		p[u] = bbar

	t = 0
	for s = 1,..., n do
		if state[s] = unentdeckt then
			DFS(G,s)
```

Ein Blick ergibt eine Laufzeit von $O(n+m)$

## Kantenarten

Sowhol BFS als auch DFS von $s$ liefert einen Suchbaum $T$ mit Wurzel $s$.
$T = (V_T, E_T)$ ist ein gerichteter Baum, der Teilgraph von $G = (V, E)$ ist.

Jede Kante $(u, v) \in E$ hat einen der folgenden Typen:

__Baumkante__
$(u, v) \in E_T$

__Vorwärtskante__
$(u, v)\not\in E_T$ und $v$ ist Nachfahre von $u$ in $T$

__Rückwärtskante__
$(u, v)\not \in E_T$ und $v$ ist Vorfahre von $u$ in $T$

__Querkante__
alle anderen Kanten

## Zyklen finden

Wir können die Tiefensuche zu einem Algorithmus anpassen, der:

- in Zeit $O(n+m)$ laeuft
- wenn $G$ einen Zyklus enthält, einen solchen Zyklus zurückgibt und
- ansonsten zurückgibt, dass $G$ azyklisch ist


>[!IMPORTANT] Definition
> Eine topologische Sortierung von $G = (V, E)$ ist eine Permutation $v_1, \dots, v_n$ von $V$, sodass:
> wenn $(v_i, v_j)\in E$, dann gilt $i< j$ Kanten gehen nur von kleineren zu grösseren Knoten