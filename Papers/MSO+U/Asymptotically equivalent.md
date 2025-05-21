---
aliases:
  - asymptotic mix
---

## Asymptotically equivalent number sequences
[Asymptotically equivalent number sequences](MSO+U.pdf#page=2&selection=286,0,291,12&color=red)

Two [number sequences](Sequences.md#Number%20Sequence) are asymptotically equivalent if, no matter which finite bound you pick, either __both__ sequences eventually stay above it or __both__ fail to do so.

$$\exists N\forall n\ge N:f_n​>M\iff \exists N′ \forall n\ge N′:g_n​>M$$

## Asymptotic mix
[Asymptotic mix](MSO+U.pdf#page=2&selection=297,2,325,1&color=red)

A vector sequence $\textbf{f}$ is called an asymptotic mix of a [vector sequence](Sequences.md) $\textbf{g}$ if every $f\in \textbf{f}$ is asymptotically equivalent to some $g\in\textbf g$.

- **Pick any** $f\in\textbf{f}$.
- You must be able to find a $g\in{\bf G}$ such that for every real $M$:
    - Either both $f$ and $g$ eventually stay above $M$ (i.e. only finitely many terms $\le M$),
    - **Or** both fail to stay above $M$ (i.e. infinitely many terms $\le M$).
