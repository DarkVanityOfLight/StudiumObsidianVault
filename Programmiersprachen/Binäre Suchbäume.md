
Ein binär, geordneter [Baum](Baum.md) heißt binärer Suchbaum, wenn:

- jedem Knoten $u$ ist ein Schlüssel $k_u$  aus einer total geordneten Schlüsselmenge zugeordnet
- für jeden Knoten $u$ gilt:
	- alle Schlüssel im linken Teilbaum von $u$ sind $< k_u$
	- alle Schlüssel im rechten Teilbaum von $u$ sind $> k_u$



```c
struct Node{
	Node* parent;
	Node* lchild;
	Node* rchild;
	type key;
	type val;
}

struct Tree {
	Node* root;
}

Node* find(Node* x, type k){
	if(x == nullptr or x->key == k){
		return x;
	}
	if(k < x-> key){
		return find(x->lchild, k);
	}else{
		return find(x->rchild, k)
	}
}

Node* min(Node* u){
	if(u->lchild != nullptr){
		return min(u->lchild)
	}
	return u
}

Node* successor(Node* u){
	if(u->rchild != nullptr){
		return min(u->rchild);
	}
	Node* p = u->parent;
	while(p != nullptr and u != p->lchild){
		u = p;
		p = p->parent;
	}
	return p;
}
```


für insert passen wir unsere `find` Funktion an sodass sie entweder ein Element mit Schlüssel $k$ oder die Stelle, an der ein solches Element eingefügt werden muss zurückgibt.

Remove ist etwas schwerer:

Wir finden zunächst den Knoten $u$, der den Schlüssel $k$ repräsentiert. Wenn dieser nicht existiert, bleibt nichts zu tun.

Fall 1: $u$ ist ein Blatt, dann reicht es dieses Blatt zu löschen.
`u.parent->lchild = nullptr` bzw. `u.parent->rchild = nullptr`

Fall 2: $u$ hat genau ein Kind
Es reicht, $u$ zu löschen und das Kind von $u$ zum entsprechenden Kind des Elternknotens von $u$ zu machen.

Fall 3: $u$ hat genau zwei Kinder, dann
finden wir den Nachfolger $v$ von $u$, wir merken $v$ hat kein linkes Kind, also höchstens ein Kind. Wir löschen $v$ von dort und speicher $v$ an der Stelle von $u$.


| Funktion           | Laufzeit           |
| ------------------ | ------------------ |
| `S.find(k)`        | $O(h)$ |
| `S.insert(e)`      | $O(h)$ |
| `S.remove(k)`      | $O(h)$ |
| `S.min()`          | $O(h)$       |
| `S.max()`          | :: ::              |
| `S.successor(k)`   | :: ::              |
| `S.predecessor(k)` | :: ::                   |


## Rotationen

![rot](rot.png)

Rotationen erhalten die Binäre Suchbaum Eigenschaft






