


![The Holy Trinity.excalidraw](The%20Holy%20Trinity.excalidraw.md)

## Word
We start from an __infinite word__ $w \in \lbrace 1, 2, 3\rbrace^\omega$

## Tree
That __word__ can be interpreted as an __infinite forest__(or as bounded depth 3 tree with depths 0, 1, 2)
- 1s in the word delimit between detph 1 subtrees
- 2s delimit between depth 2 subtrees
- 3s are leaves

So a word -> tree via syntactic interpretation.

## Vector Sequence
Once we have interpreted the __word__ as __tree__, we can extract data from it.

For a given infinite set $X$ of depth 1 nodes:
- Each subtree contains a sequence of depth 2 nodes
	- Each of which has some number of depth 3 children(leaves)

So from the $i$th tree in $X$, we can extract one vector of degrees(the degree of each depth 2 subtree) 
$f_X = (v_0, v_1, v_2, ...)$ where each $v_i = (deg_i^1, deg_i^2)$





