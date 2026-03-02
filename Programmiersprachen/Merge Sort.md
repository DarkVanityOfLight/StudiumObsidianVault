
> Wir teilen das Problem in Teilprobleme und kombinieren die Teillösungen zu einer Gesamtloesung

```python
def merge(A, B):
	i, j = 1, 1
	C = []
	for k in ranger(n+m):
		if j == m+1 or i <= n and A[i] <= A[j]:
			C[k] = A[i]
		else:
			C[k] = B[j]
			j = j+1
	return C
```

Wir Mergen zwei Sortierte Arrays zu einem grösseren.


```python
def MergeSort(A):
	if len(A) == 1:
		return A[0]

	m = n//2
	B = MergeSort(A[:m])
	C = MergeSort(A[m:])
	return Merge(B, C)
```

## Korrektheit

### Merge
Am Ende jeder for-Schleife gilt:
$C[1] \leq \dots \leq C[k]$ ist sortierte Reihenfolge von $A[1\dots i-1], B[1\dots j-1]$ und kein Element in $A[i\dots n], B[j\dots m]$ ist kleiner als $C[k]$
-> Am Ende ist $C[1], \dots, C[n+m]$ die gewünschte sortierte Reihenfolge von $A$ und $B$.

Nach dem ersten Schleifendurchlauf gilt die Schleifeninvariante:
$C[1]$ ist die sortierte Reihenfolge von $A[1..i-1], B[1..j-1]$
kein Element in $A[i..n], B[j..n]$ ist kleiner als $C[1]$

## Laufzeit

$$\Theta(n \log n)$$

