A Reverse [Unit Propagation](Unit%20Propagation.md) (RUP) proof for $F$ is a sequence of [clauses](Clause.md) where each clause is implied by unit propagation by:
- The input $F$ together with
- the clauses derived so far

In practice we consider DRUP proofs which additionally allow us to use deletion steps. 



> RUP $p$-simulates [Resolution](AlgoSAT/Resolution.md) 

Assume we have a resolution step $A \lor x$ and $B \lor \neg x$ resulting in $A\lor B$. Asserting $\neg (A \lor B)$ propagates $x$ and $\neg x$ by unit propagation, hence $A\lor B$ follows by RUP, we replace each resolution step by one RUP step, showing the claim.


