
Listen können um weitere Elemente erweitert werden.
Dies geht auch bei Arrays.

Wir betrachten dynamische Arrays mit folgenden Operationen
- Auswertung, Zuweisung
- `A.push_back(x)`
- `A.pop_back()`
- `A.size()`

wenn wir ein Array fester Größe $N$ zur Verfügung haben, können wir es benutzen solange `A.size()`$\leq N$. 
Sobald `A.size()`$< N$ wird, müssen wir ein neues Array für mindestens $N+1$ Elemente schaffen. Da dies nicht sehr effizient ist erstellen wir ein Array mit doppelter Größe.

```c
class DynArray{
	private:
		int size;
		int capacity;
		type* A
	public:
		int size() {return size;}
		void push_back(type x){
			if(size == capacity){
				capacity = 2* capacity;
				type* B = new type[capacity];
				copy A[1..size] to B[1..size]
				delete[] A;
				A=B;
			}
			A[size+1] = x;
			size++;
		}
		void pop_back(){
			size--;
			if(4*size <= capacity){
				capacity = capacity/2;
				type* B= new type[capacity];
				copy A[1..size] to B[1..size]
				delete[] A;
				A=B;
			}
		}
}
```


## Armotisierte Analyse


`push_back` und `pop_back` haben armotisiert eine Laufzeit von $O(1)$.

