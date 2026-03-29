

$$\frac{(x \lor x_1 \lor \dots \lor x_n) \quad (\overline x_1 \lor x') \quad (\overline x_2 \lor x') \dots (\overline x_n \lor x')}{(x\lor x')}$$

![all_slides_handout_experimental, p.31](all_slides_handout_experimental.pdf#page=341&rect=16,81,349,189)

HBR is [confluent](Confluence.md). It combines multiple [Resolution](AlgoSAT/Resolution.md) steps into one.

## Non-transitive Hyper Binary Resolution

A problem with classic HBR is that it adds many transitive binary clauses, thus we might want to add only non-transitive hyper binary resolvents. This can be implemented using an alternative unit propagation style.

