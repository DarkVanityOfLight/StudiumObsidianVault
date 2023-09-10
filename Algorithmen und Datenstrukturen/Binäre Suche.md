
Wir koennen einen gegebenen Schlüssel schnell suchen, wenn wir ein sortiertes Array $A[1...n]$ der Schlüssel gegeben haben.

```c
int find(type A[], int l, int r, type key){

	while(l <= r){
		int m = (l+r) /2
		if(A[m] == key){
			return m;
		} else if(A[m] < key){
			l = m+1
		}else{
			r = m-1
		}
	}
	return -1
}

```

Die Laufzeit ist $O(\log n)$

