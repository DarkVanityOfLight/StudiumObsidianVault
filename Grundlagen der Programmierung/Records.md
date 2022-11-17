## Syntax
```csharp
type Date = {day: Nat; month: Nat; year:Nat};
type Person = {forename: String; surname: String}
```

## [Statische Semantik](Semantik.md#Statische%20Semantik)
$\text{type T}= \{l_1:t_1, l_2: t_2\}$


$$\sum \vdash e_1:t_1 \qquad \sum \vdash e_2: t_2 \over
\sum \vdash \{l_1 = e_1; l_2 = e_2\}: T$$
$$
\sum \vdash e: T \over
\sum \vdash e.l_i: t_i
$$
## [Dynamische Semantik](Semantik.md#Dynamische%20Semantik)
#zuhause 
$$$$
