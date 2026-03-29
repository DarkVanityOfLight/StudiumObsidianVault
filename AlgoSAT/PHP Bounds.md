We encode whether $m$ pigeons fit into $n$ holes, where

- [Variable](Variable.md) $p_{i, j}$ means pigeon $i$ goes to hole $j$
- Every pigeon must go to at least one hole 
  $$\bigwedge^m_{i=1} (p_{i, 1} \lor p_{i, 2} \lor\dots \lor p_{i, n})$$
- No hole can contain more than one pigeon
  $$\bigwedge^n_{k=1}\bigwedge^m_{i=1}\bigwedge^m_{j=i+1} (\overline p_{i, k} \lor \overline p_{j, k})$$
Let $PHP^m_n$ denote the CNF encoding whether $m$ pigeons fit into $n$ holes.

> [Resolution](AlgoSAT/Resolution.md) proofs of $PHP^{n+1}_n$ have size $2^\Omega(n)$

We will model resolution as a _prosecutor-defendant_ game played on a formula $F$.

The prosecutor asks about values of variables and stores them in a record, he can forget values of variables in the record.

The defendant knows the current record, and does not need to answer consistently.

Prosecutor wins whenever a conflict occurs.

More formally, the game is played in rounds. In the beginning, the record $R  =\emptyset$. Each round the prosecutor decides whether to

1. Ask about a variable $x$ not in $R$, the defendant answers $a\in\{\top, \bot\}$, the value of $x$. The answer is stored in $R = R\cup\{x = a\}$
2. Forget, meaning the prosecutor shrinks $R$ to $R' \subset R$.

The winning position of prosecutor means $R$ falsifies $F$.

We are interested in a winning strategy for prosecutor. A winning strategy is a collection of records and associated moves that lead to a winning position regardless of answers given by the defendant. We measure the complexity of a strategy in the number of records stored. This gives us a relation between winning strategies of prosecutor to resolution proofs.


> Let $F$ be an unsatisfiable CNF. If there is a resolution proof $P$ of length $m$, there is a winning strategy for prosecutor that stores $\le 3m$ records.

The strategy of prosecutor based on the resolution proof $P$ works as follows. 
We play by traversing the proof:
- Start at the empty clause $\bot$ with the empty record $R$.
- We maintain the invariant that our record $R$ will always match the negation of the clause we currently inspect in $P$.
- When the current clause is $C$, it was resolved using $x \lor D_1$ and $\overline x \lor D_2$. We ask the defendant about the value of $x$. When $x$ is $\bot$, we go to $x\lor D_1$, otherwise we go to $\overline x \lor D_2$. We forget all variables not appearing in the new clause.
- Once we reach a clause $C \in F$, we have reached a conflict.


> There is a $\delta > 0$ such that for large enough $n\in\mathbb N$ any prosecutor winning strategy requires more than $2^{\delta n}$ records.


We devise a super strategy for defendant, which forces prosecutor to store many records over many games.

Given a record $R$ we call the pigeon-hole pair $p_{i, j}$
- prohibited if $p_{i, j} = \bot$ is on record $R$
- assigned if $p_{i, j} = \top$ is on record $R$


Before the game begins, choose $n/4$ and assign them to $n/4$ holes uniformly at random.

Let $M$ denote this initial matching. Observe that partial pigeon-hole matchings correspond to partial assignments.

During the play, defendant maintains a matching $M'$ with $M\subseteq M'$. The strategy for defendant looks like the following:
- Prosecutor asks about $p_{i, j}$
	- If $i$ is already matched to some $j'$, i.e., $(i, j')\in M'$, answer $\top$ if $j=j'$ and $\bot$ otherwise
	- if $i$ is not yet matched in $M'$, answer $\bot$. Then, check the number of prohibited holes for $i$. If there is more than $n/2$ prohibited holes, choose the smallest $j^*$ not yet prohibited for $i$ that is consistent with $M'$ and update $M'\cup \{j^*\}$ else give up
- Prosecutor forgets $p_{i, j}$. If pigeon $i$ is now not assigned anymore and has fewer than $n/2$ prohibited holes, remove the matching $i$ from $M'$

We call pigeon $i$ thoroughly examined in the record $R$, when $R$ contains either:
1. $p_{i, j} = \top$ for some $j$, the pigeon is assigned to a hole
2. $p_{i, j} = \bot$ for at least $n/2$ different $j$s

> Before prosecutor wins, there will be a record with at least $n/4$ thoroughly examined pigeons.

The defendant can only loose if an update of $M'$ fails, this means there is no pigeon $i^*$ that has reached $n/2$ prohibited holes, and there is no available hole $j^*$.
Thus $|M'| \ge n/2$. Consequently, $|M' \setminus M| \ge n/4$, for each pigeon matched in $M'\setminus M$, either 1. or 2. must hold.

To finish the argument, we argue that the prosecutor strategy contains at least $2^{\delta n}$ many informative records.

We must pass through some informative record $R$. Assume we can prove the following: For any fixed informative record $R$, the probability that we reach $R$ from an initial uniform random $n/4$ matching $M$ is less than $2^{-\delta n}$ for some $\delta > 0$. We will prove an even stronger statement: We prove that the probability that the initial matching $M$ is consistent with $R$ is exponentially small. 

Assuming the above, for any winning strategy $W$:
$$\begin{align}
1 &= Pr[\exists R\in W \text{ consistent with } M]\\
&\le\sum_{R\in W} Pr[R\text{ consistent with } M]\\
&\le(\text{number of records in } W) \cdot 2^{-\delta n}
\end{align}$$


Let $R$ be a fixed informative record, and $M$ a uniform initial matching.

We denote with $R\cap M$ the pigeons that are 
- thoroughly examined in $R$ and
- matched in $M$
We first want to argue that the intersection is smaller than $n/32$ with at most exponential small probability $2^{-\delta n}$ for $\delta > 0$.

For randomly chosen $M$ and fixed $R$, we have
$$E_M[|R\cap M|] \ge n/16$$
Intuitively the expected value is sharply concentrated around $n/16$ - the probability that the intersection is smaller than, say $n/32$ is exponentially small.


Let $R$ be a fixed informative record, and $M$ a uniform random initial matching. Suppose $|R\cap M| \ge n/32$. For each pigeon $i$ in the intersection, $R$ either
1. Matches $i$ to hole $j$ or
2. prohibits $n/2$ holes.

For the $i+1$ st pigeon randomly chosen in $M$, being consistent with $R$ has probability

1. $\frac{1}{n-1}$(only one hole matches $R$)
2. $\frac{n/2}{n-i}$ (all non forbidden holes are good)

For $i\le n/32$ and large enough $n$, we get a probability less than $2/3$ in both cases. For the total probability, we thus get $(2/3)^{n/32} < 2^{-\delta n}$ for some $\delta > 0$.

For randomly chosen $M$ and fixed record $R$ we thus observe:

1. The probability that the intersection is smaller than $n/32$ is at most $2^{-\delta_1 n}$ for some $\delta_1 > 0$
2. If the intersection is at least $n/32$, the probability that $M$ is not consistent with $R$ is at most $2^{-\delta_2 n}$ for some $\delta_2 > 0$
Hence, we can bound the probability that $M$ is not consistent with any fixed record $R$ with $2^{-\delta_1 n} + 2^{-\delta_2 n} \le 2^{-\delta n}$ for some $\delta > 0$

There is a matching upper bound:
> Resolution proofs of $PHP^{n+1}_n$ have size $2^{O(n)}$


