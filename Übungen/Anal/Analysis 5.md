
## Aufgabe 1

### b)
Wir setzen die n-te Stelle auf $1$ für alle n in der Gegebenen Teilmenge.
$$\begin{align}
f: \ & \{0, 1\}^\infty \to P(\mathbb N)\\
&f(x) \mapsto \{n \in \mathbb N|\text{die n-te Stelle $x_n$ ist 1} \}
\end{align}$$
### c)
Da ich mit $\mathbb N$ stellen in Binär mehr Zahlen darstellen kann als $\mathbb N$, muss mindestens eine Zahl auf das selbe abgebildet werden und damit ist die Funktion nicht mehr injektiv

## Aufgabe 2

1. Wir nehmen 0
2. Wir bilden Tupel aus  "Zähler" "Nenner":
3. Erhöhe den Nenner um 1
4. Erhöhe den Zähler um 1
5. Falls Zähler = Nenner gehe zu 3 sonst:
6. Ignoriere das Tupel wenn es in gekürzter Form schon dasteht und gehe zu 4, sonst:
7. Kopiere das Tupel mit Negativem Nenner($\cdot -1$)
8. Gehe zu 4.

$$\begin{align}
&0; (1, 1); (1, -1); (1, 2); (1, -2); (1, 3); (1, -3);\\
&(2, 3);(2, -3); (1, 4); (1, -4) (3, 4); (3, -4); (1; 5);\\
&(1, -5); (2, 5); (2, -5); (3, 5); (3, -5); (4, 5); (4, -5)\\
\end{align}$$


## Aufgabe 3

$m = 1$
$N  = 1$
---
$m = 10$
$N = 13$
---
$m = 100$
$N = 125$


## Aufgabe 4

### a)


$$\begin{align}
&5.491 - 5 \cdot 10^{k - 2 -1} < rd_2(5.491) \leq 5.491 + 5 \cdot  10^{k-2-1}\\
&5.491 - 5 \cdot 10^{0 - 2 -1} < rd_2(5.491) \leq 5.491 + 5 \cdot  10^{0-2-1}\\
&5.486 < rd_2(5.491) \leq 5.496\\
&5.486 < 5.49 \leq 5.496
\end{align}$$
---


$$\begin{align}
&5.495 - 5 \cdot 10^{k - 2 -1} < rd_2(5.495) \leq 5.495 + 5 \cdot  10^{k-2-1}\\
&5.495 - 5 \cdot 10^{0 - 2 -1} < rd_2(5.495) \leq 5.495 + 5 \cdot  10^{0-2-1}\\
&5.485 < rd_2(5.495) \leq 5.5\\
&5.485 < 5.5 \leq 5.5
\end{align}$$
---
$$\begin{align}
&99.96 - 5 \cdot 10^{k - 2 -1} < rd_2(99.96) \leq 99.96 + 5 \cdot  10^{k-2-1}\\
&99.96 - 5 \cdot 10^{1 - 2 -1} < rd_2(99.96) \leq 99.96 + 5 \cdot  10^{1-2-1}\\
&99.91 < rd_2(99.96) \leq 100.1\\
&9.91 \cdot 10^1 < rd_2(9.996\cdot 10^1) \leq 1.001 \cdot 10^2\\
&9.91 \cdot 10^1 < 1 \cdot 10^2 \leq 1.001 \cdot 10^2
\end{align}$$

### b)

$$\begin{align}
&rd_4(rd_4(1.0002 \cdot 10^{-2} + 9.0003 \cdot 10^{-2})+ 7.0001^{-2}) \\
&\not= rd_4(1.0002\cdot10^{-2} + rd_4(9.0003 \cdot 10^{-2} + 7.0001\cdot 10^{-2}))\\
&rd_4(rd_4(1.0005 \cdot 10^{-1}) + 7.0001\cdot 10^{-2}) \not = rd_4(1.0002 \cdot 10^{-2} + rd_4(1.60004\cdot 10^{-1}))\\
&rd_4(1.001 \cdot10^{-1} + 7.0001 \cdot 10^{-2}) \not = rd_4(1.0002 \cdot 10^{-2} +  1.6\cdot 10^{-1})\\
&rd_4(1.70101 \cdot 10^{-1}) \not = rd_4(1.70002 \cdot 10^{-1})\\
&1.701\cdot 10^{-1} \not = 1.700 \cdot 10^{-1}
\end{align}$$



## Aufgabe 5
```csharp
let floatingPointAddition(x: float, y: float) = x+y
```

