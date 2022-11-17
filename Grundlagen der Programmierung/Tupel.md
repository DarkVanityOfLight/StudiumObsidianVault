Tupel erlauben es zwei verschiedene Daten als Einheit zu behandeln

## Syntax
```csharp
("Lisa", 9N) : String * Nat
(7N, fun (i: Nat) -> i) : Nat * (Nat -> Nat)
```

## [Statische Semantik](Semantik.md#Statische%20Semantik)
$$
\sum \vdash e_1: t_q \qquad\sum \vdash e_2:t_2 \over \sum \vdash (e_1, e_2) : t_1 * t_2
$$

$$
\begin{align}
{\sum \vdash : t_1 * t_2 \over \sum \vdash fst\, e:t_1} \qquad {\sum \vdash e: t_1 * t_2 \over \sum snd\, e: t_2}
\end{align}
$$

## [Dynamische Semantik](Semantik.md#Dynamische%20Semantik)

$$
\delta \vdash e_1 \Downarrow v_1 \qquad \delta \vdash e_2 \Downarrow v_2 \over \delta \vdash (e_1, e_2) \Downarrow(v_1, v_2)
$$
$$
{\delta \vdash e \Downarrow(v_1, v_2) \over
\delta \vdash fst\, e \Downarrow v_1} \qquad {\delta \vdash e \Downarrow(v_1, v_2) \over
\delta \vdash snd\, e \Downarrow v_2}
$$
