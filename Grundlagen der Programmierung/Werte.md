## [Abstrakte Syntax](Syntax.md#Abstrakte%20Syntax)
```csharp
e::=
    | let x_1 = e_1 in e_2
    | x
```

## [Statische Semantik](Semantik.md#Statische%20Semantik) Signatur

$$
{\over \sum \vdash x \sum(x)} x \in dom\sum
$$

$${{ \sum \vdash e_1 : t_1 }\  {\sum,\{x_1 \mapsto t_1\}\vdash e_2:t} \over \sum \vdash let\ x_1 = e_1\ in\ e_2: }$$


$\sum \vdash e :t$ Signatur / Ausduck / Typ

## [Dynamische Semantik](Semantik.md#Dynamische%20Semantik) Umgebung

$$
\over\delta \vdash x \Downarrow \delta(x) 
$$

$$
\delta \vdash e_1 \Downarrow v_1 | e_2\Downarrow \delta, \{x_1 \mapsto v_1 \}\vdash e_2\Downarrow v_2 \over \delta \vdash let x_1 = e_1 in e_2 \Downarrow 
$$
#prüfungszettel

