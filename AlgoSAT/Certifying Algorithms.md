An algorithm takes an input $x$ and produces output $y$, a _certifying_ algorithm additionally produces a witness $w$, which a simple checker algorithm can check efficiently using $x$ and $w$.

Certifying satisfiability of a [formula](Formula.md) is easy, we just give the assignment. However certifying unsatisfiability is not so easy:
If a formula has $n$ variables, there are $2^n$ possible assignments. 