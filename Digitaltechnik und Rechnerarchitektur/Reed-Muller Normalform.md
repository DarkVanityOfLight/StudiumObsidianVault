Die Reed-Muller Normalform besteht aus mit $\oplus$ Verknüpfte $\land$ Termen.

$$\oplus^n_{i=1}\bigwedge^{m_i}_{j=1} x_{i,j}$$


## Mixed Polarity
Negationen dürfen in den Mintermen auftreten.

## Reed Muller Normalform errechnen

- Eliminiere alle anderen Operatoren: $$\begin{align}\varphi \lor \uppsi = (\varphi \land \uppsi) \oplus \varphi\oplus\uppsi\\\varphi \implies \uppsi = (\varphi \land \uppsi)\oplus \varphi \oplus 1\\\varphi \iff \uppsi = \varphi \oplus\uppsi\oplus 1\\\neg \varphi = \varphi \oplus 1\end{align}$$
- Reduziere $$\begin{align}
\varphi \land (\alpha \oplus \beta) = \varphi\land \alpha \oplus \varphi\land \beta\\\varphi \oplus \varphi = 0\\
\varphi \oplus 0 = \varphi\\
\end{align}$$
- Definiere die Variablen Ordnung
- Ordne neu
- Aufräumen
- Doppelte Konjunktive Terme löschen

## Von Mixed Polarity nach Normalform
Wir ersetzen die Negationen durch $\neg x = (true \oplus x)$.
Danach vereinfachen wir.

## Reed Muller Normalformen als Polynome

Reed Muller Normalformen sind Polynome... xD


