If $(X, \le)$ is a [WQO](Well-quasi-ordering.md), then the [embedding](Embedding%20finite%20sequences.md) $(X^*, \le_*)$ is a WQO.

An infinite sequence is _minimally bad_ if the sequence is bad(there exists no good pair) and for every $i\in\mathbb N$, there is no $y_i' \in Y$ with $y_i' < y_i$ such that $y_1, \dots, y_{i-1}, y_i'$ is the beginning of an infinite bad sequence.



*Lemma*
If $(Y, \le)$ is a [Well-Founded](Well-Founded.md) [quasi-ordering](Halbordnung.md), but no WQO, then $(Y, \le)$ has a minimal bad sequence.

There must exist some bad sequence because $(Y, \le)$ is not a WQO. We then construct a minimally bad sequence $y_1, y_2, \dots$ inductively. For $i = 1, 2, \dots$ we choose $y_i$ minimal such that $y_1, \dots, y_i$ is the beginning of some infinite bad sequence. Clearly $y_1, y_2, \dots$ is a minimal bad sequence.

*Lemma*
Let $(Y, \le)$ be a quasi-ordering. If $y_1, y_2, ...$ is a minimal bad sequence in $Y$, then for $I = \lbrace y \in Y | \exists i\in \mathbb N. y< y_i\rbrace$, the pair $(I, \le)$ is a WQO.

Suppose there is an infinite bad sequence $y_1', y_2', \dots$ in $I$, then since $y_1' \in I$, there is a $y_k$ such that $y_1' < y_k$. Consider the sequence
$$y_1, \dots, y_{k-1}, y_1', y_2', \dots$$
This is a bad sequence, there can be no indices $i < j$ with $y_i' \le y_j'$ by assumption, furthermore suppose $y_i \le y_j'$ for some $i, j$ with $i\in\{1, \dots, k-1\}$. Then there is a $y_\ell$ with $y_j' < y_\ell$ and hence $y_i \le y_j' < y_\ell$. This is impossible, if $i < \ell$ this contradicts badness of $y_1, y_2, \dots$, if $\ell < i$, this contradicts minimality of $y_1, y_2, \dots$

This contradicts minimal badness of $y_1, y_2, \dots$ because $y_1' < y_k$.

We are now ready to show that $(X^*, \le_*)$ is a WQO.

The ordering is [well-founded](Well-Founded.md): Suppose $w_1, w_2, \dots$ is an infinite descending chain in $X^*$, then $|w_1| \ge |w_2| \ge \dots$ hence $|w_k| = |w_{k+1}| = |w_{k+2}|$ for some $k\in \mathbb N$ (because $(\mathbb N, \le)$ is a WQO), therefore there must be a component with an infinite strictly decreasing chain in $X$, which can not exist because $(X, \le)$ is a WQO.


Suppose $(X^*, \le_*)$ is not a WQO, by our first lemma $(X^*, \le_*)$ admits a minimal bad sequence $w_1, w_2, \dots$, let $I = \{w \in X^* | \exists i\in\mathbb N . w\le_* w_i\}$ as in lemma 2, then $(I, \le_*)$ is a WQO by the second lemma.

Since $w_1, w_2, \dots$ must be non-empty words (the empty word embeds into every word), we can write $w_i = x_i v_i$ for $x_i\in X$ and $v_i\in X^*$, then $v_i \in I$ and hence we can select an infinite ascending chain $v_{i_1}, v_{i_2}, \dots$ of $v_1, v_2, \dots$ since $(X, \le)$ is a WQO, there must be two indices $i_k, i_\ell$ with $i_k < i_\ell$ with $i_{i_k} \le x_{i_\ell}$, but then
$$w_{i_k} = x_{i_k} v_{i_k} \le_* x_{i_\ell} v_{i_\ell} = w_{i_\ell}$$
which is a contradiction.


