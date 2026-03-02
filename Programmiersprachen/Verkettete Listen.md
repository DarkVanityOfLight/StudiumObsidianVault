

Verkettete Listen bilden eine Alternative zu [Arrays](Array.md), um eine Folge $a_1, \dots, a_n$ zu speichern. Wir bilden eine Kette bestehend aus Zeigern auf das nachfolgende Element

```c
struct ListItem {
	ListItem* next;
	type elem;
}
```


Das ende der Liste wird gekennzeichnet durch den $nullptr$

## Suchen

Gibt es ein $i$ mit $a_i = x$
Wenn ja gib einen Zeiger auf das entsprechende Item zurück Ansonsten, gib $nullptr$ zurück

```c
ListItem* find(x, LinkedList L){
	if (L.first == nullptr) return nullptr;

	ListItem* p = L.first;
	while(p-> elem != x and p->next != nullptr){
		p = p->next;
	}

	if(p->elem !=x){
		p = nullptr;
	}

	return p;
}
```

`L.find(x)` läuft in $O(n)$


## Einfügen

`L.insert_after(p, x)` $p$ ist ein Zeiger auf ein Item $a_i$ der Liste, füge $x$ nach $a_i$ ein

```c
void insert_after(ListItem* p, int x){
	ListItem* q = new ListItem;
	q->elem = x;
	q->next = p->next;

	p->next =q;
}
```

`L.insert_after(p, x)` läuft in Zeit $O(1)$

## Löschen

`L.erase_after(p)` $p$ ist Zeiger auf ein Element $a_i$ oder den Anfang der Liste. Lösche das Element $a_{i+1}$.

```c
void erase_after(ListItem* p){
	ListItem* q = p->next;

	p->next = q->next;
	delete q;
}
```

`L.erase_after(p, x)` läuft in Zeit $O(1)$.


