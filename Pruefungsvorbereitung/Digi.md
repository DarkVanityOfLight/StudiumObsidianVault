
## Wahrscheinlichkeit eines Worts

$$P(a_1\dots a_k) = \prod^k_{j=1} P(a_j)$$

## Erwartete Länge eines Wortes

$$|\epsilon(\alpha)| = \sum^k_{i=1} |\epsilon(a_i)| = \sum^n_{i=1} n_i |\epsilon(\sigma_i)|$$

Durchschnittlich haben wir $P(\sigma_i) = \frac{n_i}{k}$, deshalb 
$$|\epsilon(\alpha)| = k \cdot \sum^n_{i=1} P(\sigma_i) \cdot |\epsilon(\sigma_i)|$$

## Gewichteter Code längen Durchschnitt

$$Size(P, \epsilon) := \sum^n_{i=1} P(\sigma_i) \cdot |\epsilon(\sigma_i)|$$

## Entropy eines Alphabets

$$H(\Sigma, P) := - \sum^n_{i=1} P(\sigma_i) \cdot \log_2(P(\sigma_i))$$

## Shannon's Quellcode Theorem

$$H(\Sigma, P) \leq \sum^n_{i=1} P(\sigma_i) \cdot |\epsilon(\sigma_i)| = Size(P, \epsilon)$$
$$H(\Sigma, P) = Size(P, \epsilon) \iff  |\epsilon(\sigma_i)| = - \log_2(P(\sigma_i)) \forall \sigma_i \in \Sigma$$

$$
\sum^n_{i=1} P(\sigma_i) \cdot |\hat\epsilon(\sigma_i)| < H(\Sigma, P) + 1
$$
## Kraft's Ungleichheit

$$
\sum^n_{i=1} \left(\frac{1}{2}\right)^{|\epsilon(\sigma_i)|} \leq 1
$$

## Gibb's Ungleichheit

$$-\sum^{n}_{i=1} P_1(\sigma_i) \log_2(P_1(\sigma_i)) \leq - \sum^n_{i=1} P_1(\sigma_i) \log_2(P_2(\sigma_i))$$



## Arithmetisches Encoding

Das arithmetische Encoding ist ein leistungsstarkes Verfahren zur Datenkompression, das auf Wahrscheinlichkeiten und Intervallarithmetik basiert. Es bietet eine hohe Kompressionsrate und wird in Kombination mit anderen Kompressionsverfahren verwendet, um optimale Ergebnisse zu erzielen. Dieses Verfahren erfordert jedoch sorgfältige Beachtung bei der Behandlung von Rundungsfehlern und Genauigkeitsproblemen.

Das Verfahren des arithmetischen Encodings besteht aus den folgenden Schritten:

1. **Berechnung der kumulativen Wahrscheinlichkeiten:** Wir berechnen die kumulativen Wahrscheinlichkeiten $P(s_i)$ für jedes Zeichen $s_i$ in der Zeichenfolge. Dies kann durch die Formel $P(s_i) = \sum_{j=1}^{i} p(s_j)$ erreicht werden.

2. **Berechnung des Intervalls:** Wir repräsentieren die gesamte Zeichenfolge durch ein Intervall $[L, H)$, wobei $L = 0$ und $H = 1$ zu Beginn. Für jedes Zeichen $s_i$ in der Zeichenfolge passen wir das Intervall wie folgt an:
   
   - $L' = L + (H - L) \cdot P(s_i)$
   - $H' = L + (H - L) \cdot P(s_{i+1})$

3. **Skalierung:** Um eine genauere Repräsentation zu erhalten, skalieren wir das Intervall, sodass es den Bereich $[0, 1)$ abdeckt. Dies wird erreicht, indem wir die Werte von $L$ und $H$ verschieben und skalieren.

4. **Ausgabe des encodierten Werts:** Der encodierte Wert ist eine Dezimalzahl im Intervall $[0, 1)$, die durch das Intervall $[L, H)$ repräsentiert wird. Diese Dezimalzahl wird in eine binäre Zeichenfolge umgewandelt und als komprimierte Ausgabe gespeichert.

