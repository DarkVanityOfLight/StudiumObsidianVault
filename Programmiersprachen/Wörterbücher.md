
Unsere Daten sind Elemente der Form $e = (k, v)$.
Wir wollen eine Menge $S$ von Elementen darstellen, sodass folgende Operationen unterstützt werden:

- `S.find(k)` Gibt es ein Element $e\in S$ mit $key(e) = k$, wenn ja dann gib den Wert $v$ zurück, sodass $(k, v) \in S$ Wenn nein gib $\perp$ zurück.
- `S.insert(e)` fügt $e$ in $S$ ein
- `S.remove(k)` löscht das Element mit Schlüssel $k$ aus $S$.



Wir können Wörterbücher relativ effizient durch selbst balancierende Binärbäume darstellen, z.b. einen [Rot-Schwarz Baum](Rot-Schwarz%20Baum.md).


Eine weitere einfache Lösung des Problems ist direkte Adressierung.

Wir verwalten ein Array $P[0\dots U-1]$ mit Zeigern auf die Elemente in $S$:

$P[k]$ ist ein Zeiger auf das Element mit dem Schlüssel $k$ in $S$

Wir können:
- In Zeit $O(1)$ auf das Element mit dem Schlüssel $k$ zugreifen
- In Zeit $O(1)$ das Element mit Schlüssel $k$ hinzufügen/aktualisieren
- In Zeit $O(1)$ das Element mit dem Schlüssel $k$ löschen.

Der Nachteil dieses Ansatzes ist der Speicherbedarf von $\Theta(U)$
in sehr vielen Anwendungen ist $U$ impraktikabel groß!
Es ist jedoch eine sehr sinnvolle Lösung, wenn $U$ klein ist.

## Hashing

Gegeben $k$ errechnen wir einen Index $h(k)$ im Array $T$.

Eine Hashfunktion $h$:
$$h: K = \lbrace0,\dots, U-1\rbrace \to \lbrace0, \dots, m-1\rbrace$$

für verschiedene Schlüssel $k, k'\in S$ kann gelten:
$$h(k) = h(k')$$


deswegen speichern wir an jeder Position $j$ der Hashtabelle eine [Verkettete Liste](Verkettete%20Listen.md) $L_{j}$, $L_{j}$ speichert alle Elemente $e\in S$ mit $h(key(e)) = j$

## Hashing mit offener Adressierung

Wir speicher die Elemente direkt in der Tabelle, bei einer Kollision suchen wir systematisch einen freien Platz, der einfachste Ansatz ist lineares Sondieren, wir erhöhen den Index bis ein freier Platz gefunden wurde.

## Laufzeiten

| Funktion       | Balacierte Suchbäume | Hashing mit Verkettung |
| -------------- | -------------------- | ---------------------- |
| find           | $O(\log n)$          | erwartet $O(1)$        |
| insert         | $O(n)$               | $O(n)$                 |
| remove         | $O(n)$               | $O(n)$                 |
| Speicherbedarf | $O(n)$               | $O(n)$                 |
| Minimum        | $O(\log n)$          | $O(n)$                 |


