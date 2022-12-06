Ein Körper ist ein [kommutativer](Kommutativgesetz.md) [Ring](Ring.md) R mit 1 sodass $R\setminus\{0\}$ eine Gruppe ist.

Es muss also jedes Element in $R \setminus \{0\}$ bezüglich der Multiplikation ein Inverses besitzen.

## Archimedisch
Ein angeordneter Koerper $K$ heisst Archimedisch, wenn es zu jedem $r\in K$ ein $n\in\mathbb N$ gibt mit $n> r$.

### Beispiel
Der Koerper $\mathbb Q$ ist Archimedisch: Ist $r = {a\over b}\in \mathbb Q$ mit $b> 0$, dann gibt es ein $n \in \mathbb N$ mit $a\leq n\cdot b$. Auch $\mathbb R$ ist Archimedisch

---

Ist $K$ Archimedisch und $x\in K$ mit $-1 < x < 1$, dann gilt 
$$\lim_{n\to\infty} x^n = 0$$
### Binomialsatz
Sei $K$ ein Koerper und $x\in K$. Fuer alle $n \in\mathbb N_0$ gilt
$$(x +1)^n = \sum^{n}_{k=0} \left(n \atop k\right) x^k$$
Dabei bezeichnet $\left() n\atop k \right)$ die Anzahl der k-elementigen Teilmengen einer n-elementigen Menge.