## Huffman

Gegeben ist ein Alphabet $\Sigma = \lbrace \sigma_{1}, \dots, \sigma_{n} \rbrace$ mit den Wahrscheinlichkeiten $P(\sigma_{i})$. Wir sortieren das Alphabet und fügen die beiden kleinsten Wahrscheinlichkeiten zusammen in einen Baum. Diesen Schritt wiederholen wir bis es nur noch einen Baum gibt.

## Shannon-Fano

Gegeben ist ein Alphabet $\Sigma = \lbrace \sigma_{1}, \dots, \sigma_{n} \rbrace$ mit den Wahrscheinlichkeiten $P(\sigma_{i})$.
Wir sortieren das Alphabet nach den Wahrscheinlichkeiten, dann teilen wir das Alphabet sodass die Wahrscheinlichkeit auf beiden Seiten ungefähr gleich ist. Diesen Vorgang wiederholen wir und übertragen ihn in eine Baumstruktur.

## Hamming Distanz

>[!NOTE] Die Hamming Distanz ist also gleich der Anzahl an Bits die die Zwei Wörter voneinander unterscheiden

## Levenshtein Distanz

Die Levenshtein Distanz $\Delta_{L}(\alpha, \beta)$ ist die kleinste Anzahl an Operationen die Benötigt sind um $\alpha$ in $\beta$ zu Transformieren. Eine Operation ist __insertion__, __deletion__ oder __substitution__ eines Einzelnen Buchstabens.

## Fibonacci Codes

![fib](fib.png)

## Regeln für die Priorität
$$\iff \prec \implies \prec \lor \prec \oplus \prec \land \prec \neg$$

## Größe

$\text{Size}(x) := 0$
$\text{Size}(\neg A) := 1 + \text{Size}(A)$
$\text{Size}(A\land B) = 1 + \text{Size}(A) + \text{Size(B)}$
$\text{Size}(A \lor B) := 1 + \text{Size}(A) + \text{Size}(B)$

## Tiefe

$\text{Depth}(x):= 0$
$\text{Depth}(\neg A) := 1 + \text{Depth}(A)$
$\text{Depth}(A \land B) := 1 + \max\lbrace \text{Depth}(A), \text{Depth}(B)\rbrace$
$\text{Depth}(A \lor B) := 1 + \max\lbrace \text{Depth}(A), \text{Depth}(B)\rbrace$


## Operator Basen

### $\barwedge$

$$\begin{align}
\neg \varphi \iff \varphi \barwedge \varphi\\
\varphi \land \uppsi \iff (\varphi \barwedge\varphi)\barwedge(\varphi\barwedge\uppsi)\\
\varphi\lor\uppsi \iff (\varphi\barwedge)\barwedge(\uppsi \barwedge \uppsi)
\end{align}$$


### $(\implies | )$
$$\begin{align}
\neg\varphi \iff (\varphi \implies 0|1)\\
\varphi\lor\uppsi \iff (\varphi \implies 1 | \uppsi)\\
\varphi \land \uppsi\iff(\varphi \implies\uppsi | 0)
\end{align}$$

## BDDs

Es gibt zwei Regeln um einen OBDD in einen ROBDD umzuwandeln:

- Eliminierung: Falls $\mathbf{high}(v) = \mathbf{low}(v)$ gilt, dann lösche $v$ und verbinde alle Kanten nach $v$ nach $\mathbf{high}(v)$
- Isomorphi: Falls $\mathbf{label}(v) = \mathbf{label}(v')$ und $\mathbf{low}(v) = \mathbf{low}(v')$ gilt, loesche $v'$ und Verbinde alle kannten nach $v'$ neu nach $v$.


```python
def Ops(v, m):
	x = label(v)
	if m == D(x):
		return (low(v), high(v))
	else
		return (v, v)
```

