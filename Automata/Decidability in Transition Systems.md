



|                                                                                 | [Configuration Reachability](Configuration%20Reachability.md) | [Coverability](Coverability%20Problem.md) | [Termination](Termination.md) | [Boundedness](Boundedness%20Problem.md) | [Recurrent State Reachability](Recurrent%20State%20Reachability.md) |
| ------------------------------------------------------------------------------- | ------------------------------------------------------------- | ----------------------------------------- | ----------------------------- | --------------------------------------- | ------------------------------------------------------------------- |
| [Minsky Machine](d-Counter%20Automaton.md)                                      | Undecidable                                                   | Undecidable                               | Undecidable                   | Undecidable                             | Undecidable                                                         |
| (2)-[PDA](d-Pushdown%20Automaton.md)                                            | Undecidable                                                   | Undecidable                               | Undecidable                   | Undecidable                             | Undecidable                                                         |
| [Channel Systems](Channel%20Systems.md)                                         | Undecidable                                                   | Undecidable                               | Undecidable                   | Undecidable                             | Undecidable                                                         |
| [VASS](Vector%20Addition%20Systems.md)                                          | Decidable                                                     | Decidable                                 | Decidable                     | Decidable                               | Decidable                                                           |
| [Reset VASS](Reset%20VASS.md)                                                   | Undecidable                                                   | Decidable<br>(WSTS)                       | Decidable<br>(WSTS)           | Undecidable                             | Undecidable                                                         |
| [Lossy Channel Systems](Lossy%20Channel%20Systems.md)                           | Decidable<br>(coverability)                                   | Decidable<br>(WSTS)                       | Decidable<br>(WSTS)           | Undecidable                             | Undecidable                                                         |
| [Pushdown Systems](Pushdown%20Systems.md)                                       | Decidable                                                     |                                           |                               |                                         |                                                                     |
| [Integer VASS](Integer%20VASS.md)                                               | Decidable                                                     |                                           |                               |                                         |                                                                     |
| [Reversal bounded counter machines](Reversal%20bounded%20counter%20machines.md) | Decidable                                                     |                                           |                               |                                         |                                                                     |


[Abdulla's backward algorithm](Coverability%20Problem.md#Abdulla's%20backward%20algorithm), gives decidablity of the coverability problem, for WSTS with:
- decidable relation
- computable basis of $pre(\gamma\uparrow)$ 

[Termination](Termination.md) is decidable for WSTS with:
- Decidable relation
- computable post
- finitely branching



Finite behavior: 
- Coverability: decidable for “almost all” WSTS 1.2 Configuration reachability: undecidable for reset VASS decidable for lossy channel systems we will see: decidable for VASS 
Infinite behavior:
 - Termination: decidable for “almost all” WSTS 
 -  Recurrent state reachability: undecidable for reset VASS and for lossy channel systems we will see: decidable for VASS 
 - Boundedness: undecidable for reset VASS and for lossy channel systems also: decidable for VASS