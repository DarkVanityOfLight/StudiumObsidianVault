
Eine Queue $Q$ repräsentiert eine Folge $a_1,\dots ,a_n$. Wir haben nur eingeschränkte Zugriffsmöglichkeiten.

- `Q.first()` Gibt das erste Element der Folge in $O(1)$ zurück
- `Q.psuh_back(x)` Fügt an das Ende der Folge ein in $O(1)$
- `Q.pop_front()` Löscht das erste Element der Folge in $O(1)$

Eine Queue Funktioniert nach dem First In, First Out Prinzip(FIFO)


Queues können als [Doubly Linked Lists](Doubly%20Linked%20List.md), [Verkettete Listen](Verkettete%20Listen.md) oder als [Array](Array.md) dargestellt werden(angenommen wir haben eine Kapazitaetsgrenze $C$).

## Implementierung als Arrays

```Java
class Queue<T> {
	T A[C];
	int head;
	int tail;

	T front(){
		if (head==tail){
			throw "Schlange ist leer!"
		}
		return A[head]
	}

	void push_back(type x){
		if (head == tail+1 or (head==1 and tail==C)){
			throw "Queue ist voll"
		}

		A[tail] = x;
		if (tail == C){
			tail = 1;
		}else{
			tail = tail+1;
		}
	}

}
```
