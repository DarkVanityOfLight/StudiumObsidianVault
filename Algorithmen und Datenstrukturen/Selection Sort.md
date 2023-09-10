
> Wir gehen Rundenweise vor, in der $i$. Runde suchen wir das $i$. kleinste Element -> setzen es auf die $i$. Stelle

```python
def selectionSort(A):
	for i in range(len(A)):
		j = selectMinimum(A, i, len(A))
		swap(A[i], A[j])

def selectMinimum(A, a, b):

	tempmin = a
	for i in range(a, b):
		if A[i] < A[tempmin]:
			tempmin = i
	return tempmin
```


## Korrektheit

__Terminierung__:
Trivial da for-Loop

__Schleifeninvariante__
Sei $A'$ die Korrekte Reihenfolge.

Im $j$-ten Durchlauf des For-Loops gilt:

$A[0\dots j] = A'[0\dots j]$

__Induktionsanfang__: 
Gilt Trivial für $j=0$

__Induktionsschritt__:

Die Aussage sei erfüllt für $j-1$.

Im $j$-ten Durchlauf suchen wir das kleinste noch nicht Sortierte Element und stellen es an die Stelle $j$ damit ist die Schleifeninvariante wieder hergestellt.

## Laufzeit

Es gibt Konstanten $c_1, c_2, c_3$ sodass:
$$\begin{align}
T(n) &\leq c_1 + \sum^{n-1}_{i=1} (c_2 + \sum^{n}_{j=1} c_3)\\
&\leq c_1 + \sum^{n}_{i=1} (c_2 + \sum^{n}_{j=1} c_3)\\
&= c_1 + \sum^{n}_{i=1} c_2 + \sum^{n}_{i=1}\sum^n_{j=1} c_3\\
&= c_1 + c_2 n + c_3n^2\\
&\implies T(n) \in O(n^2)
\end{align}$$
