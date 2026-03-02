
> Wir vertauschen falsch sortierte Nachbarn solange bis die Liste sortiert ist.

```python

def bubbleSort(A):
	done = False

	while not done:
		done = True
		for i in range(len(A)):
			if A[i] > A[i+1]:
				swap(A[i], A[i+1])
				done = False
	return A

def swap(A[i], A[j]):
	x = A[i]
	A[i] = A[j]
	A[j] = A[i]
```

## Korrektheit

Sei $A'$ die sortierte Reihenfolge

Nach dem $j$-ten Durchlauf der while-Schleife gilt:
$A[k] = A'[k] \forall k\in\lbrace n-j + 1, \dots, n \rbrace$

__Induktionsanfang__:

Die Aussage gilt trivial für $j=0$.

__Induktionsschritt__:

Die Aussage sei erfüllt für $j-1$.
Im $j$-ten Durchlauf der Schleife passiert folgendes:

1. Wenn $A[n-j+1] \not = A'[n-j+ 1]$ dann:
	sobald $i$ so ist, dass $A[i] = A'[n-j+1]$
	dann vertauschen wir immer Nachbarn bis $i=n-j+1 \to A[n-j+1] = A'[n-j+1]$ ab dann gilt:
	$A[n-j+1] \leq A[n-j+2] \leq \dots A[n]$

2. Wenn $A[n-j + 1] = A'[n-j + 1]$, dann:
	wir vertauschen nichts ab $i=n-j+1$

-> Die Aussage gilt am Ende der $j$-ten Schleife.

__Terminierung__:

Spätestens nach dem $n+1$-sten Schleifendurchlauf behält $done=true$.

__Korrektheit__:
Das Ergebnis ist dann die Sortierte Permutation des Eingabearrays.

## Laufzeit

Es gibt maximal $\leq n+1$ Iterationen der While-Schleife

Es sei $T(n)$ die Worst-Case-Laufzeit von Bubble Sort

1. Ein Durchlauf des If-Blocks benötigt $\leq c_1$ Schritte für eine Konstante $c_1$

2. Die For-Schleife benötigt höchstens $c_2 + \sum^{n-1}_{i=1} c_1 = c_2 + (n-1)c_1$ Schritte für eine Konstante $c_2$

3. Ein Durchlauf der While-Schleife benötigt höchstens $c_3 + (n-1)c_1 \leq c_3 + nc_1$ Schritte für eine Konstante $c_3$.

4. Aus dem Fakt folgt: $$T(n) \leq c_4 + (n+1)(c_3 + nc_1)$$ für eine Konstante $c_4$.

$$\begin{align}
T(n) &\leq c_4 + (n+1)(c_3 + nc_1)\\
&=  (c_4 + c_3) + n \cdot (c_3 + c_1) + n^2 \cdot c_1\\
&\implies T(n) \in O(n^2)
\end{align}$$

