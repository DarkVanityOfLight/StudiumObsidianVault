
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
und deren [Komposition](Mathe/Komposition.md) $(f \circ g): C \to B$ definiert als $(f\circ g)(x) := f(g(x))$. 


Die Ersetzung $[\varphi]^{\alpha}_{x}$ ist das gleiche wie die Funktions Komposition.

Der Algorithmus der dem bei ROBDDs entspricht heißt `Compose`. Er nimmt eine Variable $x$ und zwei BDDs $\text{BDD}(\varphi), \text{BDD}(\alpha)$, $\text{Compose}(x, \varphi, \alpha)\text{BDD}([\varphi]^\alpha_x)$ 

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

Wir ersetzen also den Subtree $\alpha$ in unserem BDD $\varphi$ mit $x$

#### Exist

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

Wenden wir den Algorithmus auf eine Formel an die genau eine Variable $x$ hat, überprüfen wir damit ob es eine Belegung von $x$ gibt sodass die Formel wahr wird. Dieses Konzept gilt auch bei BDDs mit mehreren Variablen, allerdings "eliminiert" der Algorithmus effektiv die Variable $x$ aus dem Baum.

#### Forall

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

Der `Forall` Operator stellt sicher das die gegebene Formel $\varphi$ für alle möglichen Belegungen für $x$ gilt.

### Variablen Ordnungen

ROBDDs sind einzigartig für jede gegebene Variablen Ordnung, jedoch hängt die Größe des ROBDDs von der Variablen Ordnung ab. Der Einfluss einer Variablen Ordnung kann sehr groß sein.


ROBDDs aus $\bigwedge^n_{i=1}(x_i \iff y_i)$ können zwischen $O(n)$ bis $O(2^{cn})$ reichen.

#### Additions Funktionen

Boolesche Funktionen $s_i(x_0, \cdots, x_{n-1}, y_0, \cdots, y_{n-1})$ für $i = 0, \cdots, n$  mit 
$$\left(\sum\limits^{n-1}_{i=0}x_i \cdot 2^i\right) + \left(\sum\limits^{n-1}_{i=0} y_i \cdot 2^i\right) = \sum\limits^{n}_{i=0}s_i(x_0, \cdots, x_{n-1}), y_0, \cdots, y_{n-1}) \cdot 2^i$$
nennt man Additions Funktionen.

ROBBDs für $s_i$ können lineare Größe für gute Variablen Ordnungen und Exponentielle für schlechte haben.

Die Beste Ordnung für einzelne Summen Bits $s_i$ unterscheidet sich von der besten Ordnung für alle $s_i$.

### Nummern Mengen als BDDs

Jede beliebige Menge aus Nummern $\lbrace a_0, \dots, a_m\rbrace$ kann als BDD dargestellt werden, welcher die Nummern als [Radix-2](Radix-B.md) Zahl encoded.

Nehmen wir zum Beispiel die Menge
$$\lbrace c \cdot x | x\in\mathbb N \land c\cdot x < 2^n\rbrace$$

für $n=8$ und $c=3$:
![numbdd](numbdd.png)

### Symmetrische Boolesche Funktionen

$f$ ist symmetrische wenn gilt $f(x_0, \dots, c_{n-1}) = f(x_{\pi(0), \dots, x_{\pi(n-1)}})$ für jede Permutation von $\pi$.
Das heißt der Funktionswert ist nur abhängig von $\sum\limits^{n-1}_{i=0} x_i$. Es gibt nur $2^{n+1}$ n-Rangige Funktionen dieser Art.

ROBDDs von Symmetrischen Funktionen mit $n$ Variablen, haben die Größe von $O(n^2)$ fuer alle Variablen Ordnungen und die Anzahl an Knoten hängt nicht von der Ordnung ab.

### Worst Case von BDDs

