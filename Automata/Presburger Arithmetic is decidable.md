
Given a Presburger forumla $\phi(x_1, ..., x_k)$ one can compute an NFA for the language
$$ L_\phi = \{ (w\in \{0, 1\}^k)^* | (\mathbb N, +) \vDash \phi(val(w)) 
\} $$
$L_{\phi}$ is non empty iff $\phi$ is true.


We replace the addition function by the ternary addition Relation.

We construct an NFA via structural induction over $\phi(x_1, ..., x_n)$.

_Addition:_ We perform standard school addition on the tuple obtained by projecting on the 3 corresponding components.
_Addition:_ The trivial Equality Automata under the projection onto the two equal components.
_Negation/Disjunction_ Follow from the closure properties of NFAs
_Quantifiers_: $\exists x_i. \phi(x_1, ..., x_i, ..., x_n)$ is replaced by the automata under the projection $\pi$ projecting away the $i$-th component $\pi(L_\phi)$ and removing all trailing zeros by declaring states final when a final state can be reached by reading all zeros.


