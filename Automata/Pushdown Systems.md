Let $\Gamma$ be a finite stack [Alphabet](Alphabet.md) and let $\overline \Gamma = \{\overline a | a\in\Gamma\}$. The symbols $a\in \Gamma$ are push symbols and $\overline a \in\overline\Gamma$ are pop symbols.

A pushdown system $P = (Q, \Gamma, T, q_0)$ consists of 
- a finite set of states $Q$
- a finite stack alphabet $\Gamma$
- An initial state $q_0\in Q$
- A set of transitions $T\subseteq Q \times (\Gamma \cup \overline \Gamma\cup\{\varepsilon\} \times Q)$

A configuration in $P$ has the form $(q, s)\in Q\times \Gamma^*$. We have $(q, s) \to^\tau_P (q', s')$ if $\tau = (q, \alpha, q')\in T$ and
- if $\alpha = a\in\Gamma$ then $as = s'$
- if $\alpha = \overline a\in\overline\Gamma$ then $s = as'$
- if $\alpha = \varepsilon$ then $s = s'$

In comparison to pushdown automata, transitions have no labels.

Given a $d$-dim. [Integer VASS](Integer%20VASS.md) $V = (q, \Gamma, T, q_0)$ with pushdown and a state $q_f\in Q$, one can compute in polynomial time an existential Presburger formula defining $\{\mathbf u\in\mathbb Z^d | (q_0, \varepsilon, \mathbf 0) \to^* (q_f, \varepsilon, \mathbf u)\}$.

Let $T = \{\tau_1, \dots, \tau_k\}$. We construct a context free grammar $G$ over $T$ with nonterminals $A_{p, q}$ for $p, q\in Q$ such that 
$A_{p, q} \implies^*_G \sigma_1\dots\sigma_n \iff$ there is a run $(p, \varepsilon, \mathbf 0) \to^\sigma_1 \dots \to^{\sigma_n} (q, \varepsilon, \mathbf u)$.

The productions are
- $A_{p, q} \to A_{p, r} A_{r, q}$ for all $p, q, r\in Q$
- $A_{q, q} \to \varepsilon$ for all $q\in Q$
- $A_{p, q} \to \tau$ for all $\tau = (p, \varepsilon, \mathbf v, q)\in T$
- $A_{p, q} \to \tau_a A_{p', q'}$ for all $\tau_a = (p, a, \mathbf u, p')$, $\tau_{\overline a} = (q', \overline a, \mathbf v, q)\in T$

Declare $A_{q_0, q_f}$ as the start nonterminal of $G$. Let $\varphi_G(x_1, \dots, x_k)$ be an existential Presburger formula defining the [Parikh image](Parikh%20image.md) of $L(G)$. Let $\mathbf v_i\in\mathbb Z^d$ be the effect of transition $\tau_i$. Then
$$\varphi(\mathbf y) = \exists\mathbf x(\varphi_G(\mathbf x) \land \mathbf y = \sum^k_{i=1} x_i\mathbf v_i)$$

A corollayr:
> The reachability problem for $\mathbb Z$-VASS with pushdown is in NP.

If the given target configuration $(q_f, s,\mathbf u)$ does not have an empty stack add new states/transitions which pop $s$ from the stack and reach a state $q'_f$. Then $(q_f, s,\mathbf u)$ is reachable iff $(q_f',\varepsilon, \mathbf u)$ is reachable.

## Saturating PDS

We saturate a PDS, by adding transitions that preserve the reachability relation.
Then for each run $\gamma_0 \to^* \gamma_f$ we find a simple run $\gamma_0 \to^* \gamma_f$ in the saturated PDS.

```

while there exist transitions (p, a, q) and (r, ā, s) in T
      such that q --ε-->_P r
      and (p, ε, s) is not in T
do
      add (p, ε, s) to T
end while
```

$q \to^\varepsilon r$ can be tested in linear time, the while condition can be tested in polynomial time, every iteration adds a new transition to $T$, thus we have at most $|Q|^2$ iterations

