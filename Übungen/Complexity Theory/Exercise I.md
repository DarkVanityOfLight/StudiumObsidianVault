
Assume $c_1, c_2$ to be configurations $(q, u_1, i_1, u_2, i_2, \dots, u_k, i_k, v)$(use superscripts to identify between $c_1$ and $c_2$) of a Turing Machine $$M = \langle Q, \Sigma, \Gamma, \Omega, \Delta, q_0, F\rangle$$
We write $c_1 \vdash_M c_2$ iff there exists a transition in $\Delta$ such that 
$(r, a_1, \dots, a_k, s, b_1, \dots, b_k, c, d_1, \dots, d_k)$ 

The states transition correctly:
$q^1 = r$
$q^2 = p$

The working tapes change correctly
For every tape $t$ 
$u^1_t[i^1_t] = a_t$ (We read the correct symbol)
$u_t^2[i^1_t] = b_t$ (We write the correct symbol)
$\forall i. i\not = i^1_t \to u^1_t[i] = u^2_t[i]$  (The rest stays the same)

The head moves correctly
$i^1_t + d_t = i^2_t$

The output tapes is correct
$v^1.c = v^2$

--- 

Assume $|\Sigma| = kaxC$