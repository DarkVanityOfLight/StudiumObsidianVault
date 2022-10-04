# Aufgabe 1.1
a) Es schneit und es ist kalt
b) Es schneit und es ist nicht kalt
c) Wenn es schneit ist es Kalt
d) Es schneit nicht und es ist nicht kalt
e) Es schneit nicht oder es ist nicht kalt

# Aufgabe 1.2
a)
$A$  | $B$ |$A \implies B$ | $\neg A \land B$
-- |--  |--------|------
W  | W| W| W
W  | F| F| F
F | F| W| W
F|W|W|W
b)
$A$|$B$|$C$|$A \lor (B \lor C)$ |$(A \lor B) \lor C$
-|-|-|-|-
W|W|W|W|W
F|W|W|W|W
W|F|W|W|W
W|W|F|W|W
F|F|W|W|W
W|F|F|W|W
F|W|F|W|W
F|F|F|F|F

c)
$A$|$B$|$C$|$A \land (B \lor C)$| $(A \land B) \lor (A \land C)$
-|-|-|-|-
W|W|W|W|W
F|W|W|F|F
W|F|W|W|F
W|W|F|W|F
F|F|W|F|F
W|F|F|F|F
F|W|F|F|F
F|F|F|F|F

# Aufgabe 1.3
a)
Wenn $A$ lustig und $B$ langhaarig
$$(\forall m \in M| A \land B)$$
$$(\exists m \in M|\neg (A \land B))$$
b) Wenn $A$ Brille und $B$ Kontaktlinsen
$$(\exists m \in M|A \lor B)$$
$$(\forall m \in M| \neg(A \lor B))$$