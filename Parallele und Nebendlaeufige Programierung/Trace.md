
## Definition

Sei $p_0 = (E_0, \leq_0, \alpha_0)$ ein [Sequentieller](Sequentialität%20und%20Nebenläufigkeit.md) [Prozess](Prozess.md) ($E_0$ endlich). Der __Trace__ von $p_0$ ist ein Vektor von Aktionen, der rekursiv definiert ist als
- $trace(p_0) = <>$ für $E_0 = \emptyset$
- Ansonsten bestimme das Element $e \in E_0$ mit $\forall e' \in E_0 e \leq_0 e'$, definiere $p_0' = (E_0', \leq_0', \alpha_0')$ mit $E_0' = E_0\setminus\lbrace e\rbrace \leq_0', \alpha_0'$ sind $\leq_0, \alpha_0$ auf $E'_0$ eingeschränkt $\implies trace(p_0) = concatenate(<\alpha_0(e)>, trace(p_0'))$

## Beispiel

$$p_0 = (\lbrace e_1,\dots e_5\rbrace, \lbrace (e_i, e_j) | i\leq j\rbrace, \alpha_0(e_i) = a_i) \implies trace(p_0) = <a_1, a_2, a_3, a_4, a_5>$$


$$p_0 = (\lbrace e_6,\dots e_10\rbrace, \lbrace (e_i, e_j) | i\leq j\rbrace, \alpha_1(e_i) = a_{i-5}) \implies trace(p_1) = <a_1, a_2, a_3, a_4, a_5>$$


## Mengen der Traces

Sei $p_0 = (E_0, \leq_0, \alpha_0)$ ein [Prozess](Prozess.md). Die __Traces__ von $p_0$ sind gegeben durch:

$Traces(p_0) = \lbrace trace(q_0) | q_0\text{ ist eine vollstaendige Sequentialisierung von } p_0\rbrace$ 

Die Menge der Traces ist ein anderes Modell fuer eine Menge von Prozessen und wird als __Interleaving__ Modell bezeichnet.

## Eindeutigkeit

Zum Prozess $p_0$ ist das durch $Traces(p_0)$ gegebene Interleaving Modell eindeutig bestimmt. Die Umkehrung dieser Aussage gilt jedoch nicht.