```python
def Apply(op, a, b):
	if isLeaf(a) and isLeaf(b):
		return Eval(ops, label(a), label(b))
	else
		m = max(D(label(a)), D(label(b)))
		(a0, a1) = Ops(a, m)
		(b0, b1) = Ops(b, m)
		h = Apply(op, a1, b1)
		l = Apply(op, a0, b0)
		return CreateNode(m, h, l)
```

```python
def ITE(i, j, k):
	if i == BDD(0):
		return k
	elif i == BDD(1)
		return j
	elif j==k
		return k
	else:
		m = max(D(label(i)), D(label(j)), D(label(k)))
		(io, i1) = Ops(i, m)
		(j0, j1) = Ops(j, m)
		(k0, k1) = Ops(k, m)
		l = ITE(i0, j0, k0)
		h = ITE(i1, j1, k1)
		return CreateNode(m, h, l)
```

```python
def Compose(x, a, b)
	if D(x) > D(label(b)):
		return b
	elif x == label(b):
		return ITE(a, high(b), low(b))
	else
		m = max(D(label(b)), D(label(a)))
		(a0, a1) = Ops(a, m)
		(b0, b1) = Ops(b, m)
		h = Compose(x, a1, b1)
		l = Compose(x, a0, b0)
		return CreateNode(m, h, l)
```

$$\exists x.\varphi := [\varphi]^1_x \lor [\varphi]^0_x$$
(Disjunktion der Kofaktoren)

```python
def Exists(e, p):
	if isLeaf(p) or isLeaf(e):
		return p
	# Label(e) does not occur in p
	elif D(label(e)) > D(label(p)):
		return Exists(high(e), p)
	# We are at the root e == p
	elif label(e) == label(p):
		h = Exists(high(e), high(p))
		l = Exists(high(e), low(p))
		return Apply(OR, h, l)
	# D(label(e)) < D(label(p))
	else:
		h = Exists(e, high(p))
		l = Exists(e, low(p))
		return CreateNode(label(p), h, l)
```

$$\forall x.\varphi := [\varphi]^1_x \land [\varphi]^0_x$$

```python
def Forall(e, p):
	if isLeaf(p) or isLeaf(e):
		return p
	elif D(label(e)) > D(label(p)):
		return Forall(high(e), p)
	elif label(e) == label(p):
		h = Forall(high(e), high(p))
		l = Forall(high(e), low(p))
		return Apply(AND, h, l)
	else:
		h = Forall(e, high(p))
		l = Forall(e, low(p))
		return CreateNode(label(p), h, l)
```

```python
def Constrain(b, p):
	if b == BDD(0):
		return BDD(0)
	elif b in (BDD(0), BDD(1)) or (b == BDD(1)):
		return p
	else:
		m = max(D(label(b)), D(label(p)))
		(p0, p1) = Ops(p, m)
		(b0, b1) = Ops(b, m)
		if b0 == BDD(0):
			return Constrain(b1, p1)
		elif b1 == BDD(0):
			return Constrain(b0, p0)
		else:
			l = Constrain(b0, p0)
			h = Constrain(b1, p1)
			return CreateNode(m, h, l)
```

```python
def Restrict(b, p):
	if b == BDD(0):
		return BDD(0)
	elif p in (BDD(0), BDD(1)) or (b == BDD(1)):
		return p
	else:
		m = max(D(label(b)), D(label(p)))
		(p0, p1) = Ops(p, m)
		(b0, b1) = Ops(b, m)
		if b0 == BDD(0):
			return Restrict(b1, p1)
		elif b1 == BDD(0)
			return Restrict(b0, p0)
		elif m == label(p)
			return CreateNode(m,
					Restrict(b1, p1), Resitrict(b0, p0))
		else
			return Restrict(Apply(OR, b0, b1), p)
```


## Radix-B Division

```python
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


```python
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

## B-Komplement

Für $B=2b >1$ definieren wir:

$$\langle[x_{n-1}]\rangle^\mathbb Z_B := \langle[\alpha(x_{n-1}), x_{n-2},\dots, x_0]\rangle^\mathbb N_B = \alpha(x_{n-1}) \cdot B^{n-1} + \sum\limits^{n-2}_{i=0} x_i \cdot B^i$$

