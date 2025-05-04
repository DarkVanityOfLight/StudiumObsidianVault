---
title: Model Theory
aliases:
  - Model-Theoretic-Semantics
tags:
  - logic
  - semantics
  - predicate_logic
  - model_theory
---


## 1. Structure and Model

- A [Signatur](Logik/Signatur.md) (or **language**) $\mathcal{L}$ consists of:
    - A set of **constant symbols** $d, \dots$
    - A set of **function symbols** $f, g, \dots$ with specified arities
    - A set of **relation symbols** $R, S, \dots$ with arities
- An **$\mathcal{L}$-structure** (or **model**) $\mathcal{M} = (D, I)$ comprises:
    1. A [Domain](Domain.md) (universe) $D$.
    2. An [[Interpretation]] $I$ that assigns:
        - Each constant $c$ to an element $c^I \in D$.
        - Each $n$-ary function $f$ to a function $f^I: D^n o D$.
        - Each $n$-ary relation $R$ to a relation $R^I \subseteq D^n$.

---

## Satisfaction and Truth

- **Valuation**: A variable assignment $v$ maps each variable to an element of $D$.
- **Satisfaction** $(\mathcal{M}, v \models \phi)$: Defined inductively:
    1. If $\phi$ is [atomic](Logik/Atom.md), evaluate via $I$ and $v$.
    2. Composed formulas ($\land, \lor, \neg$) follow standard Boolean rules.
    3. Quantifiers:
	     - $\mathcal {M}, v \models \forall x, \phi(x)$ iff for all $d \in D$, $\mathcal{M}, v[x\mapsto d] \models \phi$.
        - $\mathcal{M}, v \models \exists x,\phi(x)$ iff some $d \in D$ makes $\mathcal{M}, v[x\mapsto d] \models \phi$.
- A sentence $\phi$ is **true in** $\mathcal{M}$ (written $\mathcal{M} \models \phi$) if $\mathcal{M}, v \models \phi$ for every $v$.

---

## Elementary Classes and Theories

- An **$\mathcal{L}$-theory** $T$ is a set of $\mathcal{L}$-sentences.
- A structure $\mathcal{M}$ is a **model of $T$** (denoted $\mathcal{M} \models T$) if it satisfies every sentence in $T$.
- A class of structures is **elementary** if it’s the class of all models of some theory $T$.
    

---

## Key Concepts

1. **Elementary Equivalence** ($\equiv$): $\mathcal{M} \equiv \mathcal{N} $if they satisfy exactly the same $\mathcal{L}$-sentences.
2. **Elementary Embedding**: A map preserving truth of every formula.
3. [Compactness Theorem](Kompaktheitssatz%20der%20Prädikatenlogik.md): A theory $T$ is satisfiable iff every finite subset of $T$ is satisfiable.
4. [Löwenheim–Skolem Theorems](Satz%20von%20Löwenheim-Skolem.md):
    - **Downward**: If $T$ has an infinite model, it has one of any smaller infinite cardinality $\le$ |signature|.
    - **Upward**: If $T$ has an infinite model, it has larger ones of any bigger cardinality.

---


## 6. Quick Recap

1. **Models** connect syntax (formulas) to semantics (truth in structures).
2. **Theories** are sets of sentences; models of a theory form elementary classes.
3. **Compactness** and **Löwenheim–Skolem** reveal surprising infinities in first-order logic.

> _Pro tip_: Use compactness to build non-standard models (e.g., non-standard naturals) by adding “infinite” axioms finitely.

---
