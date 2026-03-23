The [FO theory](Theorien%20der%20ersten%20Stufe.md) $Th(\mathbb Z, +, <, |_m, 0, 1)$ admits quantifier elimination.

First we eliminate equalities and negations.

It then remains to show how to eliminate existential quantifiers.

For this we bring the formula under the quantifier 
$\exists y \phi(x, y)$ into disjunctive normal form
$$\phi^*(x, y) = \bigvee_{i\in I} (\psi_{i, 1} \land \dots \land \psi_{i, k_i} \land \theta_i)$$
where the formulas $\psi_{i, 1}\dots, \psi_{i, k_i}$ are linear inequalities and divisibility constraints in which $y$ occurs with a nonzero ceofficient. The $\theta_i$ formulas do not contain $y$.
Then $\varphi = \exists y\phi$ is equivalnent to
$$\bigvee_{i\in I}(\exists y (\psi_{i, 1} \land \dots \land \psi_{i, k_i} \land \theta_i)$$
and it remains to eliminate the quantifier in $\exists y(\psi_{i, 1} \land \dots \land \psi_{i, k_i})$.

Consider a formula of the form
$$\exists y (\bigwedge_{i \in I} p_i(x, y) < b_i \land \bigwedge_{k\in K} c_k | r_k(x, y))$$
where $y$ has a nonzero coefficient in every $p_i$ and $r_k$.

Rewrite
$$\exists y (\bigwedge_{i \in I} p'_i(x) < a_i y \land \bigwedge_{k\in K} c_k | (a_k y  + r'_k(x)))$$
where $a_i\in\mathbb Z\setminus \{0\}$ and $p_i', r'_k$ are linear terms.
Next we ensure that the coefficients of $y$ are positive. Let $I_+ = \{i\in I | a_i > 0\}$ and $I_- = I\setminus I_+$. Then we can rewrite

$$\exists y (\bigwedge_{i \in I_+} p'_i(x) < a_i y\land \bigwedge_{i \in I_-} - a_i y < - p_i'(x) \land \bigwedge_{k\in K} c_k | ( \epsilon_ka_k y  + \epsilon_kr'_k(x)))$$
where $\epsilon_k = 1$ if $a_k > 0$ and $\epsilon_k = - 1$ otherwise.

We obtain the following form after renaming terms.

$$\exists y (\bigwedge_{i \in I} p_i(x) < a_i y\land \bigwedge_{j \in J} a_j y < - q_j(x) \land \bigwedge_{k\in K} c_k | ( a_k y  + r_k(x)))$$

where $a_i > 0$ for all $i\in I\cup J\cup K$.
We ensure that $y$ has coefficient $A = \Pi_{i\in I \cup J\cup K} a_i$ everywhere by:
- Multiplying both sides of $p_i(x) < a_i y$ by $A / a_i$
- Multiplying both sides of $a_j y < q_j(x)$ by $A/a_j$
- Multiplying both sides of $c_k | (a_k y + r_k(x))$ by $A / a_k$

$$\exists y (\bigwedge_{i \in I} \frac{A}{a_i}p_i(x) < A y\land \bigwedge_{j \in J} A y < \frac{A}{a_j} q_j(x) \land \bigwedge_{k\in K} \frac{A}{a_k}c_k | ( A y  + \frac{A}{a_k}r_k(x)))$$

We replace $Ay$ by $z$ and add the condition $A | z$
$$\exists z (A | z \land \bigwedge_{i\in I}\frac{A}{a_i} p_i(x) < z \land \bigwedge_{j\in J} z < \frac{A}{a_j} q_j(x) \land \bigwedge_{k\in K} \frac{A}{a_k} c_k | (z + \frac{A}{a_k} r_k (x)))$$
This formula is equivalent to the original.

$z$ has coefficient $1$ everywhere. We can rewrite using new linear terms $p_i, q_j, r_k$.

$$\bigwedge_{i\in I} p_i(x) < z \land \bigwedge z < q_j(x) \land \bigwedge c_k | (z + r_k(x))$$

Intuitively we look for solutions close to $\max_{i\in I}p_i(x)$ or $\min_{j\in J} q_j(x)$

The divisibility constraints can be written as a system of congruences
$$z \equiv -r_k(x) \mod c_k \text{ for } k\in K$$
By the [Chinese remainder theorem](Chinesischer%20Restsatz.md): If the congruence system has a solution $y_0$, then the solution set is $\{y_0 + \lambda C | \lambda\in\mathbb Z\}$ where $C = lcm\{c_k | k\in K\}$.

One can construct a finite set of linear terms $S$ over $x$ such that $\exists z\phi(x, z)$ is equivalent to $\bigvee_{s\in S} \phi(x, s(x))$.


$$\phi = \bigwedge_{i\in I} p_i(x) < z \land \bigwedge z < q_j(x) \land \bigwedge c_k | (z + r_k(x))$$
If $I = J = \emptyset$, then set $S = \{0, \dots, C - 1\}$

$I\not = \emptyset$, set $S = \{p_i(x) +c |i\in I, 1 \le c\le C\}$. Suppose that $(u, v)$ is a solution of $\phi$ such that $v = \min\{v' \in\mathbb Z | \phi(u, v') \text{is true}\}$. Let $i\in I$ where $p_i(u)$ is maximal. Then $v > p_i(u)$ by the inequality in $\phi$. Furthermore $v \le p_i(u) + C$, or otherwise $(u, v- C)$ would also be a solution, contradicting the minimality of $v$. Therefore $v = p_i +c$ for some $1 \le c\le C$.

$I = \emptyset, J \not=\emptyset$ Set $S = \{q_j(x) - c | j\in J, 1 \le c \le C\}$ and follow the second case.


Then $\bigvee_{s\in S} \phi(x, s(x))$ is the desired quantifier-free formula equivalent to $\exists z\phi(x, z)$. This concludes the proof of the QE.

