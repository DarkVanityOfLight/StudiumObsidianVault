>[!LEMMA]
>If $U\subseteq \Sigma^*$ is upwards closed, then $U$ is a regular language.

_Proof:_
Note that for any word $w\in \Sigma^*$ with $w = a_1, \dots, a_n, a_1,\dots, a_n \in\Sigma$ we have 
$$\{w\}\uparrow = \Sigma^* a_1 \Sigma^* \dots a_n\Sigma^*$$
hence $\{w\}\uparrow$ is a regular language.
Since $(\Sigma^*, \preceq)$ is a [WQO](Well-quasi-ordering.md), $U$ has a basis $U_0 = \{w_1, \dots, w_m\}$, then we have
$$U = \{w_1, \dots, w_n\}\uparrow = \bigcup\limits_{i=1}^m \{w_i\}\uparrow$$
hence $U$ is a regular language.

> [!THEOREM]
> If $L$ is any subset of $\Sigma^*$, then $L\downarrow$ is a [regular language](Reguläre%20Sprachen.md).

_Proof_
Suppose $L \subseteq \Sigma^*$ is an arbitrary language. Then $\Sigma^* \setminus L\downarrow$, the complement of $L\downarrow$ is upward closed. Therefore, $\Sigma^*\setminus L\downarrow$ is a regular language by our lemma. Hence $L\downarrow$ is the complement of a regular language, and thus regular.

