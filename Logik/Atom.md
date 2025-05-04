---
title: Atom
aliases:
  - Atom
  - Atomare Aussage
  - atomic
tags:
---

An **atom** (or **atomic formula**) is the simplest kind of well-formed formula (wff) in logic. It cannot be broken down into smaller formulas using logical connectives.

---

## Atoms in Propositional Logic

In propositional logic, atoms are just propositional variables like:
- $P$, $Q$, $R$
- $P_1, P_2, \dots$

They stand for simple yes/no statements (e.g., "It’s raining"). You can’t split $P$ into smaller logical parts, so it’s atomic. Everything else is built by sticking atoms together with connectives.

**Example:**

> - Atomic: $P$
> - Non-atomic: $(P \land Q) \rightarrow R$

---

## Atoms in Predicate Logic

In first-order (predicate) logic, atoms are a bit richer:

- A **predicate** symbol applied to the right number of **terms**, e.g. $R(x,y)R(x, y), P(f(a),b)P(f(a), b)$.
- Sometimes called **atomic predicates**.

Here, atoms can involve function symbols and constants, but still no logical connectives or quantifiers.

**Example:**

> - Atomic: $Likes(Alice, IceCream)$
> - Non-atomic: $\exists x\, Likes(x, IceCream)$
>     

---

## Why Atoms Matter

- **Semantics:** In model theory, truth is assigned to atoms first, then extended inductively.
- **Proofs:** In sequent calculi or natural deduction, you often reduce complex formulas down to atomic assumptions.
- **Computability:** Deciding truth of an atomic formula is usually straightforward (just look up the relation in a structure).
---

## Quick Recap

1. **Propositional atom** = propositional variable $(P, Q, R)$.
2. **Predicate atom** = predicate symbol applied to terms $P(t_1, \dots, t_n)$.
3. Atoms have **no** logical connectives or quantifiers.

> _Pro tip_: When building proofs or doing semantic evaluations, always peel off connectives layer by layer until you hit atoms. Think of it like peeling an onion down to its core.
