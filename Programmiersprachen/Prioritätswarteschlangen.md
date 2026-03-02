

Wir betrachten eine Erweiterung von [Queues](Queue.md), die Prioritätswarteschlange(Priority Queue)

Eine Priority Queue speichert eine Menge $M$ an Schlüsseln unter folgenden Operation:

- `PQ.build({e1, ..., en})` initialisiert $M = \lbrace e_1, \dots, e_n\rbrace$
- `PQ.insert(e)` fügt $e$ in $M$ ein d.h.$M \leftarrow M\cup\lbrace e\rbrace$
- `PQ.max()` return $\max M$ 
- `PQ.deleteMax()` löscht $\max M$ d.h. $M\leftarrow M\setminus \lbrace\max M\rbrace$

Wir implementieren Prioritätswarteschlangen als [Heaps](Heaps.md).

```java
class PQ<T>{
	A[C];

	T max(){
		return A[1];
	}

	void insert(T e){
		A.push_back(e);
		i = A.size();
		while(i>1 and A[parent(i)] < A[i]){
			swap(A[i], A[parent(i)]);
			i = parent(i);
		}
	}

	void deleteMax(){
		A[1] = A[size];
		size = size-1;
		siftdown(1);
	}

	void siftDown(int i){
		if(left(i) <= size){
			if(right(i) > size or A[left(i)] >= A[right(i)]){
				m = left(i);
			}else{
				m = right(i);
			}
			if(A[m] > A[i]){
				swap(A[i], A[m]);
				siftDown(m);
			}
		}
	}

	void build(T A[]){
		for(int i = A.size()/2; i >= i; i--){
			siftDown(i);
		}
	}
}
```

Unsere Operationen haben damit folgende Laufzeiten:

| Funktion                  | Laufzeit    |
| ------------------------- | ----------- |
| `PQ.build([e1, ..., en])` | $O(n)$      |
| `PQ.insert(e)`            | $O(\log n)$ |
| `PQ.max()`                | $O(1)$      |
| `PQ.delteMax()`           | $O(\log n)$ |

## Addressierbarkeit

- `PQ.build({e1, ..., en})` initialisiert $M = \lbrace e_1, \dots, e_n\rbrace$
- `PQ.insert(e)` fügt $e$ in $M$ ein d.h.$M \leftarrow M\cup\lbrace e\rbrace$ und gibt Zeiger $h$ auf das eingefügte Element zurück.
- `PQ.max()` return $\max M$ 
- `PQ.deleteMax()` löscht $\max M$ d.h. $M\leftarrow M\setminus \lbrace\max M\rbrace$
- `PQ.remove(h)` löscht das Element aus $M$, auf das der Zeiger $h$ zeigt.
- `PQ.increaseKey(h, k)` vergrößert den Schlüssel des Elements, auf das der Zeiger $h$ zeigt auf Wert $k$
- `PQ.merge(PQ2)` vereinigt Priority Queues PQ und PQ2

