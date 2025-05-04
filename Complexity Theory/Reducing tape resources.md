
## Tape alphabet
For every [TM](Turing%20Machines.md) there exists a TM $\overline M$ with the alphabet $\lbrace 0, 1,\square\rbrace$ [computing](Turing%20Machines.md#Configurations%20&%20Computations) the same function.
If $M$ is [t-time bounded](Time%20and%20Space%20bounded%20computation.md) then $\overline M$ is $O(t(n))$-time bounded.

> Encode the tape alphabet in binary in $\log \Gamma$ bits



## k-Tape to 1-tape
For every $k$-tape TM there exists a 1-tape TM $M'$ computing the same function.

Furthermore, if $M$ runs in space $s(n)$ and time $t(n)$ $M'$ runs in space $O(s(n))$ and time $O(t(n)^2)$

![](Reducing%20tape%20resources%202025-05-03%2013.29.28.excalidraw)


Thus $XSPACE(s) = XSPACE_{1-tape}(s)$
$XTIME(t) \subseteq XTIME_{1-tape}(t^2)$

# k-tape to 2-tape
There exists a 2-tape deterministic. TM $U$ such that for all 
$x, \alpha\in\lbrace 0, 1\rbrace^*$, $U(\langle \alpha, x\rangle) = M_\alpha(x)$.

If $M_{\alpha}$ halts on input $x$ in time $t$ and space $s$, then $U$ halts on input $\langle \alpha,x \rangle$ in time $c\cdot t\cdot \log t$ and space $c\cdot s$, where $c$ is a constant depending on $M_\alpha$ and not on $x$.

$U$ uses $2$ Tapes (besides input/output) 
1. Maintain tape $0$ used to store $k$ tapes
2. Scratch tape to copy blocks in time $O(d+l)$ with $d$ being the distance and $l$ being the length of the block to copy
On the main tape we can without loss of generality assume an arbitrary large tape alphabet([tape alphabet translation](#Tape%20alphabet)).

Instead of moving the head as in [k-Tape to 1-tape](#k-Tape%20to%201-tape) we move tapes. Such that all heads on the "actuall" tape align.

We periodically create "space" so that shifts only change a few cells.

We focus on a single tape:

![](Reducing%20tape%20resources%202025-05-03%2014.27.47.excalidraw)

Cells are indexed by integers:
- Cell $0$ is the home cell
- $R_i = \lbrace 2^{i+1} -1, \dots, 2^{i+2}-2\rbrace$
- $L_i = \lbrace -2^{i+1} +2, \dots, -2^{i+2}+1\rbrace$

Each cell contains some symbol from the tape alphabet $\Gamma$ or a special empty symbol $\diamond$.

We maintain the following invariants:
- Each Zone $R_i/L_i$ is either empty, half full, or full, i.e. number of $\Gamma$ symbols is $0$, $2^{i}$ or $2^{i+1}$
- Either both $L_i$ and $R_i$ are halfull or
	- $L_i$ is empty and $R_i$ is full
	- $L_i$ is full and $R_i$ is empty

The home cell always contains a $\Gamma$ symbol.

__Performing a left-shift__
- Memorize the symbol in the home cell
- Find the minimal $i_0$ such that $R_{i_0}$ is not empty(call $i_0$ the index)
- Shift the $2^{i_0}$ leftmost symbols from $R_{i_0}$ into the home cell and into the empty zones $R_0, \dots R_{i_0 - 1}$, making each zone half full.
- For $j = i_0-1, \dots, 0$ shift all $2^{j+1}$ symbols from $L_j$  to $L_{j+1}$
- Write symbol originally in the home cell into $L_0$ 

The invariants are maintained.
A single shift takes $O(2^{i_0})$

Every shift of index $i$ is followed by a sequence of $2^{i-1}$ shifts of index $<i$.

__Proof__
- An index shift requires that all zones $R_0, \dots, R_{i-1}$ or $L_0, \dots, L_{i-1}$ are empty.
- An index $i$ shift only changes zones $R_0, \dots, R_i, L_0,\dots, L_i$$

At the next index $\ge i$-shift all $2^{i+1}-2$ symbols from $L_0, \dots, L_{i-1}, R_0, \dots, R_{i-1}$ must be moved into either the left half or right half. Thus $2^i -1$ steps are needed.

Therefore only $\frac{1}{2} i$ fraction of all shifts have index $i$, that means the shifts of index $i$ only take amortized constant time per simulation step.

We perform $k\cdot t(|x|)$ shifts and the maximal index is $\log(t(|x|))$, thus the total running time is $O(t \cdot \log t)$


