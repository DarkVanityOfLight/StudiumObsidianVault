
Gegeben sei eine [Synchronisationsordnung](Synchronisation-Konsistenz.md#Synchronisationsordnung) $\text{S}\atop\rightarrow$ und eine [Menge](Mengen.md) an Synchronisationsereignissen $E_s$. Eine [Partielle Ordnung](Partielle%20Ordnung.md) ${\text{SW}\atop\rightarrow} \subseteq {\text{S}\atop\rightarrow}$ ist eine __synchronizes-with-Ordnung__ genau dann wenn:
1. Sei $e_{u,m}$ ein Unlock-Ereignis für Lock $m$. für jedes Lock-Ereignis $e_{l,m}$ für Lock $m$ gilt: $e_{u,m}{\text{SW}\atop\rightarrow} e_{l, m}$ genau dann wenn $e_{u, m} {\text{S}\atop\rightarrow} e_{l, m}$.
2. Seien $w$ und $r$ Schreib und Lesezugriffe auf eine `volatile` Variable, dann gilt: $w{\text{SW}\atop\rightarrow r}$ genau dann wenn $w {\text{S}\atop\rightarrow}r$

Daraus folgt dass die korrekte Abfolge von Lock/Unlock auf ein Lock $m$ eingehalten wird.