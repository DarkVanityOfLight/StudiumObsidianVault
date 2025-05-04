---
title: Term
aliases:
  - Terms
  - Logical Term
tags:
---
A **term** is a syntactic construct used to refer to objects in the [Domain](Domain.md) of discourse. Terms can appear inside atomic formulas (predicates) and serve as the "nouns" of logical language.

---

## Types of Terms

1. **Variables**: Symbols that range over elements of the domain.
2. **Constants**: Symbols denoting specific, fixed elements in the domain.
3. **Function Applications**: A function symbol applied to one or more argument terms, yielding another term.
    - If `f` is an n-ary function symbol and $t_1, \dots, t_n$ are terms, then $f(t_1, \dots, t_n)$ is a term.
---

## Formation Rules

- **Base**: Every variable and constant is a term.
- **Induction**: If $t_1, \dots, t_n$ are terms and $f$ is an n‑ary function symbol, then $f(t_1, \dots, t_n)$ is a term.

In formal grammar notation:

```
Term ::= Variable
       | Constant
       | FunctionSymbol"(" TermList ")"

TermList ::= Term
           | Term "," TermList
```

---

## Role in Formulas

- Terms **fill** the argument places of predicate symbols to form **atomic formulas**, e.g.:
    ```
    Likes(Alice, x)
    
    Plus(x, succ(y)) > 5
    ```
- Substitution of terms for variables underlies most proof techniques (e.g., universal instantiation).

---

## Quick Recap

1. **Variables** and **constants** are base terms.
2. **Function applications** build composite terms.
3. Terms are the “nouns” that populate predicates in atomic formulas.

> _Pro tip_: When parsing or manipulating formulas, always validate that each argument of a predicate or function is indeed a well-formed term according to your signature.

