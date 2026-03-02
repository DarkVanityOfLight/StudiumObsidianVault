Let $\Sigma$ be a [signature](Logik/Signatur.md), consisting of:
- a [set](Mengen.md) of operation symbols, and
- for each symbol $f \in \Sigma$, a natural number $\operatorname{ar}(f) \in \mathbb{N}$ called its arity.


A $\Sigma$-algebra $\mathcal{A}$ is a structure
$$\mathcal{A} = \left( A,\ (f^{\mathcal{A}})_{f \in \Sigma} \right)$$
where:
$A$ is a nonempty set (called the [universe](Domain.md) or *carrier*),
for each $f \in \Sigma$ with arity $n = \operatorname{ar}(f)$,
$$f^{\mathcal{A}} : A^n \to A$$
is an $n$-ary operation on $A$.

_Remarks_
If $\operatorname{ar}(f) = 0$, then
$$f^{\mathcal{A}} : A^0 \to A$$
corresponds to a distinguished element of $A$ (a constant symbol).
No axioms are included in the definition of an algebra itself.

An algebra is precisely a [first-order logic](Logik/Prädikatenlogik.md) [structure](Struktur.md) whose [signature](Logik/Signatur.md) contains only function symbols (and possibly constant symbols) and no relation symbols.
