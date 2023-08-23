
![B-adische Entwicklung](B-adische%20Entwicklung.md)

## Kleinste Zahl

Die kleinste Zahl der Basis $B$ mit $n$ Stellen wird erreicht indem wir alle $x_i = 0$ setzen:
$$\text{MinNat}(n) := \langle0, \dots,0\rangle^\mathbb N_B = \sum\limits^{n-1}_{i=0} 0\cdot B^i = 0$$
## Grösste Zahl

Die grösste Zahl mit $n$ Stelen zur Basis $B$ erhalten wir indem wir alle Stellen $x_i = B-1$ setzen

$$\text{MaxNat}(n) := \langle[B-1, \dots, B-1]\rangle^\mathbb N_B = \sum\limits^{n-1}_{i=0}(B-1) \cdot B^i = B^n - 1$$

Daraus folgt das $B-1$ ein Teiler von $B^n -1$ ist.

## Modulo $B^k$

Den Quotient und Rest einer Radix-B Nummer von Exponenten von $B^k$ zu bestimmen ist einfach:
$$\langle[x_{n-1}, \dots, x_0]\rangle^{\mathbb N}_B = \langle[x_{n-1}, \dots, x_k]\rangle^\mathbb N_B \cdot B^k + \langle[x_{k-1},\dots, x_0]\rangle^\mathbb N_B$$

Deshalb gilt:

$$\langle[x_{n-1},\dots,x_0]\rangle^\mathbb N_B \mod B^k = \langle[x_{k-1},\dots, x_0]\rangle^\mathbb N_B$$

## Umwandlung zu Radix-B

Fuer jedes $X = \langle[x_{n-1}, \dots, x_0]\rangle^\mathbb N_B$ kann die Stelle $x_k$ Berechnet werden durch $x_k = (X \div B^k) \mod B$. Es werden mindestens $l_x := \lceil\log_B(X+1)\rceil = \lfloor\log_B(X)\rfloor$+1 Stellen benötigt um $X>0$ darzustellen.

```python

def to_radix_b(zin: int, x: List[nat], B: int) 
-> List[int]:
    N = len(x)
    z = [0] * (N + 1)
    z[0] = zin
    
    for i in range(N):
        x[i] = z[i] % B
        z[i + 1] = z[i] // B
    
    return z

```

## Umwandlung von Radix-B

```python

def Horner(x: List[nat]):
	N = len(x)
	z[N] = [0]

	for(i=0..N):
		z[N-i-1] = z[N-i] * B + x[N-i-1]
```

Bei dieser Berechnung wird die Berechnung des Exponenten $B^i$ vermieden.



---

- Jede Natürliche Zahl kann durch eine Radix-B Zahl dargestellt werden. 
- Dafür werden mindestens $l+x := \lceil\log_B(x+1)\rceil$ Stellen benötigt wenn $x >0$.
- Für jedes Festes $l \geq l_x$, ist die Zahlendarstellung $\langle[x_{l-1}, \dots, x_0]\rangle^{\mathbb N}_B$ von $x$ Eindeutig bestimmt.
- Wenn $l_x$ die geringste Anzahl an Stellen ist die Benötigt werden um $x$ darzustellen dann gilt für alle $l \geq l_x$ $$x = \langle[x_{l-1}, \dots, x_0]\rangle^\mathbb N_B \iff \forall i \geq l: x_i = (x \div B^i)\mod B$$
## Addition

$$\langle[s_n, \dots, s_0]\rangle^\mathbb N_B = \langle[x_n, \dots, x_0]\rangle^\mathbb N_B + \langle[y_n, \dots, y_0]\rangle^\mathbb N_B$$

```python

def nat_add(x: List[int], y: List[int],
			s: List[int], B: int):

    N = len(x)
    c = [0] * (N + 1)
    c[0] = 0
    
    for i in range(N):
        sm = x[i] + y[i] + c[i]
        c[i + 1] = sm // B
        s[i] = sm % B
    
    s[N] = c[N]

```

