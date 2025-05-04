
Turing observed that there is one [TM](Turing%20Machines.md) that can simulate any other [TM](Turing%20Machines.md) $M$, given some description of $M$ as input.

We fix the following encoding of [TMs](Turing%20Machines.md) as strings of $\lbrace 0, 1\rbrace^*$ with the following properties:

- Every string $\lbrace 0, 1\rbrace^*$ represents _some_ TM. (assign invalid encodings to some fixed TM)
- Every TM is represented by __infinitely many__ strings. (eg. ignore suffixe $01^*$) 
We denote by $M_{\alpha}$ the TM represented by $\alpha \in \lbrace 0, 1\rbrace^*$ 

