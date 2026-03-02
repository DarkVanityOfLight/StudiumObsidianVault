
## Convolution

$$ w_1 \otimes \cdots \otimes w_k
\;:=\;
\begin{pmatrix}
a_{11} \\
a_{21} \\
\vdots \\
a_{k1}
\end{pmatrix}
\begin{pmatrix}
a_{12} \\
a_{22} \\
\vdots \\
a_{k2}
\end{pmatrix}
\cdots
\begin{pmatrix}
a_{1\ell} \\
a_{2\ell} \\
\vdots \\
a_{k\ell}
\end{pmatrix}
\;\in\;
(\Sigma_{\Box}^k)^* $$
For a fresh padding symbol $\Box$.

## Automatic Structures

A Relational structure $\mathfrak{A} = (A, R_1, ..., R_k)$ is automatic
if 
- $A$ is regular over a finite alphabet
- each relation $R_i \subseteq A^{r_i}$ is regular

## Automatic Structures are decidable

Given an automatic presnetation of $\mathfrak{A}$ and a formula $\phi(\bar x)$ one can compute a finite automaton for the language $L_\phi = \otimes\{\bar a | \mathfrak{A} \vDash \phi(\bar a)\}$ 

We proceed by structural induction on $\phi$.

_Relation_ if the Atom is a Relation $R_i(...)$ we construct 
$L_\phi = \text{unpad}(\sigma^-1(\otimes R))$  where unpad removes trailing $\Box$ symbols and $\sigma$  is the morphism projecting onto the components used in the relation.

_Negation/Disjunction_ Follow from the closure properties
_Quantification_ Project away the quantified component and unpad
$L_\phi =  \text{unpad}(\pi(L_\psi))$

