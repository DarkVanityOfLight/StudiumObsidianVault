

## Substitutionsregel

Ist $f: [r, s]\to\mathbb R$ stetig und $g: [a, b] \to [r, s]$ differenzierbar mit stetiger Ableitung, dann gilt:
$$
\int^{s}_{r} (f\circ g)(x) \cdot g'(x) dx = \int^{g(s)}_{g(r)} f(y) dy
$$
Mittels einer Stammfunktion $F$ von $f$ schreiben wir auch
$$
\int(f\circ g)\cdot g' dx = F\circ g
$$

## Partielle Integration

Seien $f, g: [r, s]\to\mathbb R$ differenzierbare Funktionen mit stetiger Ableitung. Dann gilt 
$$\int^{s}_{r} f(x) \cdot g'(x) dx + \int^{s}_{r} f'(x) \cdot g(x) dx = [f(x)\cdot g(x)]^{s}_{r}$$
Für die Stammfunktionen schreibt man auch
$$
\int f \cdot g' dx + \int f' \cdot g\; dx = f\cdot g
$$
