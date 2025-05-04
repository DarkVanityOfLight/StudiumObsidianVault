---
aliases:
  - time bounded
  - space bounded
  - f-time bounded
  - f-space bounded
---


**Recall:**
- [[Big-O Notation|O(f)]], [[Big-Omega Notation|\Omega(f)]], [[Little-o Notation|o(f)]] — standard asymptotic notation
- $n^{O(1)}$ — polynomial functions
- $2^{O(f(n))}$ — exponential functions


## Definitions
- **Configuration length**: Maximum length of the words on the read-write tapes.
- **Computation length**: Number of steps in the computation (length of the sequence).
- **Computation space**: Maximal size of any configuration during computation.

### Formal Definitions
- A [TM](Turing%20Machines.md) is **$f$-time bounded** if it halts in $\max(f(n), 2n+1)$ steps.
- A [TM](Turing%20Machines.md) is **$f$-space bounded** if it uses at most $\max(f(n), 1)$ space.
  
>[!IMPORTANT]
>Time and space bounds are made "safe" by ensuring minimums ($2n+1$, $1$) so TMs have enough to read the full input.


---

## Bounding Machines

For $f: \mathbb{N} \to \mathbb{N}$:
- A [Turing Machine](Turing%20Machines.md) is **$f$-time bounded** if, for every input $x$, every [computation](Turing%20Machines.md#Configurations%20&%20Computations) on $x$ has length $\leq f(|x|)$.
- Similarly: **$f$-space bounded** if space usage is $\leq f(|x|)$.



