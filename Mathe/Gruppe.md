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

## Ordnung
$|G|$ Ordnung von $G$

---

Setzt man nur die Existenz eines linksneutralen Elements voraus $e\in G$, d.h $e\circ a = a \qquad \forall a\in G$
und von Linksinversen $a^{-1} \in G: a^{-1} \circ a = e \forall a$

## Beweis

ZZ:
$\forall a,b: a\circ b = e \implies b \circ a = e$
$a\circ e = a \quad \forall a$
#übung 

---

Sei $G$ eine Gruppe dann
1. Neutrales ist eindeutig
2. Inverse sind eindeutig
3. $(a \circ b)^{-1} = b^{-1} \circ a^{-1} \qquad (a^-1)^-1 = a$

## Beispiel
$(\mathbb Z, +)$ Gruppe, Neutrales Element $0$
$(\mathbb Z, \cdot)$ Monoid, Neutrales Element 1
$(\mathbb Q\setminus \{0\}, \cdot)$ [Abelsche](#Abelsch) Gruppe, Neutrales Element 1

## Symetrische Gruppe
$X = \{1, ..., n\}$
$S_n := S(\{1, ..., n\})$
$|S_n| = \# bij. Abb \{1, ..., n\} \to \{1,...,n\} = n!$

$\sigma \in S_n$ $\sigma = \left(1, ..., n \atop \sigma(1), ... \sigma(n)\right)$

## Transposition
$\sigma \in S_n$ heißt Transposition wenn $\sigma$ genau $2$ Elemente von $x$ vertauscht

$$\sigma = \left(1 2 3 4 5 \atop 1 5 3 4 2\right)$$

## [Kartesisches Produkt](Kartesisches%20Produkt.md)
Seien $G_1, G_2$ Gruppen, das kart. Produkt $G_1 \times G_2$
$$(a_1, b_2) \underbrace{\circ}_{G_1 \times G_2} (a_2, b_2) := (a_1 \underbrace{\circ}_{G_1} a_2, b_1 \underbrace{\circ}_{G_2} b_2)$$
ist eine Gruppe.
#übung 
