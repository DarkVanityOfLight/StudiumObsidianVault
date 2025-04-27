
__Recall__: $O(f), \Omega(f), o(f), n^{O(1)}, 2^{O(f(n))}$

The length of a configuration is the maximal length of the words on its read-write tapes.

The duration/length(space) of a computation is the length of the sequence (maximal length of a configuration)

Let $f: \mathbb N \to \mathbb N$ then A TM is $f$-time bounded if for every input $x$, every computation on $x$ has length at most $f(|x|)$. Similarly: $f$-space bounded.

- $DTIME(f) = \lbrace L(M) | M\text{ deterministic and f-time bounded}\rbrace$
- $NTIME(f) = \lbrace L(M) | M\text{ non deterministic and f-time bounded}\rbrace$
- $DPSACE(f)  = \lbrace L(M) | M\text{ deterministic and f-space bounded}\rbrace$
- $NSPACE(f) = \lbrace L(M) | M\text{ non deterministic and f-space bounded}\rbrace$


- $L = DSPACE(\log n)$
- $NL = NSPACE(\log n)$
- $P = DTIME(n^{O(1)}) = \bigcup_{f\in F} DTIME(f)$
- $NP = NTIME(n^{O(1)})$
- $NPSPACE = NSPACE(n^{O(1)})$
- $EXPTIME = DTIME(2^{n^{O(1)})}$
