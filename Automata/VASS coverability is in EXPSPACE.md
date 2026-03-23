
We assume an unary encoding for the transitions of a [VASS](Vector%20Addition%20Systems.md), the complexity does not change for binary encodings.


Let $\mathcal V = (Q, T, q_0)$ be a $d$-VASS. For $\mathbf u\in\mathbb Z^d$, we have 
$||\mathbf u|| := |\mathbf u(1)| + \dots + |\mathbf u (d)|$. We define
$$||T|| = \max\{||v|| | (q,\mathbf v, q') \in T\}$$
The size of $\mathcal V$ is defined as $d \cdot ||T|| \cdot |T| \cdot Q$.

We normalize the VASS, that is every transition is either $+ e_i, -\mathbf e_i$, if a VASS is normalized its size is $d\cdot |T|\cdot |Q|$, because $||T|| = 1$. A VASS can be normalized in polynomial time.


We can reduce the [Coverability Problem](Coverability%20Problem.md) problem to the [State Reachability](State%20Reachability.md) in VASS.

> Let $\mathcal V = (Q, T, q_0)$ be a normalized $d$-VASS and $q\in Q$. If $q$ is reachable, then $q$ is reachable with a run of length $\le (2 |Q|)^{(d+1)!}$


We define a new step relation $\to^i$ on $Q\times \mathbb Z^d$ for $i\in [0, d]$, for $(q, \mathbf u), (q', \mathbf u') \in Q\times \mathbb Z^d$, let $(q, \mathbf u) \to^i (q', \mathbf u')$ if
1. There is a transition $(q, \mathbf v, q') \in T$ with $\mathbf u' = \mathbf u + \mathbf v$
2. $\mathbf u(j) \ge 0$ and $\mathbf u'(j) \ge 0$ for $j \in[1, i]$

For $i\in [0, d]$, an $i$-run from $(q, \mathbf u)$ is a run
$$(q_1, \mathbf u_1) \to^i (q_2, \mathbf u_2) \to^i \dots\to^i (q_m, \mathbf u_m)$$
with $(q_1, \mathbf u_1) = (q, \mathbf u)$ and $q_m = q_f$, and it's length is $m-1$.

Clearly $q_f$ is reachable iff there is a $d$-run from $(q_0, \mathbf 0)$. 
For $i \in [0, d]$ and $(q, \mathbf u)\in Q\times\mathbf Z^d$, let
$$m(i, (q, \mathbf u)) := \min \{\ell + 1 | \text{there is an $i$-run from $(q, \mathbf u)$ of length $\ell$}\}$$
That is the length of the shortest $i$-run from $(q, \mathbf u)$.

If there is no $i$ run from $(q, \mathbf u)$, set $m(i, (q, \mathbf u)) = 0$.

For $i\in [0, d]$, let 
$$f(i) := \max\{m(i, (q, u)) | (q, \mathbf u ) \in Q\times\mathbb Z^d\}$$
That is the maximum shortest run length over all starting configurations.
$$f(0) \le |Q|$$

> Let $n = |Q|$. For every $i\in[0, d-1]$ 
> $$f(i+1) \le n\cdot f(i)^{i+1} + f(i) - 1.$$


Let $(q, \mathbf u) \in Q\times \mathbb Z^d$ and suppose there is an $(i+1)$-run $\rho$ from $(q, \mathbf u)$.
Then we show that there is one of length $\le n\cdot f(i)^{i+1} + f(i) -1$

1. For every configuration $(p, \mathbf v) \in Q\times\mathbb Z^d$ in $\rho$, we have $\mathbf v(j) < f(i)$ for $j\in[1, i+1]$. If two configurations $(p, \mathbf v)$ and $(p, \mathbf v')$ satisfy $p=p'$ and $\mathbf v(j) = \mathbf v'(j)$ for all $j \in [1, i+1]$, then we can cut out all steps between $(p, \mathbf v)$ and $(p', \mathbf v')$ and obtain a shorter $(i+1)-$run. There are at most $n\cdot f(i)^{i+1}$ possible choices for $p\in Q$ and the values $\mathbf v(j)$ for $j\in[1, i+1]$. Therefore, after cutting, we have a run of length $\le n \cdot f(i)^{i+1} - 1$.
2. There is a configuration $(p, \mathbf v) \in Q\times \mathbf Z^d$ in $\rho$ with $\mathbf v(j) \ge f(i)$ for some $j\in [1, i+1]$. Suppose $(p,\mathbf v)$ is the earliest such configuration. Without loss of generality, suppose $\mathbf v(i+1) \ge f(i)$. Let $(p', \mathbf v')$ be the configuration right before $(p, \mathbf v)$. We can decompose $\rho$ into three parts: $$\rho = \rho_1 \rho_2 \rho_3$$
   where $\rho_1$ is an $(i+1)$-run from $(q, \mathbf u)$ to $(p', \mathbf v')$, $\rho_2$ is a transition $(p', v') \to^i (p, \mathbf v)$ and $\rho_3$ is the rest.
   Then $\rho_1$ has the property of Case 1. Hence, by the same argument, it can be replaced by an $(i+1)$-run $\rho'_1$ of length $\le n \cdot f(i)^{i+1} - 1$. $\rho_2$ has length $1$. And we can replace $\rho_3$, let $\rho_3'$ be the minimal length $i$-run from $(p, \mathbf v)$. Since $\mathbf v(i+1) \ge f(i)$ and $\rho_3'$ is of length $\le f(i) - 1$, the $i$-run $\rho_3'$ must even be an $(i+1)$-run, a run of length $f(i) - 1$ can decrease the coordinate $i+1$ by at most $f(i) - 1$, thus $\rho'_3$ cannot reach a negative value there. This implies that $\rho' = \rho'_1 \rho_2\rho_3'$ is an $(i+1)$-run from $(q,\mathbf u)$. It has length 
   $$\le (n\cdot f(i)^{i+1} - 1) + 1 + (f(i) - 1) = n \cdot f(i)^{i+1} + f(i)-1$$
   
> $f(i) \le (2n)^{(i+1)!}$ for every $i\in [0, d]$.

By induction on $i$: $f(0) \le n \le 2n = (2n)^{1!}$. Suppose $i\ge 0$ and $f(i) \le (2n)^{(i+1)!}$
Then we have:
$$\begin{align}
f(i+1) & \le n \cdot f(i)^{i+1} + f(i) \le n \cdot ((2n)^{(i+1)!})^{i+1} + (2n)^{(i+1)!}\\
&\le 2n \cdot ((2n)^{(i+1)!})^{i+1} = (2n)^{1 + (i+1)! \cdot (i+1)}\\
&\le (2n)^{(i+1)! \cdot (i + 2)} = (2n)^{(i+2)!}
\end{align}$$


We are now ready to proof the main theorem.

Suppose $q$ is reachable. Then there is a $d$-run from $(q_0, \mathbf 0)$. It has length at most $f(d) \le (2n)^{(d+1)!} = (2|Q|)^{(d+1)!}$.

We first reduce coverability to state reachability for normalized VASS, we are given a normalized VASS $\mathcal V  = (Q, T, q_0)$ and a state $q_f\in Q$. We know that if $q_f$ is reachable, then with a run of length $(2|Q|)^{(d+1)!}$. In such a run, every configuration $(q,\mathbf u)$ must satisfy $||u|| \le (2|Q|)^{(d+1)!}$. A non deterministic algorithm:

```
Input: VASS V = (Q, T, q0) and target state qf

(q, u) := (q0, 0)
c := 0
B := (2 * |Q|)^((d + 1)!)

while c <= B do
    guess a transition tau = (q, v, q')

    if u + v is in N^d and ||u + v|| <= B then
        q := q'
        u := u + v
        c := c + 1

        if q = qf then
            report "State qf is reachable"
            halt

report "State qf is not reachable"
```

We encode all numbers in binary. Then the algorithm needs space
$$|Q| \cdot d \cdot \log ((2 |Q|)^{(d+1)!})$$

We can bound this by
$$2^{(s+3)^2}$$i