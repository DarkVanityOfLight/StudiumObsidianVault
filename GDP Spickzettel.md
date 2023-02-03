## Beweisbaumregeln

$$\overline{num(n) \Downarrow n}$$
$$\frac{e_{1}\Downarrow n_{1}\qquad e_{2}\Downarrow n_2}{add(e_{1}, e_{2}) \Downarrow n_{1}+ n_2}$$

$$\frac{e_{1}\Downarrow n_{1}\qquad e_{2}\Downarrow n_2}{mul(e_{1}, e_{2}) \Downarrow n_{1}\cdot n_2}$$

$$\frac{e_{1} \qquad e_{2} \qquad e_{3}}{if\; e_{1}\; then\; e_{2}\; else\; e_{3}}$$

$$
\frac{}{\emptyset \vdash let\; s = ... \;in\; ...}
$$

## Signatur/Umgebung
Die Signatur Speicher den Typ einer Variable
Die Umgebung Speichert den Wert einer Variable
$$$$


## Standard Funktionen
List.concat: List<List 'a> -> List<'a>
List.rev