The Luby sequence $(t_i)_{i\ge 1}$ is defined recursively as:
$$t_i = \begin{cases}
2^{k-1} & \text{if } i = 2^k-1\\
t_{i-2^{k-1}+1} & \text{if } 2^{k-1} \le i\le 2^k - 1
\end{cases}$$
for $k = \lceil\log_2 (i+1)\rceil$ the sequence begins as
$$1, 1, 2, 1, 1, 2, 4, 1,1,2,1,1,2,4, 8$$
before doubling, repeat the entire sequence so far.

The restart length at step $i$ is proportional to $t_i$ for some measure of time, this ensures both short and long runs occur periodically.

> A Las Vegas algorithm is a randomized algorithm that always produces the correct output

> A Monte Carlo algorithm is a randomized algorithm for which there exists a real number $\varepsilon < \frac{1}{2}$ such that for every possible input, the output is correct with probability $1-\varepsilon$

Consider a Las Vegas algorithm $A$ with unknown, random runtime distribution. Assume we repeatedly run the algorithm with time limits $(t_1, t_2, \dots)$, restarting each time the limit is exceeded. Let $T_{A, luby}$ denote the expected runtime of $A$ using the Luby sequence as time limits.

If we had full knowledge of the distribution of $A$ running on input $x$, then there exists an optimal sequence of time limits $(t^*, t^*, \dots)$ for $x$. Let $T_{A, opt}$ denote the expected runtime of $A$ using optimal sequences of time limits.

For every Las Vegas algorithm $A$, $T_{A, luby} = O(T_{A, opt}, \log T_{A, opt})$.

For any fixed restart sequence $S$, there exists an algorithm $A$ such that $T_{(A, S)} = \Omega (T_{A, opt} \log T_{A, opt})$.
The Luby sequence is only a logarithmic factor worse than the offline optimum, and there is no universal sequence with a better asymptotic worst-case.

