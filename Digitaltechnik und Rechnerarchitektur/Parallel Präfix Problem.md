
Gegeben sei eine Assoziative Funktion $f: D \times D \to D$ mit $n$ Werten $x_0, \dots x_{n-1}$.
Das Problem:
Berechne alle Präfixes $p_i := f(x_0, \dots, x_i)$ für $i=0, \dots, n-1$ parallel.

Wir sollten $f(f(f(x_0, x_1), x_2), x_3)$ oder $f(x_0, f(x_1, f(x)2, x)3)))$ schreiben aber da $f$ Assoziativ ist macht es keinen unterschied und wir schreiben $f(x_0, x_1, x_2, x_3)$. Um ein Präfix zu berechnen sollten wir die Funktion als Binärbaum schreiben:
$$f(f(f(x_0, x_1), f(x_2, x_3)), f(f(x_4, x_5), f(x_6, x_7)))$$
Aber wir wollen alle Präfixe gleichzeitig berechnen, meistens Betrachtet man $f$ als Addition.


## Kogge-Stone

Wir Konstruieren $\log_2(n)$ Level aus $n-2^0, n-2^1,..., n-2^{\log_2(n)-1}$ Knoten
Im $l$ten Level Berechnen wir $x[i+2^l] = x[i+2^l] + x[i]$ für $i=0,\dots, n-1 -2^l$.

