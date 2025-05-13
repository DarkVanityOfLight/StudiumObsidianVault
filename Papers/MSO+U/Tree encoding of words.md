We encode words $w = \lbrace 1, 2, 3\rbrace^\omega$ 

- The leaves of $tree(w)$ are positions with label $n$ [MSO+U, p.5](MSO+U.pdf#page=5&selection=60,21,71,0&color=red).
- Label $1$ divides depth 1 trees(makes new trees) [MSO+U, p.5](MSO+U.pdf#page=5&selection=110,17,129,37&color=red)
- Label $2$ divides depth 2 trees
- Label $3$ are leaves
- Two leaves share a common ancestor at depth $i$ if there are no labels $\le i$ between them.

This also means the mapping $w \mapsto tree(w)$ is not one to one(two or more words share the same tree) 

![Drawing 2025-05-13 21.55.48.excalidraw](Drawing%202025-05-13%2021.55.48.excalidraw.md)

The numbers are dividers rather then nodes(except leaves).
