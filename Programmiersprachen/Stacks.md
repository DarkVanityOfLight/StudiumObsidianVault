
Ein Stack $S$ repräsentiert eine Folge $(a_1, \dots, a_n)$, wir haben aber nur eingeschränkte Zugriffsmöglichkeiten.

- `S.last()` gibt das letzte Element der Folge in $O(1)$ zurück
- `S.push_back(x)` fügt $x$ an das Ende der Folge in $O(1)$ ein
- `S.pop_back(x)` löscht das letzte Element der Folge in $O(1)$

Wir können Stacks als [Dynamisches Array](Dynamisches%20Array.md) oder als [Verkettete Listen](Verkettete%20Listen.md) implementieren.

## Als Array
```c

class Queue{
	type A[C];
	int head;
	int tail;

	type front() {
		if (head==tail){
			error: Schlange ist leer!
		}
		return A[head]
	}

	void push_back(type x){
		if (head==tail+1) or (head==1 and tail==C){
			error: Queue hat Kapzitaetsgrenze ueberschritten
		}
		A[tail] = x;
		if(tail == C){
			tail = 1;
		} else {
			tail = tail+1;
		}
	}

	void pop_front(){
		if(head==tail){
			error: Schlange ist leer!
		}
		if (head == C){
			head = 1;
		}else{
			head = head+1
		}
	}
}
```






