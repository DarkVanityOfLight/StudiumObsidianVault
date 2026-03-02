
> ([MSO+U, p.6](MSO+U.pdf#page=6&selection=120,0,199,50&color=red))
> For every [Minsky Machine](Minsky%20Machine.md), one can compute a formula of mso+u which defines the set of words $w \in \lbrace1, 2, 3, 4\rbrace^\omega$ which have infinitely many 1’s and such that tree(w) has the following properties, [...] 
> - the degree of depth-3 nodes tends to infinity;
> - all but finitely many depth-1 nodes have the same degree d;
> - for every $i \in \lbrace1, . . . , d\rbrace$, all but finitely many depth-2 nodes that are an i-th child have the same degree, call it $n_i$; 
> - $n_1 − 1, . . . , n_d − 1$ describe some accepting run of the Minsky machine.


Assume Predicates $P_i/1$ for $i=1,2,3, 4$ such that $P_i(x)$ if the word has character $i$ at position $x$.



## The degree of depth 3 nodes tends to infinity
$$U X. \bigl( isFour(X) \land \exists n \land P_3(n) \land \forall x. X(x) \to isChild(n, x)\bigr)$$


---

## Well formed

> [!PDF|red] [MSO+U, p.6](MSO+U.pdf#page=6&selection=207,0,212,16&color=red)
> > We say that a sequence of trees of depth 3 is well-formed if the degree of depth-2 nodes tends to infinity
> 

## Almost constant degree
> [!PDF|red] [MSO+U, p.6](MSO+U.pdf#page=6&selection=212,27,217,25&color=red)
> > it has almost constant degree if all but finitely many depth-1 nodes have the same degre


[Lemma 3.1](Lemma%203.1.md) expresses the conjunction of being [well formed](#Well%20formed) and [almost constant degree](#Almost%20constant%20degree).

We [flatten](Flattening.md) the tree/word.
Since the degree of depth 3 nodes tends to infinity, the flattening is well formed(the degree of depth 2 nodes is now the degree of depth 3 nodes).



