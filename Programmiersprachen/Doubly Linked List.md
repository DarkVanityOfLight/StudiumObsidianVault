
Doppelt verkettete Listen sind flexibler als [Verkettete Listen](Verkettete%20Listen.md). Wir verwenden einen zusätzlichen Zeiger auf das vorhergehende Element.

```c
struct DListItem {

	DListItem* next;
	DListItem* prev;
	type elem;
}
```


`find`, `insert`, `erase` sind Analog zu Verketteten Listen.


## Splice

`splice(q, r, t)` $q, r$ sind Zeiger auf das erste und letzte Item einer Teilliste $(a_i, \dots, a_j)$, $t$ ist ein Zeiger auf ein Item $b$ nachdem wir einfügen wollen.

```c
void splice(DListItem* q, DListItem* r, DListItem* t){
	ListItem* p = q->prev;
	ListItem* s = r->next
	p->next = s;
	s->prev = p;

	ListItem* u = t->next;
	r->next = u;
	u->prev = r;
	t->next = q;
	q->prev = t;
}
```

Laufzeit in $O(1)$