Dieser Algorithmus Addiert die Stellen $x[i], y[i]$ und den Übertrag der letzten Addition.

## Subtraktion 

$$\langle[s_n, \dots, s_0]\rangle^\mathbb N_B = \langle[x_n, \dots, x_0]\rangle^\mathbb N_B - \langle[y_n, \dots, y_0]\rangle^\mathbb N_B$$

```python

def nat_sub(x: List[int], y: List[int],
			s: List[int], B: int):

    N = len(x)
    c = [0] * (N + 1)
    c[0] = 0
    
    for i in range(N):
        sm = x[i] - (y[i] + c[i])
        c[i + 1] = -(sm // B)
        s[i] = sm % B
    
    s[N] = c[N]
```

Wir merken das die Summe Negativ sein kann.

![Subtraktion durch Addition](B-Komplement.md#Subtraktion%20durch%20Addition)

## Vergleich


!????
```python

def nat_cmp(x: List[int], y: List[int]) -> Tuple[bool, bool]:
    N = len(x)
    ls = [False] * (N + 1)
    eq = [True] * (N + 1)
    
    ls[N] = False
    eq[N] = True
    
    for i in range(N):
        ls[i] = ls[i + 1] or (eq[i + 1] and x[i] < y[i])
        eq[i] = eq[i + 1] and x[i] == y[i]
    
    les = ls[0]
    eqq = eq[0]
    
    return les, eqq

```

## Multiplikation

Wir Multiplizieren in zwei Schritten:
- Generiere Teilprodukte
- Summiere die Teilprodukte

$$x\cdot y = x \cdot \sum\limits^{n-1}_{j=0} y_j \cdot B^i = \sum\limits^{n-1}_{j=0} x \cdot y_j \cdot B^i = \sum\limits^{m-1}_{i=0}\sum\limits^{n-1}_{j=0} x_i \cdot y_i \cdot B^{i+j}$$

Die Partialprodukte $x_i \cdot y_i$ müssen mit einem Gewicht $B^{i+j}$ aufsummiert werden.

```python
from typing import List

def nat_mul_cra(x: List[int], y: List[int], p: List[int]) -> None:
    B = len(x)
    M = len(x)
    N = len(y)
    sm: List[List[int]] = [[0] * N for _ in range(M)]
    c: int = 0
    
    for j in range(N):
        c = 0
        for i in range(M):
            sm[i][j] = x[i] * y[j] + p[i + j] + c
            c = sm[i][j] // B
            p[i + j] = sm[i][j] % B
        p[M + j] = c
```


![carryripplemultradixb](carryripplemultradixb.png)


## Division

Sei $x$ und $y$ gegeben und wir suchen $q$ und $r$ mit:

$$\langle X\rangle^\mathbb N_B = \langle q \rangle^\mathbb N_B \cdot \langle y \rangle^\mathbb N_B + \langle r \rangle^\mathbb N_B$$ mit $\langle r \rangle^\mathbb N_B < \langle y \rangle^\mathbb N_B$, wir vernachlässigen $\langle y \rangle^\mathbb N_B = 0$.

Die Idee ist(wenn wir $r$ und $q$ bereits haben):
$$r = x-y\cdot q = x - \sum\limits^{m-1}_{i=0} (y \cdot q_i) \cdot B^i$$

Wir subtrahieren die Partialprodukte $y \cdot q_i$ von der rechten Quotienten Stelle $q_i$
Rechts bedeutet das $q_i$ die Maximale Stelle ist die einen Positiven Rest $r$ zurücklasst.

Wir berechnen nacheinander:
$$x^{(i)} = x - \sum\limits^{m-1}_{j=1} (y \cdot q_j) \cdot B^j$$
$$x^{(i-1)} = x^{(i)} - y \cdot q_{i-1} \cdot B^{i-1}$$


```python
from typing import Optional, List

def nat_div_mod_algo(x: int, y: int, r: Optional[int], q: List[int]) -> None:
    B = 10  # Assuming B is 10 based on the provided code
    M = len(q)
    
    r = x  # r := x (m )
    
    for j in range(M):
        i = M - 1 - j
        
        # find maximum q[i] with r >= q[i] * y * B^i
        q[i] = B - 1
        while r < q[i] * y * (B ** i):
            q[i] -= 1
        
        # compute x(i - 1) = x(i) - q[i] * y * B^i
        r = r - q[i] * y * (B ** i)
```

für alle Indexe $i \in M-1,\dots, 0$ wird folgendes getan:
- Wir Versuchen die Stellen $B-1, B-2, \dots,$ für $q[i]$ bist die Maximale Stelle $q[i]$ gefunden wurde wobei gilt $r \geq q[i] \cdot y \cdot B^i$
- Mindestens die Stelle $q[i]=0$  wird dies erfüllen.
- Mit dieser Stelle $q[i]$: Wir Subtrahieren $q[i] \cdot y \cdot B^i$ von $r$

Um $q_{i-1}$ zu bestimmen beginnen wir mit $0$
### Non-Performing

- Erhöhe $q_{i-1}$ bis $x^{i} \geq q_{i-1} \cdot y \cdot B^{i-1}$
- Verringere $q_{i-1}$ bis $x^{(i)} < q_{i-1} \cdot y \cdot B^{i-1}$ gilt für maximale $q_{i-1}$
- Subtrahiere $x^{i-1} := x^{(i)} - q_{i-1} \cdot y \cdot B^{i-1}$

### Restoring

- Subtrahiere $x^{(i-1)} := x^{i} - y \cdot B^{i-1}$ und erhöhe $q_{i-1}$ bis $x^{(i-1)}$ negativ wird
- Wenn $x^{i-1}$ negativ wird, verringere $q_{i-1}$ und stelle $x^{(i-1)} := x^{(i)} + y \cdot B^{i-1}$ wieder her

```python
from typing import List

def nat_div_mod_rst(x: int, y: int, r: int,
					M: int, q: List[int]):
    i: int
    r = x
    for j in range(M):
        i = M - 1 - j
        while r >= 0:
            q[i] = q[i] + 1
            r = r - y * B ** i  
        # Restoring step
        q[i] = q[i] - 1
        r = r + y * B ** i  


```

## Nonrestoring

- Subtrahiere $ := x^{i} -y \cdot B^{i-1}$ und erhoehe $q_{i-1}$ bis $x^{i-1}$ negativ wird
- Sobald $x^{(i-1)}$ negativ wird, verringer $q_{i-1}$ aber stelle $x^{(i-1)}$ nicht wieder her

Wir sollten $x^{(i-1)} := x^{(i)} - q_{i-1} \cdot y \cdot B^{i-1}$ berechnen, wir haben aber 
$v^{(i-1)} = x^{(i)} - (q_{i-1} + 1) \cdot y \cdot B^{i-1}$
$x^{(i-1)} = v^{(i-1)} + y \cdot B^{i-1}$ berechnet. Wir korrigieren indem wir $y \cdot B^{(i-1)}$ addieren:
$$\begin{align}
x^{(i-2)} &= x^{(i-1)} - q_{i-2} \cdot y \cdot B^{i-2}\\
&= v^{(i-1)} + (B-q_{i-2}) \cdot y \cdot B^{i-2}
\end{align}$$

Anstatt $y$ zu subtrahieren addieren wir $(B-1) \cdot y$

```python

def nat_div_mod_nrt(x: int, y: int,
					r: int, M: int, q: List[int]):
    i: int
    r = x
    for j in range(M):
        i = M - 1 - j
        if r < 0:
            q[i] = q[i] + 1
            r = r + (B - 1) * y * B ** i  
        while r >= 0:
            q[i] = q[i] + 1
            r = r - y * B ** i  
        q[i] = q[i] - 1
        

```