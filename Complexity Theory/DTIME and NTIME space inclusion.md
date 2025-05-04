

$NTIME(f) \subseteq DSPACE(f)$

Consider a nondeterministic [f-time bounded](Time%20and%20Space%20bounded%20computation.md) [Turing Machine](Turing%20Machines.md) $M$, some input $x$ and the computation tree 

![](DTIME%20and%20NTIME%20space%20inclusion%202025-05-03%2013.15.02.excalidraw)

Let $m$ be the maximum number of transitions that are that are enabled from some configuration.

```
for all "direction strings" d1 ... dl in {1, ..., m}* of length <= f(|x|):
	starting from the initial configuration, compute its 
		d1 successor, then
		d2 successor, then
		...
		dl succesor
	and check wheter an accepting configuration is reached
```



So far we know:
$$L \subseteq NL \subseteq P \subseteq NP \subseteq PSPACE \subseteq NPSPACE \subseteq EXPTIME$$

