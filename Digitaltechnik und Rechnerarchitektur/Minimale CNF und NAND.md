
## CNF

Da wir nur Algorithmen betrachten die DNFs ergeben wird hier erklärt wie man aus einer DNF eine minimale CNF macht.

Um die Minimale CNF einer Formel $\varphi$ zu berechnen:
- Berechne die Minimale DNF $\bigvee_i\bigwedge_j \alpha_{i,j}$ für $\neg \varphi$
- Negiere die DNF um die minimale CNF $\varphi: \bigwedge_i\bigvee_j \neg \alpha_{i, j}$


> [!IMPORTANT] Eine minimale DNF von $\varphi$ gehört zu einer minimalen CNF von $\neg\varphi$ und eine minimale DNF von $\neg \varphi$ gehört zu einer minimalen CNF von $\varphi$


## NAND

Wir können auch eine "zwei Level" NAND Formel berechnen

- Berechne die Minimale DNF $\bigvee_i\bigwedge_j \alpha_{i,j}$ für $\varphi$
- Diese ist Äquivalent zu $\neg\bigwedge_i \neg\bigwedge_j \alpha_{i, j}$
- Wir müssen noch die Negationen $\neg x$ mit $\neg(x\land x)$ ersetzen

> [!NOTE] $\neg\bigwedge^{n-1}_{i=0} \varphi_i \equiv \neg(\varphi_0 \land \dots \land \varphi_n-1)$ wird als ein NAND [Gatter](Gatter.md) gezählt. 

Das selbe Funktioniert für NOR Formeln mit einer minimalen CNF.

