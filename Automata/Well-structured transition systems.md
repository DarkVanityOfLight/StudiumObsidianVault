---
aliases:
  - WSTS
  - Well-structured transistion system
---

A _well-structured_ [Transition System](Transition%20System.md) (WSTS) is a tuple $(\Gamma, \gamma_0, \to, \le)$, where
- $(\Gamma, \gamma_0, \to)$ is a transition system
- $(\Gamma, \le)$ is a [WQO](Well-quasi-ordering.md)
- The relation $\le$ is _compatible_ with $\to$: For all $\gamma_1, \gamma_2, \gamma_3 \in\Gamma$, if $\gamma_1 \to \gamma_2$ and $\gamma_3 \ge \gamma_1$, then there is $\gamma_4\in\Gamma$  with $\gamma_4 \ge \gamma_2$ and $\gamma_3 \to \gamma_4$ $$
\begin{array}{ccc}
\gamma_3 & \to & {\gamma_4} \\
\downarrow\scriptstyle{\mathrm{VI}} & & \downarrow\scriptstyle{\mathrm{VI}} \\
\gamma_1 & \to & \gamma_2
\end{array}
$$

This compatibility can be extended to runs. If $\gamma_1 \to^* \gamma_2$ and $\gamma_3 \ge \gamma_1$, then there is a $\gamma_4\in\Gamma$ with $\gamma_4 \ge \gamma_2$ and $\gamma_3 \to^* \gamma_4$.
$$
\begin{array}{ccc}
\gamma_3 & \to^* & {\gamma_4} \\
\downarrow\scriptstyle{\mathrm{VI}} & & \downarrow\scriptstyle{\mathrm{VI}} \\
\gamma_1 & \to^* & \gamma_2
\end{array}
$$