mit 

$$\alpha := \begin{cases}x : \text{ if } x < b\\x-B : \text{ if } x\geq b\end{cases}$$
$$\gamma(x) := \begin{cases}x : \text{ if } x \geq b\\x+B : \text{ if } x< b\end{cases}$$

für Radix-B Zahlen werden die Zahlen aus $nat\lbrace B\rbrace = \lbrace 0, \dots, B-1\rbrace$ genommen, bei B-Komplement, ist dies auch so nur die erste Linke Zahl wird als $int\lbrace b \rbrace = \lbrace-b, \dots, b-1 \rbrace$

### Addition

```python
def int_add(x: List[int], y: List[int], s: List[int]):
    N = len(x)
    c = [0] * (N + 1)  # carry digits
    c[0] = 0
    for i in range(N - 1):
        sm = x[i] + y[i] + c[i]
        c[i + 1] = sm // B  
        s[i] = sm % B  

	# most significant digits
	# require alpha / gamma applications
    sm = alpha(x[N - 1]) + alpha(y[N - 1]) + c[N - 1]
    s[N - 1] = sm % B 
    s[N] = gamma(sm // B)
```

## Subtraktion

```python
def IntSub(x: List[int], y: List[int], s: List[int]) -> None:
    N = len(x)
    c = [0] * (N + 1)  # carry digits
    c[0] = 0

    for i in range(N - 1):
        sm = x[i] - (y[i] + c[i])
        c[i + 1] = -(sm // 2)
        s[i] = sm % 2

    # Most significant digits require alpha/gamma applications
    sm = alpha(x[N - 1]) - (alpha(y[N - 1]) + c[N - 1])
    s[N - 1] = sm % 2
    s[N] = gamma(sm // 2)
```

## Multiplikation

![bmult](bmult.png)


```python
def IntMulCRA(x: List[int], y: List[int], p: List[int]) -> None:
    B = 2  # Assuming base B is 2
    M = len(x)
    N = len(y)
    
    for j in range(N):
        c = 0
        for i in range(M):
            xin = alpha(x[i]) if i == M - 1 else x[i]
            yin = alpha(y[j]) if j == N - 1 else y[j]
            pin = alpha(p[i + j]) if i == M - 1 else p[i + j]
            sm = xin * yin + pin + c
            p[i + j] = sm % B
            c = sm // B
        p[M + j] = gamma(c)

```

## Schaltungen

![all](all.png)


```perl
circuit NatMulCRA (
	[ x0 , x1 , x2 ],
	[ y0 ,y1 , y2 ],
	[ w0 ,w9 , w15 , w17 , w19 ,w20 ])
  {
	// compute products of digits
	w2 = AND ( x2 , y0 ) ;
	w1 = AND ( x1 , y0 );
	w0 = AND (x0 , y0 ) ;
	w5 = AND ( x2 , y1 ) ;
	w4 = AND ( x1 , y1 );
	w3 = AND (x0 , y1 ) ;
	w8 = AND ( x2 , y2 ) ;
	w7 = AND ( x1 , y2 );
	w6 = AND (x0 , y2 ) ;
	// add first and second row 
	( w9 , w10 ) = HA (w1 , w3 ) ;
	( w11 , w12 ) = FA ( w2 , w4 , w10 );
	( w13 , w14 ) = HA ( w5 , w12 );
	// add the third row 
	( w15 , w16 ) = HA ( w11 , w6 );
	( w17 , w18 ) = FA ( w13 ,w7 , w16 ) ;
	( w19 , w20 ) = FA ( w14 ,w8 , w18 ) ; 
}
```

![mp](mp.png)

Grüne Gatter sind einfache `AND` Gatter.
Gelbe Gatter sind Halbaddierer mit `AND` Gattern
Blaue Gatter sind Volladdierer mit `AND` Gattern

![bmp](bmp.png)
## Parallel Prefix Carry

