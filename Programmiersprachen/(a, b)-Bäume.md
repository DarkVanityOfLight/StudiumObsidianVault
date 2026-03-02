

Für einen Knoten $u$ sei der Grad $\deg(u)$ definiert als die Anzahl an Kindern von $u$.

> [!IMPORTANT] Definition
> Ein __(a, b)-Baum__ ist ein geordneter [Baum](Baum.md) $T$ mit folgenden Eigenschaften:
> - Alle inneren Knoten außer die Wurzel $r$ haben mindestens $a$ und höchstens $b$ Kinder $a \leq \deg(u) \leq b$ für alle inneren Knoten $u$ mit $u\not=r$
> - Die Wurzel $r$ hat mindestens 2 und höchstens $b$ Kinder $2 \leq \deg(r) \leq b$
> - Alle Blätter befinden such auf dem gleichen Level
> Jedem Knoten $u$ sind $\deg(u) - 1$ Schluessel als Splitter $s_1 \leq s_2 \leq \dots \leq S_{\deg(u) - 1}$ zugeordnet.
> Wir setzen $s_0 := - \infty$ und $S_{\deg(u)} := \infty$
> Die Schluessel im Teilbaum des $i$. Kindes sind in $(s_{i-1}, s_i]$
> Wir verlangen, dass $a\geq 2$ und $b \geq 2a -1$


```c
struct BNode{
	int deg;
	type s[b-1];
	BNode* children[b];
}

struct BTree{
	BNode* root;
	int h;
}
```

Typischerweise werden die eigentlichen Elemente in den Blättern gespeichert. Hierbei eignet sich besonders eine [Doubly Linked List](Doubly%20Linked%20List.md). Die Successor Funktion läuft dann sogar in $O(1)$

## Höhe

Für die Höhe eines $(a, b)$-Baums mit $n$ Schlüsseln gilt:
$$\log_b(n+1) \leq h \leq 1 + \log_a(n+1)$$



## Suche

Diesmal gibt `find` das Element mit dem kleinsten Schlüssel $k' \geq k$ zurück.

```python
def find(Node* x, type k, int h){
	bestimme i als kleinsten Wert <= j <= deg sodass k <= s[j]
	
	if h==1:
		return x->children[i]
	else:
		return find(x->children[i], k, h-1)
}
```

Find läuft in $O(h\log b)$, wenn $b$ eine feste Konstante ist, ist das in $O(h) = O(\log_a n) = O(\log n)$.

## Einfügen

Suche die Stelle, an der der Schlüssel $k$ bereits gespeichert ist oder eingefügt werden muss.
-> Wir sind entweder fertig oder erzeugen ein neues Blatt $b$ mit Schlüssel $k$
-> Der Elternknoten $x$ muss einen neuen Splitter $s=k$ und Kind $c=b$ einfügen.

Wir wiederholen:
- füge Splitter $s$ und Kind $c$ in das Splitterarray und Kindarray von $x$ ein
- Wenn $\deg(x)\leq b$ sind wir fertig.
- Ansonsten ist der neue Grad $\deg(x) = b+1$ und wir machen eine Spaltung von $x$:
	- Wir wählen den mittleren Splitter $s[m]$ mit $m = \lceil\frac{b}{2}\rceil$ zur Aufteilung
	- Wir erzeugen einen neuen Knoten $L$  links von $x$, der alle kleineren Splitter als $[m]$ und das Kind $c[m]$ enthält
	- $x$ behält alle verbleibenden Splitter und Kinder(diese enthalten nur Schlüssel $> s[m]$)
	- Jetzt müssen wir den neuen Knoten $L$ mit dem Splitter $s[m]$ an den Elternknoten von $x$ einfügen
	  -> Wir setzen $c= L, s=s[m]$ und $x$ auf den Elternknoten von $x$

Wenn die Wurzel mehr als $b$ Kinder bekommen soll, spalten wir die Wurzel in zwei Knoten ($L$ und $x$) und erzeugen eine neue Wurzel mit Kindern $L$ und $x$.
-> die Höhe des Baumes erhöht sich.

