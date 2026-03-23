A tree is called _infinite_ if it has infinitely many nodes.
A tree is called _locally finite_ if every node has only finitely many children.

> Every infinite locally finite tree contains an infinite branch.


We construct the infinite branch inductively(Axiom of Choice required). We know that all of the infinitely many vertices can be reach from $v_0$. Suppose $u_1, u_2, \dots, u_k$ are children of $v_0$. At least one of them can be used to reach infinitely many vertices, say $u_i$. Set $v_1 = u_i$ and iterate.

