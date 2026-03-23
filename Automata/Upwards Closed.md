---
aliases:
  - upwards closed
---

Given a [WQO](Well-quasi-ordering.md) $(X, \le)$, for a subset $U\subseteq X$ we define the _upward closure_ of $U$ by 
$$U \uparrow := \lbrace x \in X | \exists u \in U. u \le x\rbrace$$

The upwards closure is idempotent:
$$U\uparrow\uparrow = U\uparrow$$

Clearly $U \uparrow \subseteq U\uparrow \uparrow$, conversely assume we have $x \in U\uparrow\uparrow$, then per definition there is $y \in U\uparrow$ with $y \le x$, since $y \in U\uparrow$ there is $z \in U$ with $z \le y$, by transitivity we get $z \le x$ so $x\in U\uparrow$


The upwards closure is compatible with inclusion, let $V \subseteq X$, if $U \subseteq V$ then $U\uparrow \subseteq V\uparrow$.

Let $x\in U\uparrow$, then there is $u\in U$ with $u\in U$ and $u\le x$, because $U \subseteq V$ $u$ is also in $V$, so $x \in V \uparrow$.