Die Booleschen Funktionen mit $p_i(x_1,\dots, x_n, y_1,\dots, y_n)$ mit $0 \leq i \leq 2n-1$ mit
$$\left(\sum\limits^{n-1}_{i=0} x_i \cdot 2^i\right) \cdot \left(\sum\limits^{n-1}_{i=0} y_i \cdot 2^i\right) = \left(\sum\limits^{2n-1}_{i=0} p_i(x_1, \dots, x_n, y_1, \dots, y_n) \cdot 2^i\right)$$
nennt man Multiplikationsfunktionen, der ROBDD von $p_n$ braucht mindestens $2^{\frac{n}{8}}$ Knoten für jede Variablenordnung.

ROBDDs zum Quadrieren, Multiplikatives Inverses und der Division von [Ganzen Zahlen](Ganze%20Zahlen.md) haben auch eine Exponentielle Größe für jede Variablenordnung.

>[!IMPORTANT] Die Anzahl an Knoten für einen Beliebigen BDD mit $n$ Variablen ist kleiner als $\frac{2^n}{n} \cdot (2 + \epsilon)$ für genügend große $n$

>[!IMPORTANT] Die Anzahl an Knoten für einen Beliebigen BDD mit $n$ Variablen ist kleiner als $3.125 \cdot \frac{2^n}{n}$ für alle $n$

### Optimale Variablen Ordnungen

>[!IMPORTANT] Eine Variablen Ordnung ist Optimal, wenn der dazugehörige ROBDD die kleinst mögliche Anzahl an Knoten hat.

Das errechnen der Optimalen Ordnung ist NP-Vollständig.

Der Beste bekannt Algorithmus läuft in $O(3^n n^2)$.

#### Heuristics

In Praxis sind die Algorithmen zu Zeitaufwändig deshalb verwendet man Heuristische Algorithmen

- Statische Heuristische Algorithmen wählen die Variablenordnung indem sie die Formel vor dem erstellen des ROBDDs betrachten
- Dynamische Heuristische Algorithmen verbessern die Variablenordnung während des erstellen des ROBDD wenn die Anzahl an Knoten eine vom Nutzer bestimmte Anzahl überschreitet

##### Statische Heuristic
Ein Ansatz ist für jede Gleichung $y_i = \varphi_i$ die Variable $y_i$ größer als die Variablen in $\varphi$ zu machen.

![drssv](drssv.png)

##### Dynamic Reordering

###### Window Permutations

Gegeben sei ein ROBDD mit den Variablen $x_1 \prec \dots \prec x_n$ und ein Fenster der Größe $k$ mit $1 \leq k \leq n$

Betrachten wir ein Fenster $x_i \prec \dots \prec x_{i+k-1}$ der Größe $k$ an der Position $i$.
- Versuche alle Permutationen der Variablen im Fenster -> $k! -1$ Vertauschungen
- Verwende nur Vertauschungen um die Permutationen zu Enumerieren
- Speichere die letzte beste Variablenordnung
- Nach dem beenden, verwende diese Ordnung in $O(k^2)$ vertauschungen

Wiederhole diese Schritte für alle Fenster $F_1, ..., F_{n-k+1}: O(n)$ Wiederholungen
Maximal brauchen wir also $O(k!k^2 n)$ Vertauschungen.

###### Sifting

Die Fenster Permutation errechnet die lokalen Minima in den Fenstern. Sifting hingegen betrachten das gesamt Bild.

Dabei suchen wir einen guten Platz für die Variable $x$ wobei alle anderen an ihrem Platz bleiben, wir merken uns diesen besten Platz und schieben $x$ danach zurück an die Position.

Wir wiederholen diese Schritte für alle Variablen und erhalten damit maximal $O(n^2)$ Vertauschungen.


### Care Sets

Formel haben meist ein sogenanntes Care Set, irrelevante Variablenbelegungen nennt man "don't cares"

#### Beispiel

| $x_1$ | $x_2$ | Color  |
| ----- | ----- | ------ |
| 0     | 0     | red    |
| 0     | 1     | yellow |
| 1     | 0     | green  |
| 1     | 1     | -      | 


Don't Cares können verwendet werden um ROBDDs zu minimieren. Hier ist die Idee:

