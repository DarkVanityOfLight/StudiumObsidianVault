Der Shannon-operator($if-then-else$ Operator) funktioniert wie ein herkömmliches $if-then-else$ in den meisten Programmiersprachen.

## Boolscher Ausdruck

Der Shannon-Operator kann folgendermaßen in herkömmlichen Booleschen Operatoren dargestellt werden:

$$(\alpha \implies \beta|\gamma): \iff\alpha \land \beta \lor \neg\alpha\land\gamma$$

$$\begin{align*}
\neg\varphi\iff(\varphi\implies0|1)\\
\varphi \land \uppsi \iff (\varphi \implies \uppsi|0)\\
\varphi\lor\uppsi \iff (\varphi \implies 1|\uppsi)
\end{align*}$$