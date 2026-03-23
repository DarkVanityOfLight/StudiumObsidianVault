
A transition system is a triple $(\Gamma, \gamma_0, \to)$ where
- $\Gamma$ is a (finite or infinite) set of configurations
- $\gamma_0$ is its initial configuration
- $\to \subseteq \Gamma\times\Gamma$ is a binary relation on $\Gamma$, called transition relation

For $\gamma, \gamma' \in\Gamma$ we write $\gamma \to^*\gamma'$ if there are configurations 
$\gamma_1, \dots, \gamma_n \in\Gamma$ with
$$\gamma_1 \to \gamma_2 \to\dots \to \gamma_n$$
and $\gamma = \gamma_1$ and $\gamma' = \gamma_n$.

