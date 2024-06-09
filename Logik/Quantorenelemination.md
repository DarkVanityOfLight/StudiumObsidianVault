
Aus dem [Los-Vaught-Test](Los-Vaught-Test.md) entsteht kein effizientes Entscheidungsverfahren. Die _Quantorenelimination_ ermöglicht uns, die Erfüllbarkeit von Formeln in $Th(\mathbb Q, <)$ und komplexeren Theorien zu entscheiden.

für einfache Formeln lässt sich diese Methode manuell ausführen.

>[!DEFINITION]
>Eine Theorie $T$ hat Quantorenelimination, wenn jede Formel $\varphi(\overline x)$ eine $T$-äquivalente quantorenfreie Formel $\psi(\overline x)$ hat, d.h., 
>$$T\vDash \forall *(\varphi \leftrightarrow \psi)$$

Ein Quantoreliminationsalgorithmus (QE-Algorithmus) für $T$ ist ein [Algorithmus](Algorithmus.md), der aus jedem $\varphi$ ein $\psi$ produziert.

Ein QE-Algorithmus für $T$ resultiert in einem Entscheidungsverfahren für $T$, weil jeder Satz dadurch auf $\top$ oder $\bot$ reduziert wird.

Es genügt, die Eliminierung eines __einzigen Quantors zu zeigen__ d.h. Sei $\exists x\varphi$ gegeben, wobei $\varphi$  q-frei ist, finde man $q$ freies $\psi$, wobei 
$$T \vDash \psi \leftrightarrow \exists x\psi$$

Sei eine Formel $Q_1 x_1 \dots Q_n x_n \varphi$ gegeben, wobei $\varphi$ q-frei ist.

1. $F := \varphi$
2. for $i=n, \dots, 1$
	1. if $Q_i = \exists$:
		1. $F :=$ zu $\exists x_i F$ $T$-äquivalente q-freie Formel
	2. else:
		1. $F := \neg(\text{zu } \exists x_i \neg F)$ $T$-äquivalente q-freie Formel
3. Gib $F$ aus

## Quantorenelimination für $Th(\mathbb Q, <)$

Wir zeigen, wie sich $x$ in $\exists x\varphi$ eliminieren lässt, wobei 
$$\varphi = \bigwedge^n_{i=1} x \sim_i x_i$$ mit $\sim_i \in \lbrace <, >, =\rbrace$

Generelles q-freies $\varphi$:
1. Man Eliminiere die Negation
2. Wandle in [Disjunktive Normalform (DNF)](Normalformen%20in%20der%20Aussagenlogik.md#Disjunktive%20Normalform%20(DNF) um und verwende:
   $$\exists x(\varphi \circ \psi) \equiv \exists x \varphi \circ \psi$$ wobei $\circ \in\lbrace \land, \lor \rbrace$ $x \not \in free(\psi)$


## Beispiel
$\exists x(y \not = z \land x < y) \equiv (y \not = z) \land \exists x(x<y) \equiv ((y<z) \lor (z< y)) \land \exists x(x< y)$

_Fall 1_: Eine Teilformel ist $x = x_i$. Dann $(\mathbb Q, <) \vDash \exists x \varphi \leftrightarrow \varphi[x_i/x]$
_Fall 2_: Eine Teilformel ist $x<x$. Dann $(\mathbb Q, <) \vDash \exists x\varphi\leftrightarrow \bot$
_Andernfalls_: Man trenne Ober-/Untergrenzen für $x$. Dann:
$$(\mathbb Q, <) \vDash \exists x\left(\bigwedge_{i=1}^{r} l_i < x \land \bigwedge^{s}_{j=1} x< u_j\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} l_i < u_j$$



## Optimierung 1
Man wende Folgendes soweit möglich an
$$\exists x(\varphi \circ \psi) \equiv \exists x\varphi \circ \psi$$ mit $\circ \in \lbrace \land, \lor \rbrace$ und $x\not\in free(\varphi)$
Dann wandle man die Formel in DNF um.

## Optimierung 2
Man lässt [Relationen](Relation.md) der folgenden Art zu
$$x \leq y := x < y \lor x = y$$
Dies ist nützlich, da $(\mathbb Q, <)\vDash x\not= y \leftrightarrow y \leq x$. Die QE Methode erweitert sich:

_Fall 3_: Man ersetze $x \leq x$ durch $T$. Dann verwende:

$$(\mathbb Q, <) \vDash \exists x\left(\bigwedge_{i=1}^{r} l_i \sim_i x \land \bigwedge^{s}_{j=1} x \approx u_j\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} l_i \sim_{i, j} u_j$$
wobei $\sim_i, \approx_j \in \lbrace <, \leq \rbrace$ und falls $\sim_i = \approx_j = \le$, dann $\sim_{i,j} := \le$ sonst $\sim_{i, j} := \le$

### Komplexität
Ein naive Implementation läuft in doppelt Exponentieller Zeit, kann aber so verbessert werden, sodass sie in einfach Exponentieller Zeit läuft.

## Quantifier Elimination over $Th(\mathbb Z; <, 0, s, p)$

$$\begin{align}
s: \mathbb Z\to \mathbb Z; s: i\mapsto i +1\\
p: \mathbb Z \to \mathbb Z; p: i\mapsto i-1
\end{align}$$

We show how to eliminate $x$ from $\exists x\varphi$, where 

$$\varphi = \bigwedge^n_{i=1} s^{k_i}(x) \sim_i s^{k'_i}(x_i)$$ where $\sim_i \in \lbrace <, >, =\rbrace$

We can assume that each conjunct is of the form 
$$x \sim s^k{y}$$
for some $\sim, k$.

We take a look at $3$ different cases:

1. One conjunct is $x\sim^k(x)$.
	1. Replace $x\sim s^k(x)$ by $\top$ iff $x\sim x+k$
	2. If we replaced by $\bot$ replace $\exists \varphi$ with $\bot$
	3. Otherwise, go to Case 2
2. One conjunct is $x = s^k(y)$ with $y$ distinct from $x$. Then: $$\mathcal Z_< \vDash \exists x\varphi \leftrightarrow \varphi[s^k(y) / x]$$
3. If we have upper/lower bounds on $x$. Then, 
   $$\mathcal Z_< \vDash \exists x \left(\bigwedge^r_{i=1} s^{k_i}(y_i) < x \land \bigwedge^s_{j=1} x < s^{k'_j}(z_j)\right) \leftrightarrow \bigwedge^r_{i=1}\bigwedge^s_{j=1} s^{k_i + 1}(y_i) < s^{k'_j}(z_j)$$
   