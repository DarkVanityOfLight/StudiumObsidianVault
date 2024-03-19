
## Motivation

Es kann passieren, dass nebenläufige Prozesse auf einem einzelnem Core/Prozessor ausgeführt werden.

Dann muss sich für eine Reihenfolge der nebenläufigen Ereignisse Entschieden werden.

## Definition

Ein [Prozess](Prozess.md) $p_1 = (E_1, \leq_1, \alpha_1)$ heißt __Sequentialisierung__ von $p_0 = (E_0, \leq_0, \alpha_0)$ gdw.
- $E_1 = E_0$
- $\forall e, e' \in E_1. (e \leq_1 e' \implies e \leq_0 e')$
- $\alpha_1 = \alpha_0$

Falls der Prozess $p_1$ sequentiell ist, dann ist die Sequentialisierung vollständig.