- Anstatt von $\varphi$ betrachten wir eine Formel $\uppsi$ die von $\varphi$ unterschiedlich sein kann über dem "Don't Care" Set
- Unser ziel ist es einen minimalen ROBDD für $\varphi$ zu bestimmen

#### Orthonormal Basis

Die Formeln $\beta_0, \dots,\beta_{n-1}$ sind eine Orthonormale Basis wenn folgendes gilt:
$\beta_i \land \beta_j \iff 0$ wenn $i\not= j$
$$\left(\bigvee^{n-1}_{i=0}\beta_i\right) \iff 1$$

Gegeben sein eine ONB $\beta_0, \dots,\beta_{n-1}$, für jede Formel $\phi$ gibt es Formeln $\varphi_0, \dots, \varphi_{n-1}$ sodass $\phi$ neu geschrieben werden kann als:
$$\phi \iff \bigvee^{n-1}_{j=0} \varphi_j \land \beta_j$$ und auch
$$\phi \iff \oplus^{n-1}_{j=0} \varphi_j \land \beta_j$$

$\varphi_i$ nennt man Kofaktoren von $\phi$ bezüglich $\text{ONB}\lbrace \beta_0, \dots, \beta_{n-1} \rbrace$

nehmen wir an die Formel $\varphi$ ist als ihre generalisierten Kofaktoren $\varphi_0, \dots,\varphi_{n-1}$ für eine $\text{ONB}\lbrace \beta_0, \dots, \beta_{n-1} \rbrace$
$$\phi \iff \bigvee^{n-1}_{j=0} \varphi_j \land\beta_j$$
das impliziert das $\phi \land \beta_i \iff \varphi_i \land \beta_i$ 

$\beta_i$ ist ein Care-Set 
- $\phi$ und $\varphi_i$ sind äquivalent solange $\beta_i$ gilt
- $\phi$ und $\varphi_i$ können unterschiedlich sein wenn $\beta_i$ nicht gilt

die Kofaktoren $\varphi_i$ sind nicht eindeutig definiert für $\phi$ und eine ONB, insbesondere $\phi \land \beta_i$ und $\phi\lor\neg\beta_i$ können als Kofaktoren $\varphi_i$ verwendet werden.

#### Constrain

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

Wir haben $\text{Constrain}(\beta, \phi)\land\beta = \phi \land \beta$, wir merken $\text{Constrain}(\beta, \phi)$ ist ein generalisierter Kofaktor.

Schauen wir uns den Aufruf
$\text{Constrain}((x \implies \beta_1 | 0), (x\implies \phi_1 | \phi_0))$

Der negative Kofaktor $\phi_0$ ist beliebig. 
Beim ersten Versuch wählen wir $\phi'_0 = 0$, dies schein ein kleiner ROBDD zu sein, aber $\phi'_0 = Constrain(\beta_1, \phi_1)$ ist besser.
Da gilt $(x \implies \phi'_0 | \phi'_0) = \phi'_0$ können wir den Knoten $x$ löschen. Das Endergebnis ist deswegen $\phi'_0$

Meistens ist $\text{Constrain}(\beta,\phi)$ kleiner als $\phi$, in manchen fällen ist es allerdings sogar grösser.
Um dies zu verhindern gibt es Restrict.
#### Restrict

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


Wir haben $\text{Restrict}(\beta, \phi) \land \beta = \phi \land \beta$ 
Restrict ist auch ein generalisierter Kofaktor, Restrict funktioniert aehnlich wie Constrain jedoch:
Nehmen wir an $m \not = \mathbf{label}(\phi)$
- $\implies \mathbf{label}(\phi) < \mathbf{label}(\beta)$
- deswegen gilt $\mathbf{label}(\beta)$ taucht nicht in $\phi$ auf
- deswegen wir $\mathbf(label)(\beta)$ aus $\beta$ mit Quantifikation gelöscht
- dies wird durch die Disjunktion von $\beta_0$ und $\beta_1$ erreicht

Manchmal ist `Constrain` und manchmal `Restrict` besser und beide können mehr Knoten als $\phi$ haben, aber meist sind sie kleiner