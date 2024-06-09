>[!DEFINITION]
> Given an [integer linear system](Linear%20Integer%20Arithmetic.md) $S$, its relaxation is $S$ without the integrality requirement
> We denote the relaxed problem of $S$ by $\text{relaxed}(S)$. 

We assume the existence of a decision procedure $LP_{feasible}$, which receives a linear system $S$ as input, and returns Unsatisfiable if $S$ is unsatisfiable and a satisfying assignment otherwise, this could be implemented using [Simplex](Simplex.md).

The algorithm goes as follows:

```ocaml
(*
Input: An integer linear system $S$
Output: Satisfiable if $S$ is satisifiable and Unsatisfiable otherwise
*)
let SEARCHINTEGRALSOLUTIONS(S) = 
	let res = LPfeasible (relaxed S) in
	if res = Unsat then return;
	else
		if res is integral then
			raise Satisfiable (*Lule*)
		else
			(*Select a variable v,
			that is assigned a nonintegral value v*)
			SEARCHINTEGRALSOLUTIONS(union S (v <= floor(r)))
			SEARCHINTEGRALSOLUTIONS(union S (v >= ceil(r)))

let FEASIBILITYBRANCHANDBOUND(S) =
	SEARCHINTEGRALSOLUTIONS S
	UNSAT
```

If the relaxed problem is unsatisfiable, it backtracks because there is also no integer solution in this branch. If, there is a solution to the relaxed problem, if the solution from $LP_{feasible}$ is integral we terminate, otherwise we split into two subproblems, adding additional constraints.

