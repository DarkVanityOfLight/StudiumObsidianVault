
Die [Shannon Normal Form](Shannon%20Normal%20Form.md) stellt eine Boolesche Funktion mit den Konstanten 1,0 und dem [Shannon Operator](Shannon%20Operator.md) dar.

Beim Dekomposieren der Formel bemerken wir das mehr und mehr Formeln wieder auftauchen. Wenn wir diese Unterformeln nur einmal speichern erhalten wir BDDs


BDDs sind gerichtete azyklische Graphen(DAGs), es gibt eine einzelnen Wurzel Knoten $v_0$ und zwei Blatt Knoten $L_0$ und $L_1$. Jeder Knoten $v \not \in \lbrace L_0, L_1 \rbrace$ hat zwei Folgeknoten bezeichnet als $\mathbf{high}(v)$ und $\mathbf{low}(v)$ und eine Bezeichnung durch eine Variable $\mathbf{label}(v)$.
Blätter werden durch $\mathbf{label}(L_0) := 0$ und $\mathbf{label}(L_1) := 1$ bezeichnet. Kanten respektieren

## Variablen Ordnung

Gegeben die Variablen $V = \lbrace x_1, \cdots, x_n \rbrace$ und eine [Bijektive](Bijektiv.md) Funktion $\pi: V \to\lbrace 2, \cdots, |V| + 1 \rbrace$ wobei $\pi$ die Totale Ordnung der Variablen darstellt.

Wir erweitern $\pi$ auf die folgende Grad Funktion über $V\cup\lbrace1, 0\rbrace$:
$$D(v) := \begin{cases}\pi(v) : \text{if } v\in V\\v :\text{if } v\in\lbrace1, 0\rbrace\end{cases}$$

Dies erlaubt den Vergleich von Atomaren Propositionen in $V \cup\lbrace1,0\rbrace$. Die Ordnung sieht also Folgendermaßen aus:
$$0 \prec_\pi 1 \prec_\pi x_1 \prec_\pi x_2 \prec_\pi \cdots \prec_\pi x_n$$



## Ordered Binary Decision Diagrams

In OBBDs Respektieren Kanten die Variablen Ordnung
$$D(\mathbf{label}(\mathbf{high}(v))) < D(\mathbf{label}(v))$$
$$D(\mathbf{label}(\mathbf{low}(v))) < D(\mathbf{label}(v))$$

### Beispiel

Hier ein OBDD von $x_1 \land x_2 \lor x_3 \land x_4$
![obbd](obdd.png)

### ROBDDs

Ein Ordered Binary Decision Diagram gilt als Reduziert wenn
- es kein $v$ mit $\mathbf{high}(v) = \mathbf{low}(v)$ gibt
- es kein $v, v'$ gibt sodass der Subgraph an $v$ [Isomorph](Isomorphismen.md) zu dem an $v'$ ist.

#### Reduzierungs Regelen

Es gibt zwei Regeln um einen OBDD in einen ROBDD umzuwandeln:

- Eliminierung: Falls $\mathbf{high}(v) = \mathbf{low}(v)$ gilt, dann lösche $v$ und verbinde alle Kanten nach $v$ nach $\mathbf{high}(v)$
- Isomorphi: Falls $\mathbf{label}(v) = \mathbf{label}(v')$ und $\mathbf{low}(v) = \mathbf{low}(v')$ gilt, loesche $v'$ und Verbinde alle kannten nach $v'$ neu nach $v$.

Eliminierung:
![](erobdd.png)

Isomorphie:
![irobdd](irobdd.png)

#### Rekursive Boolesche Komposition

>[!NOTE] 
$$f = (x_f \implies f_1 | f_0)$$
$$g = (x_g \implies g_1 | g_0)$$


Rekursive aufrufe Folgen der Variable Ordnung, je nach Ordnung machen wir den Rekursiven Aufruf mit $(f, f)$ oder $(f_0, f_1)$.

Wir vereinfachen dies durch eine Hilfsfunktion, dafür definieren wir für einen beliebigen Knoten $v$ mit der Variable $x = \mathbf{label}(v)$ und ein beliebiges $m\in \mathbb N$:
$$\text{Ops}(v, m) := 
\begin{cases}
(\mathbf{low}(v), \mathbf(high)(v)) :\text{if } m = D(x)\\
(v, v) : \text{ else }
\end{cases}$$

```python
def Ops(v, m):
	x = label(v)
	if m == D(x):
		return (low(v), high(v))
	else
		return (v, v)
```

Unser Apply Algorithmus für einen Beliebigen Booleschen Operator sieht dann so aus:

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

`Eval` inspiziert die Wahrheitstabelle und gibt eine der Blatt Knoten zurück
`CreateNode` inspiziert die einzigartige Tabelle für den Knoten $(m, h, l)$ und erstellt ihn falls er noch nicht existiert.

Manche Operationen können direkt evaluiert werden.

$0 \land\varphi \iff0$
$1\land\varphi \iff \varphi$


#### ITE Algorithmus

BDD Pakete merken sich bereits ausgeführte Operationen in Trippeln $(\oplus, f, g)$. Verschiedene Operationen $(\oplus, f, g)$ können dieselben Ergebnisse liefern.

Deswegen wird meist eine Operator Basis mit einem Operator verwendet(meist [Shannon Operator](Shannon%20Operator.md))

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

#### Komposition

Gegeben sei $f: A \to B$ und $g: C \to A$
und deren [Komposition](Mathe/Komposition.md) $(f \circ g): C \to B$ definiert als $(f\circ g)(x) := f(g(x))$. Für eine beliebige gegebene Formel $\varphi$ über den Variablen $x_1, \cdots, x_n$ betrachten wir die dazugehoerige Boolesche Funktion $f_\varphi(v_1, \cdots, v_n) := \textlbrackdbl [\varphi]^{v_1, \cdots , v_n}_{x_1, \cdots, x_n} \textrbrackdbl_\varepsilon = \textlbrackdbl\varphi\textrbrackdbl_{\varepsilon}$ mit $v_i \in \lbrace0, 1\rbrace$.
Dann gilt 
$$
f_{[\varphi]^\alpha_{x_n}}(v_1, \cdots , v_n) := f_\varphi(v_1, \cdots, v_{n-1}, f_{\alpha}(v_1, \cdots, v_n))
$$

Die Ersetzung $[\varphi]^{\alpha}_{x}$ ist das gleiche wie die Funktions Komposition.

Der Algorithmus der dem bei ROBDDs entspricht heißt `Compose`. Er nimmt eine Variable $x$ und zwei BDDs $\text{BDD}(\varphi), \text{BDD}(\alpha)$ und gibt aus: $\text{BDD}([\varphi]^\alpha_x)$ 

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

