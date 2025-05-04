
- [[DTIME(f)]] = { languages accepted by deterministic, $f$-time bounded TMs }
- [[NTIME(f)]] = { languages accepted by nondeterministic, $f$-time bounded TMs }
- [[DSPACE(f)]] = { languages accepted by deterministic, $f$-space bounded TMs }
- [[NSPACE(f)]] = { languages accepted by nondeterministic, $f$-space bounded TMs }

## Important Special Cases

- [[L (complexity class)]] = $DSPACE(\log n)$
- [[NL]] = $NSPACE(\log n)$
- [[P]] = $DTIME(n^{O(1)})$ = $\bigcup_{f \in n^{O(1)}} DTIME(f)$
- [[NP]] = $NTIME(n^{O(1)})$
- [[NPSPACE]] = $NSPACE(n^{O(1)})$
- [[EXPTIME]] = $DTIME(2^{n^{O(1)}})$


## Relationships
![](Complexity%20Classes%202025-04-27%2018.47.59.excalidraw)

(In $t$ steps we can touch at most $t$ cells)