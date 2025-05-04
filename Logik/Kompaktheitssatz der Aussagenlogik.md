

Eine [Menge](Mengen.md) $\Sigma$ von Formeln nennt man [Erfüllbar](Erfüllbarkeit.md) , falls es eine Interpretation $I$ gibt, die jede Formel aus $\Sigma$ erfüllt. Ist $\Sigma$ endlich. dann ist dies äquivalent zu der Aussage, dass $\bigwedge_{\varphi\in\Sigma} \varphi$  [erfüllbar](Erfüllbarkeit.md) ist. Wir lassen aber auch zu das $\Sigma$ unendlich ist.


>[!DEFINITION] Endlich erfüllbar 
>Eine [Menge](Mengen.md) $\Sigma$ von Formeln nennen wir endlich [erfüllbar](Erfüllbarkeit.md), falls jede endliche Teilmenge $\Sigma' \subseteq \Sigma$ erfüllbar ist.

>[!DEFINITION] Kompaktheitssatz
>Eine Menge $\Sigma$ von Formeln ist erfüllbar genau dann wenn sie endlich erfüllbar ist

Der Kompaktheistsatz ist oft anders formuliert: 
Gegeben eine [unerfüllbare](Unerfüllbar.md) Menge $\Sigma$, dann existiert eine endliche unerfüllbare Teilmenge $\Sigma'\subseteq \Sigma$. Der Kompaktheitssatz ist also besonders interessant, da er die Existenz eines endlichen Zeugen für die Unerfüllbarkeit beweist. Dieser Zeuge ist aber nicht im Beweis konstruiert oder mit einem Algorithmus berechnet. Eine Folgerung aus dem Kompaktheitssatz ist die Folgende Proposition:

> [!DEFINITION] Satz
> Ist $\Sigma \vDash \varphi$, dann existiert eine endliche Teilmenge $\Sigma' \subseteq \Sigma$ sodass $\Sigma' \vDash \varphi$.

## Beweis

Die $\implies$ Richtung ist trivial. Wir werden uns auf die andere Richtung konzentrieren. Wir nehmen an, dass $\Sigma$ endlich erfüllbar ist. Für den Beweis brauchen wir das folgende Lemma.

>[!DEFINITION] Lemma
>Sei $\varphi$ eine Formel. Ist $\Sigma$ endlich erfüllbar, dann ist entweder $\Sigma \cup \lbrace \varphi \rbrace$ oder $\Sigma\cup \lbrace\neg \varphi\rbrace$ endlich unerfüllbar.

Der Beweis ist durch Widerspruch. Angenommen $\Sigma \cup\lbrace\varphi\rbrace$ und $\Sigma\cup \lbrace\neg\varphi \rbrace$ wären beide nicht endlich erfüllbar. Aus der Tatsache, dass $\Sigma \cup\lbrace\varphi\rbrace$ nicht endlich erfüllbar ist folgt die Existenz einer endlichen Menge $\Sigma_1 \subseteq \Sigma$, sodass jedes [Modell](Modell.md) von $\Sigma_1$ auch ein Modell von $\neg \varphi$ ist. Analog gibt es eine endliche Menge $\Sigma_2 \subseteq \Sigma$, sodass jedes Modell von $\Sigma_2$ ebenfalls ein [Modell](Modell.md) von $\varphi$ ist. Sei $\Sigma' := \Sigma_1 \cup \Sigma_2$. Da $\Sigma' \subseteq \Sigma$ endlich ist, existiert ein [Modell](Modell.md) $I$ für $\Sigma'$ (dies folgt aus der Annahme, dass $\Sigma$ endlich erfüllbar ist). Da $I$ ein Modell von $\Sigma_1$ ist, gilt $I\vDash \varphi$. Analog, da $I$ ein Modell von $\Sigma_2$ ist, gilt $I\vDash \neg\varphi$. Dies ist ein Widerspruch.
$\blacksquare$

