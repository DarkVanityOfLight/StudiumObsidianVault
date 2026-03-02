## Motivation
- [Complexity Classes](Complexity%20Classes.md) like [[DTIME(f)]] should ideally ignore constant factors.
- Otherwise, closure under composition becomes ugly.

## Tape Compression

For any $\varepsilon > 0$ we have $XSPACE(s) \subseteq XSPACE(\varepsilon \cdot s)$ for $X\in\lbrace D, S\rbrace$
__Idea:__ Pack $k$ symbols into macro-symbols to simulate fewer steps.

## Linear Speedup

For all $c > 0$ we have $DTIME(c \cdot n) \subseteq DTIME(O(n))$.
__Idea:__ Again, compress input and simulate $k$ steps in one macro-step.

**Note:**  
Also holds for nondeterministic machines!

## See Also
- [Time and Space bounded computation](Time%20and%20Space%20bounded%20computation.md)
- [Complexity Classes](Complexity%20Classes.md)
