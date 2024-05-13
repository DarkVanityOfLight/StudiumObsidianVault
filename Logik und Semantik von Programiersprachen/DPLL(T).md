## Offline

Naively enumerating disjuncts and invoking solvers for conjunctive formulas is not efficient, when checking satisfiability of [Theorien der ersten Stufe](Theorien%20der%20ersten%20Stufe.md), is not efficient.
DPLL(T) comibines SAT solvers and solvers for conjunctive theories.

In practice [CDCL](CDCL.md) is used instead of DPLL, but the historical name stuck.

$$x = y \land ((y=z \land \neg(x = z)) \lor x =z)$$

When running a SAT-solver returns [unsat](Unerfüllbar.md) to the [Propositional Skeleton](Propositional%20Skeleton.md) of $\varphi$, then $\varphi$ is unsatisfiable too.

$$p \land ((q\land \neg r) \lor r)$$

If the SAT-solver returns a satisfying assignment

$$p = T, q =T, r= F$$

we then run the [[Decision Procedure]] for the [theory](Theorien%20der%20ersten%20Stufe.md) on

$$\begin{align}
&p \land q \land \neg r\\
&\psi := x = y \land y = z \land x \not = z
\end{align}$$
if this is satisfiable the formula $\varphi$ is [sat](Erfüllbarkeit.md). But the above formula is unsatisfiable. So we know the negation is valid, which we add to the propositional skeleton

$$\neg q \lor \neg p \lor r$$

The SAT solver is then run on 
$$p \land ((q\land \neg r) \lor r) \land (\neg p \lor \neg q \lor r)$$
and we get the following assignment

$$p=T, q =T, r =T$$

The theory solver says SAT on the interpreted conjunction
$$x = y \land y =z \land x = z$$
Therefore the original formula is satisfiable.


```
#F is a quantifier free formula in a theory T with solver A
1. B := propositional skeleton of F
2. <asg, res> = SAT-SOLVER(B)
3. if res = UNSAT return "unsat"
4. if res = SAT,
	 F' = theory interpretation of asg
	 <F', res> = A(F')
	 if res = sat, then return "sat"
	 F := F /\ F'
	 Go to (1)
```


## Better blocking clauses

> [!PROPOSITION]
> Given an assignment $\alpha$ and an $T$-unsatisfiable $Th(\alpha)$ with a [Minimal Unsatisfiable Core](Minimal%20Unsatisfiable%20Core.md) $M\subseteq Th(\alpha)$, then $\bigvee_{t\in M}\neg t$ is a blocking clause.

## Online

We only invoke the theory solvers on full assignments, so CDCL might waste time exploring paths only to know later they are  $T$unsat.

We can invoke theory solvers on partial assignments and use theory propagation together with BCP. 

### $TH(\alpha)$ on partial assignment $\alpha$

The same definition of $Th(\alpha)$ works: unassigned variables do not appear in $Th(\alpha)$

$$Th(\alpha) := \lbrace R(\overline x : \alpha(e(R\overline (x))) =1 \rbrace \cup \lbrace \neg R(\overline x) : \alpha(e(R(\overline x))) = 0\rbrace$$

### Theory propagation

We alternate between executing BCP and Theory-Deduce till no further applications are possible. Theory Deduce is invoked on $\alpha$ represented by the current trail

```
repeat:
	while(BCP() = conflict):
		backtrack-level = ANALYZE-CONFLICT()
		if backtrack-level < 0
			return unsat
		Backtrack(backtrack-level)
	(t, res) = THEORY-DEDUCE(Th(alpha))
	Add-clauses(e(t))
until t = T
```

$t = \top$ means that $\varphi$ is sat if $\alpha$ is full, else we guess the next variable.

When `res` is unsat, the blocking requirement ($e(t)$ contradicts $\alpha$) is not needed for the partial assignments $\alpha$, so we prefer an incomplete but faster to generate clause.

THEORY-DEDUCE must be invoked on full assignments.

### Exhaustive Theory Propagation
In exhaustive theory propagation, we identify all literals $l$ over the atoms in $\varphi$ such that

$$T \vDash Th(\alpha) \to l$$

## Partial Theory propagation

Exhaustive Theory propagation is expensive, that's why we preferre partial theory propagation. We choose some easy to check condition $T \vDash Th(\alpha) \to l$ and if the premise is true, we then propagate $l$; otherwise we propagate nothing.

