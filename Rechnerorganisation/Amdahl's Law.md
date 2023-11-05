Eine generelle Messung von Verbesserung von wird durch Amdahl's Gesetz gegeben:
$$Speedup = \frac{\text{unoptimized runtime}}{\text{optimized runtime}} = \frac{T_{old}}{T_{new}}$$

Nehmen wir an das $\beta \cdot T_{old}$ Schritte mit $0 < \beta \leq 1$ nicht optimiert werden können und das die anderen $(1 - \beta) \cdot T_{old}$  Schritte um einen Faktor von $p$ Optimiert werden können.

$$T_{new} = T_{old} \left(\frac{1 - \beta}{p} + \beta\right)$$

$$\text{Speedup}(p) = \frac{p}{1 - \beta + p\beta} = \frac{1}{(1-\beta)\left(\frac{1}{p} - 1\right) + 1} < \frac{1}{\beta} = \lim_{p\to\infty} \text{Speedup}(p)$$
