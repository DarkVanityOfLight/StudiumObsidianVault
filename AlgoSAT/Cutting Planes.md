0-1 integer linear inequalities have the form
$$\sum_i a_i \ell_i \ge A$$

With coefficients and threshold $a_i, A \in \mathbb Z$.

We can encode [literals](AlgoSAT/Literal.md) $\ell_i$ as boolean
$$\ell_i \in \{x_i, \overline x_i\} \quad x_i + \overline x_i = 1$$

We can derive the following [proof system](Proof%20of%20Unsatisfiability.md) for cutting planes:

$$\text{INPUT}\frac{}{\text{contraint from input}}$$
$$\text{LITERAL}\frac{}{\ell_i \ge 0}$$
$$\text{ADDITION}\frac{\sum_i a_i \ell_i \ge A \quad \sum_i b_i\ell_i \ge B}{\sum_i(a_i + b_i)\ell_i \ge A + B}$$
$$\text{MULTIPLICATION}\frac{\sum_i a_i \ell_i \ge A }{\sum_i( c a_i + b_i)\ell_i \ge cA }(c\in\mathbb N^+)$$

$$\text{MULTIPLICATION}\frac{\sum_i a_i \ell_i \ge A }{\sum_i( \lceil \frac{a_i}{c}\rceil + b_i)\ell_i \ge \lceil \frac{A}{c}\rceil }(c\in\mathbb N^+)$$


Using Cutting Planes we can simulate resolution

$$\frac{y\lor z \quad x \lor y\lor \overline z}{x \lor y}$$
to
$$\frac{y+z \ge 1 \quad x + y + \overline z \ge 1}{\frac{x + 2y \ge 1}{x + y \ge 1}}$$

## RUP
We can extend [Reverse Unit Propagation Proofs](Reverse%20Unit%20Propagation%20Proofs.md) to [pseudo-boolean](AlgoSAT/Cutting%20Planes.md) constraints. We define what it means to propagate pseudo-Boolean constraints.

- A constraint $C$ propagates a variable if setting $x$ to the wrong value makes $C$ unsatisfiable.


Let $C$ be a pseudo-Boolean constraint
$$C: \sum_i a_i\ell_i \ge A, a_i, A\in\mathbb Z_{\ge 0} \quad \ell_i\in\{x_i, \overline x_i\}$$

For a partial assignment $\alpha$, define the maximum achievable value
$$\max_{\alpha}(C) := \sum_{\alpha(l_i) \not = 0} a_i$$

The slack of $C$ under $\alpha$ is 
$$slack_{\alpha}(C) := \max_\alpha(C) - A$$

A literal $\ell_j$ propagates under $\alpha$ if
$$\alpha(\ell_j) \text{ is unassigned and } \max_\alpha(C) - a_j < A$$