> $\gamma \to^*_P \gamma'$ iff $\gamma \to^*_{\hat P} \gamma'$ 

Let $P_i = (Q, \Gamma, T_i, q_0)$ be the pushdown system after $i$ iterations. If $\gamma \to^*_{P_{i-1}} \gamma'$ then $\gamma \to^*_{P_i} \gamma'$.

Conversely, consider a run $\pi$ from $\gamma$ to $\gamma'$ in $P_i$. Assume that $(p, a, q), (r, \overline a, s) \in T_{i-1}, q\to^\varepsilon_{P_{i-1}} r$ and the transition $(p, \varepsilon, s)$ is added to $T_i$ in the $i$-th iteration.

We replace in $\pi$ every step $\gamma_1 \to^(p, \varepsilon, s)_{P_i} \gamma_2$ by a run $\gamma_1 \to^{a\overline a}_{P_{i-1}} \gamma_2$. This yields a run from $\gamma$ to $\gamma'$ in $P_{i-1}$.

> If $\gamma \to^{ua\overline a v}_{\hat P} \gamma'$ then $\gamma \to^{uv}_{\hat P} \gamma'$, for all $u, v \in (\Gamma \cup \overline \Gamma)^*, a\in\Gamma$.

$\hat P$ has the following property: If $(p, a, q), (r, \overline a, s)\in\hat T$ and $q \to^\varepsilon_{\hat P} r$ then $(p, \varepsilon, s)\in \hat T$. Hence any run
$$\gamma \to^u_{\hat P} (p, w) \to^a_{\hat P} (q, aw) \to^\varepsilon_{\hat P} (r, aw) \to^{\overline a}_{\hat P} (s, w) \to^v_{\hat P} \gamma'$$
can be shortened to
$$\gamma \to^u_{\hat P} (p, w) \to^\varepsilon_{\hat P} (s, w) \to^v_{\hat P} \gamma'$$

> Given a pushdown system $P = (Q, \Gamma, T, q_0)$, one can compute in polynomial time a pushdown system $\hat P = (Q, \Gamma, \hat T, q_0)$ with $\hat T \supseteq T$ such that for all configurations $\gamma, \gamma'$ we have:
> $$\gamma \to^*\gamma' \iff \text{ there exists } w\in(\overline \Gamma)^*\Gamma^*\text{ such that } \gamma\to^w_{\hat P} \gamma'$$

The backward direction follows from the correctness lemma. For the forward direction we show that $\gamma \to^w_{\hat P} \gamma'$ implies $\gamma \to^{\hat w}_{\hat P} \gamma'$ for some $\hat w \in (\overline \Gamma)^*\Gamma^*$. By induction on $|w|$:
- If $w = \varepsilon$ then $w\in(\overline \Gamma)^*\Gamma^*$
- If $w\not\in(\overline \Gamma)^*\Gamma^*$ then $w = w_1 a\overline b w_2$ for some $a, b\in\Gamma$. Clearly we must have $a = b$. By the previous lemma we know $\gamma \to^{w_1, w_2}_{\hat P} \gamma'$, and by induction we obtain $\gamma \to^{\hat w}_{\hat P} \gamma'$ with $\hat w\in(\overline\Gamma)^*\Gamma^*$.

> The reachability problem for pushdown systems is decidable in polynomial time.

Given a pushdown system $P$. We can assume that the target configuration of the form $(q, \varepsilon)$: If the target configuration is $(q, w)$, extend $P$ by a sequence of popping transitions to a new state $q_f$, so that $(q, w)$ is reachable iff $(q_f, \varepsilon)$ is reachable.
First we compute the saturated pushdown system $\hat P$ in polynomial time. To test wheter $(q_0,\varepsilon) \to^* (q, \varepsilon)$, it suffices to check whether $q_0 \to^\varepsilon_{\hat P} q$, which can be decided in linear time.

