
Given two [VASS](Vector%20Addition%20Systems.md) $\mathcal V_1$ and $\mathcal V_2$, it is undecidable to check $Reach(\mathcal V_1) = Reach(\mathcal V_2)$ ([Reachability Set](Reachability%20Set.md)).

We reduce from the global state reachability of deterministic [Minsky Machines](Minsky%20Machine.md). 

It is easy to construct a VASS $\mathcal V$ which simulates a D2CM $\mathcal M$ when allowed to make a mistake on the zero test.
We construct $\mathcal V_1$ and $\mathcal V_2$ from $\mathcal V$, by addressing the following issues:
1. If a mistake is made on a zero test, how can it be reflected in the set Reach
2. How can we ensure that $Reach(\mathcal V_1) = Reach(\mathcal V_2) \iff \mathcal M$ cannot reach $q_f$

Let $\mathcal M = (Q, T, q_0)$ with a designated final state $_f$ where $T$ has transitions of the following forms:
- (t1) $q\to^{+e_k}q'$
- (t2) $q\to^{z_k}, q\to^{-e_k}q''$
In the second case, the initial state $q$ is the same in both transitions. We will write $c++$, $c--$ on a transition with the assumption that there is some intermediate state which is not of importance. 
Define the VASS $\mathcal V = (Q', T', q'_0)$ as follows:
- Retain each transition of type t1
- For a transition of type t2, add $t^z_i = (q \to^0 q')$, $t^{NZ}_i = (q \to^{-e_k} q'')$ and $t'_i = (q \to^{-e_k, + e_k} q')$

The transitions $t'_i$ are said to be _definitely cheating_.

We construct an VASS $\mathcal V'$ from $\mathcal V$, which we will then modify to obtain $\mathcal V_1$ and $\mathcal V_2$.
- Add 5 additional counters $r_1, r_2, STEPS, TNZ, DOUBLE$
- Initialize $r_1$ to $1$, other four counters to $0$
- Modify each transition in $\mathcal V$ to incremenet $r_2$, $STEPS$ and decrement $r_1$. If the transition is a $t_i^{NZ}$, then also increment $TNZ$.
- For each state $q$ of $\mathcal V$ do the following: Replace the state with two copies $q^{in}$ and $q^{out}$, modify each transition such that incoming transitions come into $q^{in}$ and outgoing transitions go out of $q^{out}$, and add the following transitions:
![](Undecidability%20of%20VASS%20reachability%20set%20equality%202026-03-12%2014.34.27.excalidraw)

With 
- $\mathbf v_1 = r_2 --, TNZ --, r_2++, DOUBLE += 2$
- $\mathbf v_2 = r_2 --, r_1++$
- $\mathbf v_3 = r_1--, DOUBLE--, r_1++, TNZ++$

This gadget enables us to double the number of tokens in the counter $TNZ$ after each transition of $\mathcal V$, the number of tokens in $r_1$ and $r_2$ always add up to $1$. While executing a transition in $\mathcal V$, we move the token from $r_1$ to $r_2$ in $\mathcal V'$ while incrementing $STEPS$. If it is a $t_i^{NZ}$ transition, we also increment $TNZ$. The loop on $q^{in}$ verifies that $r_2$ contains a token, then puts two tokens in $DOUBLE$ for each token $TNZ$. We then shift back the token back to $r_1$ from $r_2$ and mvoe to $q^{out}$. At $q^{out}$, we are allowed to shift tokens from $DOUBLE$ to $TNZ$.

> Suppose the unique computation in $\mathcal M$ reaching $q_f$ takes $k$ steps. Then $\sigma = t^1\sigma_u^1t^2\sigma^2_u\dots t^k\sigma^k_u$ is allowed in $\mathcal V'$, where the $t^i$ are counted transitions(which lead to incrementing $STEPS$) which are noncheating and the $\sigma^i_u$ are instances of $\sigma_u$ which causes the maximum possible increase of $TNZ$. Let $C$ be the configuration reached at the end of $\sigma$ and $C'$ be the configuration reached at the end of any other run $\sigma'$ which contains $k$ counted transitions. Then $C'(TNZ) < C(TNZ)$.

It suffices to consider $\sigma'$ which use instances of $\sigma_u$ which maximally increase $TNZ$. Hence we can assume that $\sigma' = z^1\sigma_u^1z^2\sigma^2_u \dots z^k\sigma^k_u$. Observe that if the bit representation of $C'(TNZ) = b_1b_2\dots b_{k+1}$ then $b_i = 1$ iff $z^i$ is some $t_j^{NZ}$. Furthermore, $\sigma'$ can only differ from $\sigma$ on a $t_j^{NZ}$ transition at the first place where they differ: instead it uses $t_j^Z$ or $t_j'$. In this case, the corresponding bit in $C'(TNZ)$ is a $0$ instead of a $1$ in $C(TNZ)$. Since this bit can never be changed later in the computation, the lemma follows.


To $\mathcal V'$, add two more counters $p, p'$ and initialzie them with $1, 0$ tokens respectively. Modify each definitely cheating transition $t'_i$ to also shift the token from $p$ to $p'$ and add a new state $q'_f$ and a transition $t_a = (q_f^{out} \to^0 q_f)$. At this point, we have constructed $\mathcal V_1$. To $\mathcal V_1$ add the transition $t_b = (q_f^{out} \to^{p--, p'++} q_f')$ to get $\mathcal V_2$.

We will now show that $\mathcal M$ halts iff $Reach(\mathcal V_1) \not = Reach(\mathcal V_2)$.

$\mathcal M$ halts: Consider the correct simulation $\sigma = t^1\sigma^{1}_{u} t^2 \sigma^{2}_{u} \dots t^k\sigma^k_{u} t^{k+1}$ where $t^{k+1} = t_b$ in $\mathcal V_2$. Let $C$ be the configuration at the end. Consider any $\sigma'$ in $\mathcal V_1$ which ends in the same configuration $C$: it has to contain exactly $k$ counted transitions since $C(STEPS) = k$. Furthermore, $\sigma'$ has to attain $C(TNZ)$ and by the gadget lemma, it has to have a prefix $t^1 \sigma^1_u t^2_u\dots t^k\sigma^k_u$. But only $t_a$ can be applied in $\mathcal V_1$ which implies that the token cannot be shifted from $p$ to $p'$.

$\mathcal M$ does not halt: Note that $t_b$ can be used at most once in $\mathcal V_2$. Let $\sigma'$ be any sequence ending with $t_b$: It cannot have any definitely cheating transitions because this moves the token from $p$ to $p'$. However, since there is no run in $\mathcal M$ to $q_f$, this means $\sigma'$ must have cheated on a $t_i^Z$ transition. The same configuration can be reached in $\mathcal V_1$ by replacing $t_i^Z$ by $t_i'$ and the final $t_b$ by $t_a$.