Wir beweisen die $\Longleftarrow$ Richtung. Wir nehmen an, es gibt nur abzählbar unendlich viele Variablen $x_1, x_2, \dots$ . Dies ist eine sinnvolle Annahme in der Informatik. Der Beweis im allgemeinen Fall wen es Überabzählbar unendlich viele Variablen geben könnte ist dem Leser überlassen. Wir definieren zunächst $\Sigma_0 := \Sigma;$ zur Erinnerung, $\Sigma$ ist die gegebene endliche [erfüllbare](Erfüllbarkeit.md) Menge von Formeln. Wir definieren eine "wachsende" Kette von Mengen von Formeln wie folgt.

$$\begin{align}
\Sigma_{i+1} = \begin{cases} 
\Sigma_i \cup\lbrace x_{i+1}\rbrace \text{falls $\Sigma \cup \lbrace x_{i+1}\rbrace$ endlich erfüllbar ist}\\
\Sigma_i \cup \lbrace \neg x_{i+1} \rbrace \text{andernfalls}
\end{cases}
\end{align}$$

Definieren $\Gamma := \bigcup^{\infty}_{i=0} \Sigma_i$  .

>[!NOTE] Behauptung
> Jede Menge $\Sigma_i$ ist endlich erfüllbar.

Dies folgt aus Lemma $1$ mit Induktion. Die folgende Behauptung folgt aus der letzten Behauptung, da jede endliche Teilmenge von $\Gamma$ eine endliche Teilmenge von einem $\Sigma_i$ ist für ein $i$.

>[!NOTE] $\Gamma$ ist endlich erfüllbar

Wir zeigen nun, dass $\Gamma$ erfüllbar ist. Dafür konstruieren wir ein [Modell](Modell.md) $I$. Aus $\Sigma \subseteq \Gamma$ folgt, dass $\Sigma$ erfüllbar ist. Unser Modell weist $true$ allen [Atomaren Formeln](Logik/Atom.md) $x_i$ aus $\Gamma$ zu, und $false$ wir zugewiesen andernfalls.

>[!NOTE] $I\vDash \Gamma$

Sei $L$ die Menge aller [Literale](Literal.md) $(\neg)x_i$ aus $\Gamma$. Wir bemerken, dass $L$ keine Paare von widersprechenden Literalen enthalten kann, denn sonst wäre $\Gamma$ nicht endlich erfüllbar. Sei $\varphi \in \Gamma$ beliebig. Wir zeigen, dass $I\vDash \varphi$. Sei $U$ die Menge der Variablen in $\varphi$. Sei weiterhin $L_U$ die Menge der Literale aus $L$, deren Variable in $U$ vorkommt. Betrachte die Teilmenge $\Gamma_U \subseteq \Gamma$ von Formeln mit Variablen aus $U$. Wir bemerken, dass $\Gamma_U$ endlich bis auf [Äquivalenz](Äquivalenz.md) ($\equiv$) ist; d.h. die Partition von $\Gamma_U$ mit der [Äquivalenzrelation](Äquivalenzrelationen.md) $\equiv$ hat endlich viele [Äquivalenzklassen](Äquivalenzrelationen.md#Äquivalenzklassen) (oder anders Formuliert, hat einen "endlichen Index"). Dies ist der Fall, da es nur endlich viele [Boolesche Funktionen](Boolesche%20Funktion.md) mit Variablen aus der endlichen Menge $U$ gibt. Da $\Gamma$ endlich erfüllbar ist, ist $\Gamma_U$ endlich erfüllbar. Da entweder $x\in L_U$ oder $\neg x\in L_U$ für jede Variable $x \in U$  gilt und $L_U \subseteq \Gamma_U$, gibt es eine eindeutige erfüllende Belegung $I' : U\to \lbrace 0, 1 \rbrace$ mit $I' \vDash \Gamma_{U}$. Außerdem, da $I(x) = I'(x)$ für jedes $x\in U$ gilt, $I \vDash \Gamma_U$. Aus $\varphi \in \Gamma_U$. Aus $\varphi \in \Gamma_{U}$, folgt $I\vDash \varphi$
$\blacksquare$
