
Für einen [Prozess](Prozess.md) $p_0$:

Sequentielle Ereignisse:
$e_1, e_2 \in E_0: e_1 \not = e_2 \land (e_1 \leq_0 e_2 \lor e_2 \leq_0 e_1)$

Nebenläufige Ereignisse
$e_1, e_2 \in E_0: \neg (e_1 \leq_0 e_2) \land \neg (e_2 \leq_0 e_1)$


$p_0$ ist sequentiell wenn alle Paare an Ereignissen sequentiell sind, ansonsten ist $p_0$ Nebenläufig.
$\leq_0$ ist eine [Lineare Ordnung](Lineare%20Ordnung.md) wenn $p_0$ sequentiell ist.

