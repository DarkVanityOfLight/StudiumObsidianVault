

Eine Rekursionsgleichung hat die Form

$$T(n) = a \cdot T(\frac{n}{b}) + f(n)$$
## Einfache Form

Es gibt Konstanten $C, D, n_0, a, b, s$ sodass
$$T(n) \leq \begin{cases}C : n \leq n_0\\ a\cdot T(\frac{n}{b}) + Dn^s : n>n_0\end{cases}$$


## Allgemeinere Form


Es gibt Konstanten $C, D, n_0, a, b, e, s$ sodass
$$T(n) \leq \begin{cases}C : n \leq n_0\\ a\cdot T(\lceil\frac{n}{b}\rceil + e) + Dn^s : n>n_0\end{cases}$$

## Beispiel

```python

if n==1 return A[1]

m = n//2

B[:m] = MergeSort(A[1...m])
B[m+1:] = MergeSort(A[m+1:])

return Merge(B[:m], B[m+1:])
```

Es gibt Konstanten $C, D$ sodass

$T(1) = C$
$$\begin{align}
T(n) &\leq T(\frac{n}{2})+ T(\frac{n}{2}) + Dn\\
&\leq 2 \cdot T(\frac{n}{2} + 1) + Dn
\end{align}$$



## Rekurenzgleichung lösen


### Rekursionsbaummethode

Angenommen, wir wissen für eine Laufzeitfunktion $T$, dass es Konstanten $c, d$ gibt sodass

$$
T(n) \leq \begin{cases}
c : n < 4\\
3 T(\frac{n}{4}) + d\cdot n^2 : n \geq 4
\end{cases}
$$

Wiederholtes einsetzen ergibt:


$$\begin{align}
T(n) &\leq 3T(\frac{n}{4}) + dn^2\\
&\leq 3\left(3T\left(\frac{n}{16}\right) + d \left(\frac{n}{4}\right)^2\right) + dn^2\\
&\dots\\
&\leq 3^{\log_4(n)} T(1) + 3^{\log_4(n) -1} \cdot \frac{dn^2}{16^{\log_4(n) -1}} + \dots + 3^2 \cdot \frac{dn^2}{16} + dn^2\\
&= n^{\log_4(3)} T(1) + \sum^{\log_4(n) -1}_{i=0} (\frac{3}{16})^i dn^2 \leq n^{\log_4(3)} c + \left(\sum^\infty_{i=0} \left( \frac{3}{16} \right)^i\right) dn^2\\
&\in O(n^{\log_4(3)} + n^2) =  O(n^2)
\end{align}$$




[Mastertheorem](Mastertheorem.md)