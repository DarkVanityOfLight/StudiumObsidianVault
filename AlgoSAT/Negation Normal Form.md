[Negation Normal Form](Digitaltechnik%20und%20Rechnerarchitektur/Negation%20Normal%20Form.md), [Negationsnormalform (NNF)](Normalformen%20in%20der%20Aussagenlogik.md#Negationsnormalform%20(NNF)) 

A formula is in NNF if:
- Each propositional variable $p$ and the negation $\overline p$ of a propositional variable are in negation normal form
- If $A$ and $B$ are in negation normal form, then so are $A\land B$ and $A\lor B$


A formula can be transformed into NNF by pushing negations inwards:

- $A \to B \equiv \neg A \lor B$
- $\overline{A \lor B} \equiv \overline A \land \overline B$
- $\overline{A \land B} \equiv \overline A \lor \overline B$
- $\overline{A \land B} \equiv \overline A \lor \overline B$
- $\overline{\overline A} \equiv A$

