> Eine Abbildung $f: M \to N$ ist eine [Relation](Relation.md) $R\subset \underbrace{M}_{\text{Quelle}} \times \underbrace{N}_{\text{Ziel}}$ sodass es für jedes $m\in M$ genau ein $f(m)\in N$ gibt mit $(m, f(m)) \in R$.

## Schreibweise 
$$\begin{align}
f:& M \to N\\
&m \mapsto f(m)
\end{align}$$
## Bild
Für $A\subset M$ heißt  $f(A) = \{f(m) | m\in A\}$ Bild von A unter f
$$Bild(f) := f(M) \subset N$$
## Urbild
Für $B\subset N$ heißt $f^{-1}(B) := \{m\in M | f(m) \in B\}$ Urbild von B unter f.

## Graph
$R = Graph(f) := \{(m, f(m)) | m \in M\} \subset M\times N$

### Beispiel
$$\begin{align}
f:&\mathbb R \to \mathbb R\\
&x\mapsto f(x) := x^2
\end{align}
$$
$R^2 \supset R = Graph(f) = \{(x, x^2)| x\in \mathbb R\}$
$f(\mathbb R) = Bild(f) = \mathbb R_{\geq 0}$

Logische Formel B abhängig von $A_1,...,A_n$ ist eine n-stellige boolsche [Funktion](Mathe/Funktionen.md)

$$\begin{align}
f_B :& \{0, 1\}^n \to \{0, 1\}\\
&(A_1, ..., A_n) \mapsto B(A_1,..., A_n)O
\end{align}$$

## Surjektiv
$f: M\to N$ heißt surjektiv wenn $f(M) = N$

## Injektiv
Gilt für alle $m_1, m_2 \in M$ dass $f(m_1) = f(m_2) \implies m_1 = m_2$
so heißt f injektiv.

## Bijektiv
Wenn der Graph [Surjektiv](#Surjektiv) und [Injektiv](#Injektiv) ist, ist er Bijektiv
Ist $f: M \to N$ bijektiv dann gibt es für jedes $n \in N$ genau ein $m \in M$
mit $f(m) = n$
$\implies f^{-1}: N \to M, n \mapsto m$ falls $f(m) = n$

### Beispiel
$\forall m\in M$
$f^{-1}(f(m)) = m$
$f^{-1}$ inj Sei $n_1, n_2 \in N$ $f^{-1}(n_1) = f^{-1}(n_2)$
$$\begin{align}
\exists m_1, m_2 \in M: {f(m_1) = n_1 \atop f(m_2)= n_2}
\end{align}$$

$$\begin{align}
&f^{-1} (n_1) = f^{-1}(n_2)\\
&f^{-1}(n_1) = m_1\\
&f^{-1}(n_2) = m_2
\end{align}$$
also $m_1 = m_2 \implies f(m_1) = f(m_2)$ 

Siehe [Funktionen](Mathe/Funktionen.md)

## Schubfachprinzip
$M,N$ endl. $f: M \to N$  $inj \implies |M| \leq |N|$

## Beispiel
$M = \{1,2,3\}$ $N= \{1, 2\}$
$\implies |M| > |N| \implies$ es gibt keine inj. Abbildung $M\to N$

### Beweis
$$\begin{align}
|N| = \sum_{n\in N} 1 = \sum_{n\in N} \underbrace{|f^{-1}(\{n\})|}_{0 \text{falls} m \not\in Bild(f)\atop 1 \text{falls} m \in Bild(f)} \doteq |M|
\end{align}$$

$$
\text{gilt da}: M = \bigcup_{n\in N} \underbrace{f^{-1}(\{n\})}_{levelsets}
$$

Ist $f: M\to N$ bij. dann gibt es eine eindeutig bestimmte Umkehrabbildung
$f^{-1}: N \to M, n \mapsto m$ falls $f(m) = n$.
Es gilt $$\begin{align}
&f^{-1}(f(m)) = m& \forall m \in M\\
&f(f^{-1}(n)) = n& \forall n \in N
\end{align}$$
$Graph(f^-1) = \{f^{-1}(n), m| m \in M\}$
