## Allquantor
> Die Universalaussage wird mit dem Allquantor $\forall$ bezeichnet.
> Man ließt "für alle"
>Eine Universalaussage wird [verneint](Aussagen.md#Negation), indem man den [Existenzquantor](#Existensquantor) $\exists$ vor die verneinte Aussage stellt.

$${\cap \atop i \in I}M_i = \{m | m \in M_i \forall i\in I\}$$

## Existensquantor
>Die Existenzaussage wird mit dem Existensquantor $\exists$ bezeichnet.
>Man ließt "mindestens eins"
>Eine Existenzaussage wird [verneint](Aussagen.md#Negation), indem man den [Allquantor](#Allquantor)$\forall$ vor die verneinte Aussage stellt.

$$
{\cup \atop i\in I} M_i = \{m|\exists i\in I\ mit\ m\in M_i\}
$$

## Beispiel
Alle Studierenden sind fleißig.
Es handelt sich hierbei um eine Universalaussage.
$$\forall s \in S$$
$\forall$ ist der "Allquantor"
$\neg A$ Es gibt einen Studierenden, der nicht fleißig ist:
$$\neg (\forall s \in S:  s\ ist\ fleißig)$$
$$\exists s \in S : s\ ist\ nicht \ fleißig$$

Es gibt Vögel die nicht fliegen können.
Es handelt sich hierbei um eine Existenzaussage.
$$\exists v \in V$$
$\exists$ Existensquantor
$$\begin{align}
&\neg (\exists v \in V: v\ kann\ nicht\ fliegen)\\
\iff & \forall v \in V: v\ kann\ fliegen 
\end{align}
$$