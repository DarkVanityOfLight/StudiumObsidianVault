Ein Körper ist ein [kommutativer](Kommutativgesetz.md) [Ring](Ring.md) $R$ mit 1 sodass $R\setminus\{0\}$ eine Gruppe ist.

Es muss also jedes Element in $R \setminus \{0\}$ bezüglich der Multiplikation ein Inverses besitzen.

## Archimedisch


Ein angeordneter Körper $K$ heißt Archimedisch, wenn es zu jedem $r\in K$ ein $n\in\mathbb N$ gibt mit $n> r$.

Ist $K$ Archimedisch und $x\in K$ mit $-1 < x < 1$, dann gilt 
$$\lim_{n\to\infty} x^n = 0$$ ^113caa
### Beispiel
Der Körper $\mathbb Q$ ist Archimedisch: Ist $r = {a\over b}\in \mathbb Q$ mit $b> 0$, dann gibt es ein $n \in \mathbb N$ mit $a\leq n\cdot b$. Auch $\mathbb R$ ist Archimedisch

---

### Binomialsatz
Sei $K$ ein Körper und $x\in K$. Fuer alle $n \in\mathbb N_0$ gilt
$$(x +1)^n = \sum^{n}_{k=0} \left(n \atop k\right) x^k$$
Dabei bezeichnet $\left() n\atop k \right)$ die Anzahl der k-Elementigen Teilmengen einer n-elementigen Menge.
