Alle wichtigen Prozesse in der Natur können (in idealisierter Form) durch Differentialgleichungen beschrieben werde. In ihrer grundlegendsten Form beschreibt eine Differentialgleichung eine Beziehung zwischen einer Funktion $f(x)$ und ihrer Steigung $f'(x)$ der Form
$$f'(x) = \alpha \cdot f(x)$$
mit einer Konstanten $\alpha$. Beispielsweise ist das Wachstum $f'(x)$ einer Population $f(x)$ als Funktion von der Zeit $x$ ein Vielfaches der aktuellen Größe der Population. In diesem Fall wäre also typischerweise $\alpha > 0$. Um Beispielsweise die Kaninchenpopulation für sehr große $n$ als Funktion $f(x)$ der Zeit $x$ zu beschreiben würde man für $\alpha$ die asymptotische Wachstumsrate $\alpha = \frac{1+\sqrt{5}}{2}$ nehmen. Genauso könnte $f(x)$ auch die Ladung in einem Kondensator sein. Beim radioaktiven Zerfall ist dien pro Zeiteinheit zerfallende Zahl der Teilchen proportional zur Teilchen zahl, hier wäre also $\alpha < 0$.
Das Ziel ist es dann, die Menge aller Funktionen zu $f(x)$ zu bestimmen, die die Differentialgleichung lösen. Der Einfachheit halber betrachten wir ($\alpha = 1$)
$$f'(x) = f(x)$$

Zunächst stellt sich die Frage, wie wir die Steigung $f'(a)$ der Funktion im festgelegten Punkt $a$ herausfinden. Für $x\not = a$ aber nahe bei $a$ erhalten wir eine Näherung durch die Steigung der __Sekante__, die wiederum durch den __Differenzquotienten__ 
$$
\frac{f(x) -f(a)}{x-a}
$$
der Funktionswerte und der Argumente gegeben ist. Die Steigung der Tangente und damit der Funktion in $x=a$ erhalten wir also durch den Limes
$$f'(a) = \lim_{\begin{array}{} x\to a\\ x\not = a\end{array}} \frac{f(x)-f(a)}{x-a}$$
falls dieser denn existiert (und dann heißt $f$ differenzierbar).

---

Eine [Funktion](Mathe/Funktionen.md) $f: D\to\mathbb R$ heißt differenzierbar in $a\in D$, wenn

$$f'(a) := \lim_{\begin{array}{}x\to a\\ x\not= a\end{array}}\frac{f(x)-f(a)}{x-a}$$
existiert und $f'(a)$ heißt __Ableitung__ von $f$ in $a$. Weiter heißt $f$ differenzierbar, wenn $f$ in jedem $a\in D$ differenzierbar ist und die Funktion
$$f': D\to \mathbb R, x\mapsto f'(x)$$
heißt Ableitung von $f$.
Wir schreiben rekursiv $f^{(n)} = (f^{(n-1)})'$ für die n-te Ableitung wobei $f^{(0)} = f$ insbesondere ist also $f^{(2)} = f''$ und $f^{(3)} = f'''$.
Um die Notation zu vereinfachen, schreiben wir im Folgenden in der Definition von $f'(a)$ nur $\lim_{x\to a}$ und setzen $x\not = a$ stillschweigend voraus.

Eine notwendige Bedingung für die Differenzierbarkeit ist die [Stetigkeit](Stetigkeit%20und%20Zwischenwertsatz.md)

> Jede differenzierbare Funktion ist stetig



