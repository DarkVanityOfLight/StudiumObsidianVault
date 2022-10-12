# Folgen
![Schranken](Schranken.md)
![Monotonie](Funktionen.md#Monotonie)


Sein $\epsilon > 0$ vorgegeben. Wir müssen $n_\epsilon \in N$ bestimmen, sodass $|a_n -a| < \epsilon$, also $|{1\over n} - 0| < \epsilon \forall n \geq n_\epsilon$
da $1\over n$ stets positiv ist, soll also ${1\over n} < \epsilon$, also $n > {1\over \epsilon} \forall n \geq n_\epsilon$
Also $n_\epsilon$ können wir wählen $n_\epsilon := \lceil {2\over \epsilon}\rceil$
Sei $\epsilon > 0$ beliebig. Sei $n_\epsilon := \lceil {2\over \epsilon}\rceil$. Dann gilt
für alle $n \geq n_\epsilon$
$$\begin{align}
|{1\over n} - 0| = |{1\over n}| = {1\over n} \leq {1\over n_\epsilon} = {1\over \lceil {2\over \epsilon}\rceil} \leq {1 \over {2\over \epsilon}} = {\epsilon \over 2} < \epsilon
\end{align}$$

$\neg B \implies \neg A$ : nicht beschränkt $\implies$ nicht konvergent
Beschränktheit ist keine hinreichende Bedingung für Konvergenz