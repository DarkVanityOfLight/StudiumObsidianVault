Eine Gruppe $(G, \circ)$ ist eine [Menge](Mengen.md) $G$ mit einer Verknüpfung
$$\begin{align}
\circ :& G \times G \to G\\
&(a,b) \mapsto a \circ b
\end{align}$$

- [Assoziativ](Assoziativgesetz.md) $a \circ (b \circ c) = (a\circ b) \circ c \quad \forall a, b, c  \in G$
- Es existiert ein neutrales Element dh. $e \in G$ mit $e \circ a = a\circ e =a \forall a \in G$
- Existenz des Inversen dh. $\forall a \in G \exists a^{-1} \in G\quad a^{-1} \circ a = a \circ a^{-1} = e$

## Monoid
[Assoziativ](Assoziativgesetz.md) + Existenz des Neutral elements

## Abelsch
Gilt das [Kommutativgesetz](Kommutativgesetz.md) $a \circ b = b \circ a\quad \forall a, b \in G$
dann heißt $G$ abelsch oder kommutativ.

### Beispiel
#### Monoid
$\mathbb N_0 = \{0, 1\} \text{mit} +$ ist eine abelsche Monoid mit Neutralem 0.

$\mathbb N = \{1, 2, 3, ...\}$ mit $\cdot$ ist abelsches Monoid mit Neutralem 1. Keine Gruppe da $2 \cdot x = 1$ nicht lösbar in $\mathbb N$
