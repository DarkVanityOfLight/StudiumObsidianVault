_Idea_ We build a NFA $A$ for a language $L \in \text{PSPACE}$ such that 
$$ M \text{ accepts } w \iff A_w \text{ is non-universal}$$

Assume $M$ is Linearly Bounded, meaning it only uses the input cells as space(Archieved by Paddin the Language).

A run on $M$ is a word
$$c_0\#c_1\#...\#c_m$$
with
1. $c_i \in \Gamma^* Q\Gamma$ 
2. $c_0 = q_0w$
3. $c_{i-1} \vdash c_i$ 
4. $c_m \in \Gamma^* q_f \Gamma^+$ 

We construct a NFA such that 
$$ L(A_w) = \{x \in \Omega^* | x \text{ is not an accepting computation of } M \text{ on } w\} $$
(The Language of all non accepting runs)

Observe that this is non-universal if $M$ accepts $w$

For 1. 2. 4. it is easy to construct a DFA, by taking the complement of
$$ q_0w(\#\Gamma^*Q\Gamma^+)\#\Gamma^*q_f\Gamma^+ \cap (\Gamma \cup Q)^{n+1} ((\# \Gamma \cup Q)^{n+1})^*$$

To check for a violation of condition 3. we guess a position
$c_{i-1}$ with distance $\ge 2$ to the head (state), and verifie that the symbol is not correctly copied to $c_i$ (n+2) positions later


