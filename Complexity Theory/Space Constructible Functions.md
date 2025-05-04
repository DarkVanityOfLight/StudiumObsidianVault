---
aliases:
  - space constructible
tags:
  - complexity
  - space_constructible
---

## Definition
- A function $s : \mathbb{N} \to \mathbb{N}$ is **space-constructible** if a [TM](Turing%20Machines.md) can [compute](Turing%20Machines.md#Configurations%20&%20Computations) $s(n)$ using $O(s(n))$ space.

**Examples**:
- $n$, $\log n$, $n^2$ are all space-constructible.

## Importance
- If $s$ is not constructible, a TM might not know how much space it can legally use!

## Space Simulation
- For space-constructible $s$:
  $$
  NSPACE(s) \subseteq DTIME(2^{O(s(n))})
  $$
- Simulate a nondeterministic machine by exploring the configuration graph.

## See Also
- [[Tape Compression and Linear Speedup]]
- [[Complexity Classes Overview]]
