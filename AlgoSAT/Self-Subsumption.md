
$$\frac{C \lor l \quad D\lor \overline l}{D} C\subseteq D \qquad \frac{(a \lor b \lor l) \quad (a\lor b\lor c\lor \overline l)}{a \lor b \lor c}$$

Let $C \lor l$ and $D \lor \overline l$ with $C \subseteq D$ be clauses in $F$. Let $F'$ denote the formula where $D \lor \overline l$ is replaced by $D$. $F$ and $F'$ are equivalent.

$D$ is obtained by resolution from $F$, so $F\land D$ is equivalent to $F$, clearly $D \vDash D \lor \overline l$, hence the claim follows.

Another clause $C \lor l$ is used to shrink $D \lor \overline l$, self-subsumption is used to shorten conflict clauses. Practical candidates for $C\lor l$ are antecedents on the trail.