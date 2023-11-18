## RAW

> read-after-write auch genannt echte Abhängigkeit

$\mathcal I^{(t)}$ liest eine Variable die von einer der $\mathcal I^{(t-1)}, \dots \mathcal I^{(t+i-p)}$ in einer der nächsten Stufe geschrieben wird.

$\mathcal I^{(t)}$  liest in Stufe $i$ eine Variable die später von einer Vorangehenden Anweisung $\mathcal I^{(t-j)}$ geschrieben wird. $\mathcal I^{(t)}$ liest zu früh, es sollte nur gelesen werden wenn alle vorangehenden Anweisungen geschrieben haben.
## Formale Definition von RAW Konflikten
Betrachten wir zwei Anweisungen $\mathcal I$ und $\mathcal J$, in Sequentieller Ausführung, würden erst alle Schritte von $\mathcal J$ ausgeführt bevor einer der Schritte von $\mathcal I$ Ausgeführt wird, dadurch würden alle Schreib Operationen von $\mathcal J$ von $\mathcal I$ gesehen werden. In einer Pipeline starten wir früher mit $\mathcal I$ müssen dafür aber Konflikte vermeiden.

|Zeit/Stufe|$i$|$\dots$|$i+k$|$i+k+2$|$\dots$|$p$|
|----------|-|-|-|-|-|-|
|$t$|$\mathcal I: read(x)$|$\dots$|$\mathcal J: x = \tau;\; next(x) = \tau$||||
|$t+1$||$\dots$||$\mathcal J x = \tau;\;next(x) = \tau$|||
|$\vdots$|$\vdots$|$\dots$|$\vdots$|$\vdots$||$\vdots$|
|$t_p$||$\dots$||||$\mathcal J x=\tau;next(x) = \tau$|


Eine Zuweisung von $\mathcal J$ zum Zeitpunkt $t$ wird nur von einer Leseoperation zum Zeitpunkt $t$  von $\mathcal I$ gesehen, alle anderen Zuweisungen von $\mathcal J$ sind zu spät.

Nehmen wir nun an das:
- $t_r$ ist der erste Punkt in unserer Zeit an dem $\mathcal I$ den Wert $x$ liest, der von $\mathcal J$ geschrieben wurde
- $t_{w, i}$ ist der letzte Punkt an dem $\mathcal J$ die Zuweisung $x=\tau$ ausführt
- $t_{w,d}$ ist der letzte Punkt an dem $\mathcal J$ eine verspätete Zuweisung $next(x) = \tau$ ausführt

Wir merken das $t_r \ge t_{w, i}$ und $t_r > t_{w, d}$ gelten muss.

Wir definieren $RAW(\mathcal I, \mathcal J)$ wenn eine der folgenden [Mengen](Mengen.md) nicht leer ist:
- $Read(\mathcal I, i) \cap \bigcup^{p}_{j=i+1} DWrite(\mathcal J, j)$
- $Read(\mathcal I, i) \cup \bigcup^{p}_{j=i+2} IWrite(\mathcal J, j)$
## Erkennen von RAW Konflikten

### Tabelle
Eine Tabelle ist eine Boolesche [Matrix](Matrix.md) $S[i][j]$ für die Register $i \in\lbrace 0,\dots, r\rbrace$ und eine Pipeline mit den Stufen $j\in \lbrace 1, \dots, p\rbrace$. Der Eintrag $S[i][j]$ sollte uns sagen ob das Register $Reg[i]$ in der Zukunft von den Befehlen in den Stufen $j,\dots, p$ überschrieben wird


Betrachten wir eine Pipeline zum Zeitpunkt $t$

|Stufe|$1$|$2$|$\dots$|$p-1$|$p$|
|-----|-|-|-|-|-|
||$\mathcal I_1$|$\mathcal I_2$|$\dots$|$\mathcal I_{p-1}$|$\mathcal I_p$|

Beim durchlaufen der restlichen Pipeline Stufen $k, \dots, p$ wird $\mathcal I_k$ die folgenden Dinge überschreiben:
$$OW(k) = \bigcup^p_{s=k} DWrite(\mathcal I_k, s) \cup\bigcup^p_{s=k+1} IWrite(\mathcal I_k, s)$$
Wir bemerken:
$$OW(k) \subseteq OW(k-1)$$
Deshalb betrachten wir $S[i][j]$ in jedem Cycle als $S[i][j] = Reg[i] \in \bigcup^p_{s=j} OW(j)$, dadurch gilt $S[i][j]$ genau dann wenn eine der Anweisungen $\mathcal I_j, \mathcal I_p$ in der Pipeline das Register $Reg[i]$ später schreiben wird.

Ist eine Anweisung $\mathcal I$ in der Stufe $j$  und will $Reg[i]$ lesen, dann kann es dies tuen wenn $S[i][j]$ falsch ist.

Ansonsten werden die Stufen $1, \dots j$ unterbrochen bis $S[i][j] = false$ gilt. Dies ist die einfachste Methode um RAW Konflikte zu beheben.