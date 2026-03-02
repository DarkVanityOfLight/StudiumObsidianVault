
Jede von einem [Nichtdeterministischen endlichen Automaten](Nichtdeterministische%20endliche%20Automaten.md) erkennbare [Sprache](Sprache.md) kann auch von einem [Deterministischen endlichen Automaten](Deterministische%20endliche%20Automaten.md) erkannt werden.

Sei $A = (Q, \Sigma, \Delta, I, F)$ ein NFA.
Definiere den DFA(der sogenannte Potenzmengenautomat)
$$2^A = (2^Q, \Sigma, \delta, I, F)$$
wobei

$$\delta(P, a) = \lbrace q \in Q | \exists(p, a, q) \in \Delta : p\in P\rbrace \forall P\subseteq Q, a\in\Sigma$$
$$F  = \lbrace P\subset Q | P\cap F \not= \emptyset\rbrace$$


