
> Wir bestimmen ein Pivotelement $p$ und teilen das Problem in zwei Teile in einem sind alle Elemente $\leq p$ im anderen sind alle Elemente $\geq p$
> Wir sortieren diese Teile getrennt voneinander
> Wir fügen das Ergebnis zusammen


```python
def QuickSort(A, l, r):
	if l < r:
		q = Partition(A, l, r)

		QuickSort(A, l, q-1)
		QuickSort(A, q+1, r)
```

## Korrektheit

Induktion über $r-l$

Quicksort permutiert die Elemente in $A[l...r]$ sodass:

$$A[l] \leq \dots\leq A[q-1] \leq A[q] \leq A[q+1] \leq \dots \leq A[r]$$



## Partition

```python
def Partition(A, l, r):
	k = pickPivot(A, l, r)
	p = A[k]
	swap(A[k], A[r])

	s = l
	for i in range(l, r-1):
		if A[i] <= p :
			swap(A[i], A[s])
			s = s+1
	swap(A[s], A[r])

	return s
```

Die Ausgabe ist ein Index $l \leq q \leq r$ sodass:
- Alle Elemente in $A[l...q-1]$ sind höchstens $A[q]$
- Alle Elemente in $A[q+1...r]$ sind mindestens $A[q]$


## Uniform Zufälliges Pivot

Die erwartete Laufzeit von Quicksort mit uniform zufälligem Pivot ist in $O(n\log n)$.

## Beliebiges Festes Pivot

Laufzeit $\Theta(n^2)$

## Median und das Auswahlproblem

>[!IMPORTANT] Median
> Für eine Folge $(a_1, \dots, a_n)$ heißt $a$ ein Median der Folge, wenn 
> $|\lbrace 1\leq i\leq n | a_i \leq a\rbrace| \geq \lceil\frac{n}{2}\rceil$, sowie
> $|\lbrace 1 \leq i \leq n | a_i \geq a \rbrace| \geq \lceil\frac{n}{2}\rceil$

Wir können den Median einer Folge durch sortieren in $O(n \log n)$ lösen, es geht aber auch $O(n)$

```python
def QuickSelect(A, l, r, k):

	if l<r:
		q = Partition(A, l, r)
		L = q - l + 1
		if k < L:
			return QuickSelect(A, l, q-1, k)
		elif k > L:
			return QuickSelect(A, q+1, r, k-L)
		else:
			return A[q]
```

Quickselect mit uniform zufälligen Pivotelement ist ein [[Las-Vegas-Algorithmus]] für Rangselektion mit erwarteter Laufzeit $O(n)$.

Dies geht auch Deterministisch, da auch der Approximative Median genügt.

>[!IMPORTANT] Median der Mediane
> Teile die Elemente in 5er Gruppen auf.
> Bestimme den Median $x_i$ der $i$-ten 5er-Gruppe
> Bestimme $x$ als Median von $x_1, \dots, x_m$

```python
def pickPivot(A, l, r)
	n = r-l+1
	m = n//5
	# M = [] * m
	for i in range(m):
		M[i] = MedianOfFive(A[l+5i -4:l+5i])

	return QuickSelect(M, 1, m, m//2)
```