$$(g_2, p_2) \odot (g_1, p_1) := (g_2 \lor p_2 \land g_1, p_2 \land p_1)$$

$$(c_{i+1}, \bigwedge^i_{j=0} p_j) \iff (g_i, p_i) \odot \dots \odot (g_0, p_0) \odot (c_0, 1)$$


## Fixed Point

$$\langle[x_{m+n}, \dots, x_0]\rangle^\mathbb R_{B, n} := \langle[x_{m+n}, \dots, x_0]\rangle^\mathbb Z_B \cdot B^{-n} = \alpha(x_{m+n}) \cdot B^m + \sum\limits^{m+n-1}_{i=0} x_i \cdot B^{i-n}$$

## Floating Point

Wir stellen die Mantisse als eine [Radix-B](Radix-B.md) Zahl dar und, den Exponenten als eine Radix-B Zahl mit einem bias $\beta$ (Excess-$\beta$)

$$\begin{align}
&\langle[x_{e+m}, x_{e+m-1}, \dots, x_m, x_{m-1}, \dots, x_0]\rangle^\mathbb R_{B, m, e}:= \\&\underbrace{(-1)^{x_e+m}}_{\text{Sign}} \cdot \underbrace{\left(\langle[x_{m-1}, \dots, x_0]\rangle^\mathbb N_B \cdot B^{1-m}\right)}_{mantissa} \cdot B^{\underbrace{\langle[x_{e+m-1}, \dots, x_m]\rangle^\mathbb N_B -\beta}_{exponent}}
\end{align}$$

wobei
$\beta := MaxNat(e) \div 2 = (B^e -1) \div 2$
Wir nehmen an das $x_{e+m} \in \lbrace1,0\rbrace$


- Warum Multiplizieren wir mit der Mantissa $B^{1-m}$?
$M := \langle[x_{m-1}, \dots, x_0]\rangle^\mathbb N_B \cdot B^{1-m}$ ist eine [Fixed-Point Nummer](Fixed-Point%20Nummern.md), der Dezimalpunkt ist zwischen $x_{m-1}$ und $x_{m-2}$, also $0.0 \leq M \leq B-B^{1-m} < B$
- Warum Verwenden wir ein Explizites Zeichen für die Mantissa?
Dies vereinfacht den Vergleich von Floating-Point Zahlen, und ermöglicht einen Symmetrischen Darstellungsbereich.
- Warum verwenden wir Excess-$\beta$ als Exponenten?
Darum

### Zahlenbereiche

#### Normalisisert

Exponent: $MaxNat(e) = (B^e - 1) -\beta$
Mantissa: $MaxNat(m) = (B^m -1) \cdot B^{1-m} = B-B^{1-m}$
-> $(B-B^{1-m} \cdot B^{(B^e -1) - \beta})$

Exponent: $-\beta$
Mantissa: $\langle[1, 0, \dots, 0]\rangle^\mathbb N_B \cdot B^{1-m} = 1.0$
-> $B^{-\beta}$


#### Denormalisiert

Exponent: $E = -\beta$ 
Mantissa $(B^{m-1} -1) \cdot B^{1-m} = 1 - B^{1-m}$
-> $(1-B^{1-m}) \cdot B^{-\beta}$

Exponent: $E = -\beta$
Mantissa $\langle[0, \dots, 0, 1]\rangle^\mathbb N _B \cdot B^{1-m} = B^{1-m}$
-> $B^{1-m-\beta}$

### IEEE 754


| class            | sign | exponent  | mantissa           |
| ---------------- | ---- | --------- | ------------------ |
| $NaN$            | $*$  | $1\dots1$ | $\not=0\dots0$     |
| $\pm\infty$      | $*$  | $1\dots1$ | $0\dots0$          |
| denormale Zahlen | $*$  | $0\dots0$ | $\not = 0 \dots 0$ |
| Nullen           | $*$  | $0\dots0$ | $0\dots0$          |

Normalisierte Zahlen verwenden die Exponenten $0\dots01$ bis $1\dots10$

## Endlicher Automat

