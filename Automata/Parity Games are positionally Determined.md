Let $\mathcal{G}$ be a parity [Game](Game.md) with maximal color $k$.
- $\mathcal G$ is positionally determined
- The players have a uniform positional winning strategies on their winning regions


> Parity games are prefix independent, that is deleting a finite prefix does not change the winner.
> This implies the following properties
> - $\sigma$ is winning from $v \in V_p$, then $\sigma$ is winning from $\sigma(v)$
> - $\sigma$ is winning from $v \in V_{1-p}$, then $\sigma$ is winning from every $v' \in vE$



---
Let 
$$W_1 := \{ v\in V | \text{Player 1 has a positional winning strategy from $v$} \}$$
> Note that from each $v\in W_1$ there might be different winning strategy, not a uniform one.


_Lemma_
We show Player $1$ has a uniform positional winning strategy $\sigma_1$ on $W_1$.

We can define a well-order $\le$ on $W_1$ because of the axiom of choice.

Now let $\sigma_w$ be the positional winning strategy from $w \in W_1$.

We call $w\in W_1$ a _companion_ of $v\in W_1$ if $\sigma_w$ is winning from $v$.
We can define the following positional strategy
$$\sigma(v) := \sigma_w(v)$$
where $w$ is the smallest companion of $v$ w.r.t $\le$.

> Because $v$ is a companion of itself this is well defined.

$\sigma$ is a uniform winning strategy for Player 1 on $W_1$.

Let $\pi = v_1v_2...$ be the play starting in $W_1$ consistent with $\sigma$
1. $\pi$ stays in $W_1$, because $\sigma$ is a winning strategy for $W_1$ and thus every node $v$ in the image of $\sigma$ must be in $W_1$ because $\sigma$ is a positional winning strategy from $v$.
2. The sequence of companions of nodes in $\pi$ is decreasing.
   $\sigma_{w_i}$ is winning from $v_i$, and therefore also from $v_{i+1}$(by prefix independence and because we are consistent with $\sigma$). So $w_i$ is a companion of $v_{i+1}$, the companion of $w_{i+1}$ is defined as the smallest companion of $v_{i+1}$ so it must be $\le w_i$.
3. Because $\le$ is a well-order there can not be an infinite decreasing subsequence, and thus eventually $w_i = w_{i+1} = ...$

---

We proceed by induction on the largest color $k$ in $G$. W.l.o.g assume $k$ is even.

We restrict the game to $V\setminus W_1$($G'$) (since $W_1$ is winning for Player 1).

Let $C_k := \{v \in V\setminus W_1 | c(v) = k\}$ the set of nodes in the new arena, with the maximal color, and the attractor $A := attr(C_k)$.

Further restrict $G'$ to the arena $V \setminus (W_1 \cup A)$, call the new game $\mathcal H$ and observe that the highest color in $\mathcal H$ is smaller then $k$. And thus the induction hypothesis applies.

We obtain winning regions $U_0$ and $U_1$ with uniform positional winning strategies $\mu_0, \mu_1$.

$U_1 = \emptyset$

Consider the following strategy $\nu_1$ for Player 1 in $\mathcal G$

- On $U_1 \cap V_1$ use $\mu_1$
- On $W_1 \cap V_1$ use $\sigma_1$ from the previous lemma
- On all other positions in $V_1$ use any positional strategy
$\nu_1$ is a positional winning strategy in $\mathcal G$ for any position in $U_1$, consider any play consistent with $\nu_1$ starting in $U_1$

- Any play from $\mu_1$ will map any position $u\in U_1$ back into $U_1$, so any play moving into $A \cup U_0$ , must come from Player $0$, but then $u$ would belong to $A \cup U_0$.
- If the play starts in $\mathcal H$, then Player 1 wins using $\mu_1$ via induction
- If the play enters $W_1$, then Player 1 wins by $\sigma_1$

So $U_1 \subseteq W_1$, by definition of $W_1$ exhibiting $\nu_1$ as proof. But since $U_1$ and $W_1$ are disjoint $U_1$ must be empty.

We can now construct a uniform positional winning strategy $\sigma_0$ on $V \setminus W_1$, using the positional attractor strategy of Player $0$ on $A$.
$$\sigma_0(v) = \begin{cases}
\mu_0(v) & \text{if } v\in U_0\\
\sigma_A(v) & \text{if } v\in A \setminus C_k\\
\text{any position in } vE\setminus W_1 &\text{if } v \in A \cap C_k\\
\text{any position in } vE & \text{otherwise}
\end{cases}$$

Any play consistent with $\sigma_0$, will either visit $A$ infinitely often, then the largest color $k$ is even and is visited infinitely often. Or the play eventually stays in $U_0$ where we use $\mu_0$
