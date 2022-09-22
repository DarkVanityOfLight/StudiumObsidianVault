# Die Wurzel aus 2 ist nicht Rational
Wir suchen eine Zahl d, mit der wir die Länge der Diagonalen im Quadrat der Seitenlänge $1$ angeben können. Die in der unteren der beiden Abbildungen dargestellte Konstruktion mit einer Zerlegung in Dreiecke zeigt dann, dass das Quadrat mit Seitenlänge $d$ eine doppelt so große Fläche hat, wie das Quadrat mit Seitenlänge $1$. Da die Fläche eines Quadrates mit Seitenlänge d durch $d^2$ gegeben ist, sehen wir also, dass die gesuchte Zahl $d$ die Gleichung $d^2=2$ erfüllen muss.
Hippasos erkannte, dass es keine rationale Zahl gibt, die diese Gleichung erfüllt, d.h., es gibt keine ganzen Zahlen pp und $q \neq 0$, so dass $d={p \over q}$.
Der bekannteste Beweis geht auf den Griechen Euklid im 4. Jahrhundert v. Chr. zurück. Er basiert auf einem Widerspruch. Angenommen $d$ ist eine rationale Zahl. Da $d$ sicher größer als Null ist, kann dd sogar als Quotient zweier natürlicher Zahlen dargestellt werden, also
$$d = {p \over q}, p,q \in N$$
Insbesondere können wir davon ausgehen, dass pp und $q$ keine gemeinsamen Teiler haben, der Bruch also [vollständig gekürzt](Erweitern%20und%20Kürzen%20von%20Brüchen.md) ist. Da nun
$$2 = d^2 = ({p \over q})^2 = {p^2 \over q^2} \leftrightarrow p^2 = 2q^2$$
und $2q^2$ eine gerade Zahl ist, ist folglich auch $p^2$ eine gerade Zahl. Daraus folgt, dass auch $p$ eine gerade Zahl sein muss, denn es gilt: Das Quadrat einer ungeraden Zahl ist selbst wieder ungerade. Das bedeutet, dass$$p =2m$$
mit $m \in N$. Einsetzen in obige Gleichung ergibt, dass wegen $$2q^2 = p^2 = (2m)^2 = 4m^2 \leftrightarrow q^2 = 2m^2$$
auch $q^2$ und damit auch q gerade Zahlen sind. Zusammengefasst sind also sowohl p, als auch q durch zwei teilbar, im Widerspruch dazu, dass der Bruch $p^q$ vollständig gekürzt ist. Somit muss die Annahme, dass die Gleichung $d^2=2$ durch eine rationale Zahl gelöst werden kann falsch sein, oder anders ausgedrückt:
$$d\ ist\ irrationa\ q.e.d\blacksquare$$