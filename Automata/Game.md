A game is defined as a tuple $\mathcal G = \langle A, \text{Win}\rangle$ where
- $A = \langle V, E\rangle$ is an [Arena](Arena.md)
- $\text{Win} \subseteq V^*$ is the winning [set](Mengen.md)

## Winning

A [play](Play.md) $\pi$ in game $\mathcal G$ is winning for Player $0$ if and only if $\pi \in \text{Win}$.
All other plays are winning for Player $1$

