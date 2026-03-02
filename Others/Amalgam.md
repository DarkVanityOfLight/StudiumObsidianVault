An _amalgam_ can be formally defined as a 5-tuple $(A,f,B,g,C)$ such that $A,B,C$ are structures having the same signature, and $f: A \to B$, $g: A \to C$ are [embeddings](Embedding.md).

A class $K$ of structures has the amalgamation property if for every amalgam with $A, B, C \in K$ and $A \not = \emptyset$, there exists both a structure $D \in K$ and embeddings $f': B \to D, g': C \to D$ such that
$$ f' \circ f = g' \circ g$$
A first-order theory $T$ has the amalgamation property if the class of models of $T$ has the amalgamation property.