Wir fuegen in Zeit $O(\log_a(n) \cdot b)$ in einen $(a, b)$-Baum ein.

## Spaltung

Wir spalten einen Knoten $x$ mit $b+1$ Kindern am mittleren Splitter $s[m]$ mit $m = \left\lceil\frac{b}{2}\right\rceil$ 
- $L$ bekommt die kleineren $m = \left\lceil\frac{b}{2}\right\rceil$ Kinder
- $x$ behält die grösseren $(b+1) - m$ Kinder

![spalt](spalt.png)

Die Laufzeit der Spaltung von $x$ ist $O(b)$ also $O(1)$ wenn $b$ eine Konstante ist.



## Entfernen

Wir suchen die Stelle, an der der Schlüssel $k$ bereits gespeichert ist und gelöscht werden muss

Wir entfernen das Blatt. Dessen Elternknoten $x$ verliert also ein Kind $c$ und einen Splitter.

Wir wiederholen:
- Wenn $\deg(x) \geq a$, dann beenden wir
- Ansonsten ist $\deg(x) = a-1$. Wir betrachten den linken oder rechten Geschwister knoten $y$ von $x$.

Fall 1: $y$ hat $a+t$ Kinder mit $t\geq 1$
Wir gleichen die Grade von $x$ und $y$ an: $y$ gibt $\left\lceil\frac{t}{2}\right\rceil \geq 1$ Kinder an $x$ ab.
Dabei gibt $y$ einen Splitter an seinen Elternknoten $p$ und $p$ einen Splitter an $x$ ab.

Fall 2: $y$ hat $a$ Kinder

Wir fusionieren $x$ und $y$: $x$ gibt alle Kinder und Schlüssel an $y$ ab.
Dabei gibt der Elternknoten $p$ den entsprechenden Splitter an $y$ ab und verliert ein Kind.
Wir betrachten nun den Elternknoten $p$ als Knoten $x$

### Sonderfall letztes Kind

Suche die Stelle, an der der Schlüssel $k$ bereits gespeichert ist und gelöscht werden muss
-> Wir entfernen das Blatt. Dessen Elternknoten $x$ verliert also ein Kind $c$ und einen Splitter

Wir entfernen den zugehörigen Splitter:
Wenn das Blatt das letzte Kind des Elternknoten ist, vertausche Splitter mit Wert $k$ durch Vorgänger Splitter
Nun können wir das Blatt und den Splitter $k$ entfernen

![entf2_001](entf2_001.png)



Wir löschen in $O(\log_a(n) \cdot b)$
## Fusionieren

Wir fusionieren einen Knoten $x$ mit $a-1$ Kindern mit einem Nachbarn mit $a$ Kindern.

Der Elternknoten verliert ein Kind und gibt den dazugehörigen Schlüssel an den fusionierten Knoten ab

Der neue Knoten hat $2a-1\leq b$ Kinder

![fus](fus.png)

Die Laufzeit einer Fusion ist $O(b)$ also $O(1)$ wenn $b$ eine Konstante ist.

## Angleichen

Wir gleichen einen Knoten $x$ mit $a-1$ Kindern mit einem Nachbarn $y$ mit $a+t$ Kindern an:

Wir setzen $l = \left\lfloor\frac{t}{2}\right\rfloor$ und lassen den Nachbarn $a+l$ Kinder behalten.
-> $x$ bekommt $t-l = \left\lceil\frac{t}{2}\right\rceil \geq 1$ zusätzliche Kinder

Dabei gibt $y$ einen Schlüssel an den Elternknoten ab und der Elternknoten einen Schlüssel an $x$ ab.

![angl](angl.png)


Die Laufzeit einer Angleichung ist $O(b) \implies O(1)$.


## Laufzeiten

| Funktion          | Laufzeit    |
| ----------------- | ----------- |
| `S.find(k)`       | $O(\log n)$ |
| `S.insert(e)`     | $O(\log n)$ |
| `S.remove(k)`     | $O(\log n)$ |
| `S.min()`         | $O(1)$      |
| `S.max()`         | $O(1)$      |
| `S.successor(x)`  | $O(1)$      |
| `S.predecessor(x)` | $O(1)$            |