>[!IMPORTANT] Definition
> Ein endlicher Automat $A$ ist ein Tupel $A = \langle\Sigma_{in}, S, L, R, F\rangle$ wobei
> $\Sigma_{in}$ das Eingabe Alphabet ist
> $S = \lbrace s_1, \dots, s_m\rbrace$  eine endliche [Menge](Mengen.md) von Knoten ist
> $L\subset S$ die Menge von Start Knoten ist
> $R\subset S \times \Sigma_{in} \times S$ die Kanten sind
> $F \subset S$ die End Knoten sind.

Für jeden FSM $A = \langle \Sigma_{in}, \Sigma_{out}, S, L, R\rangle$ koennen wir einen FSA $A' = \langle\Sigma_{in} \times \Sigma{out}, S\cup\lbrace s_0\rbrace\rangle, L, R', F$ mit 

$s_0$ ist ein neuer Knoten nicht in $S$

$$R' = \begin{align}
&\lbrace(s, (i, o, s') | (s, i, o, s') \in R\rbrace \cup\\ &\lbrace (s, (i, o), s_0 | \neg\exists s' \in S.(s, i, o, s') \in R) \rbrace\cup\\
&\lbrace (s_0, (i, o), s_0) | (i, o) \in\Sigma_{in} \times \Sigma_{out} \rbrace
\end{align}$$

$F = S$

$A$ übersetzt $a_1, \dots, a_l \in \Sigma^*_{in}$ nach $b_1, \dots, l \in\Sigma_{out} \iff A'\text{ akzeptiert } (a_1, b_1) \dots (a_l, b_l)$ 

Wenn wir $(i, o)$ im Knoten $s$ lesen wechseln wir nach $s'$ in $A'$ wenn $A$ von $s$ nach $s'$ wechselt wenn es $i$ liest und $o$ generiert.

Der Fehlerknoten $s_0$ wird erreicht wenn ein Paar $(i, o)$ in einem Knoten $s$ gelesen wird sodass $A$ im Knoten $s$ für Input $i$ ein anderes Ergebnis $o$ liefert

Die andere Richtung funktioniert auch:


Für jeden FSA $A = \langle \Sigma_{in}, \Sigma_{out}, S, L, R\rangle$ können wir einen FSM $A' = \langle\Sigma_{in} \times \Sigma{out}, S\cup\lbrace s_0\rbrace\rangle, L, R', F$ mit 

$$R' \iff \begin{align}
\lbrace (s, i, 0, s') | (s, i, s') \in R \land s' \not\in F' \rbrace \cup\lbrace (s, i, 1, s') | (s, i, s') \in R \land s' \in F' \rbrace
\end{align}$$

$A$ akzeptiert 
$\alpha := a_1\dots a_l \in\Sigma^{*}_{in} \iff A'$ $\alpha$ nach $b_1, b_l \in \lbrace 0,1\rbrace^*$ sodass $b_l = 1$

Mit Ausnahme des leeren Wortes kann ein FSM also auch Informationen über das Akzeptieren generieren.


```python
def Equivalence(Sigma, S1, I1, R1, F1, S2, I2, R2, F2):
    Delta_new = set()
    for f1 in F1:
        for s2 in (S2 - F2):
            Delta_new.add((f1, s2))
    for s1 in (S1 - F1):
        for f2 in F2:
            Delta_new.add((s1, f2))
    
    while True:
        Delta_old = Delta_new.copy()
        
        for s1 in S1:
            for s2 in S2:
                if (s1, s2) not in Delta_old:
                    for sigma in Sigma:
                        s1_prime = successor(s1, sigma)  
                        s2_prime = successor(s2, sigma)  
                        
                        if (s1_prime, s2_prime) in Delta_old:
                            Delta_new.add((s1, s2))
                            break
        
        if Delta_old == Delta_new:
            break
    
    return not any((i1, i2) not in 
				   Delta_new for i1 in I1 for i2 in I2)


result = Equivalence(alphabet, states1, initial1, accepting1, failing1, states2, initial2, accepting2, failing2)
```