
$$(x_1 \land y_1) \lor (x_2 \land y_2) \lor (x_3 \land y_3)$$

$$\begin{align}
\varphi_i \equiv\\
F_i \iff (x_i \land y_i)\\
F_i \implies (x_i \land y_i)\land (x_i \land y_i) \implies F_i\\
\equiv\\
(\neg F_i \lor x_i) \land (\neg F_i \land y_i) \land (\neg x_1 \lor \neg y \lor F_i)
\end{align}$$

$$(F_1 \lor F_2 \lor F_3) \land \varphi_1 \land \varphi_2 \land \varphi_3$$
Wir bekommen $1 + 3n$ Klauseln


---

$$X_1 \lor (\neg x_1 \land x_3) \lor (x_1 \land \neg x_2)$$

$$C_1 = \lbrace \neg X_1 \lor x_1, \neg X_1 \lor x_2, \neg x_1 \lor \neg x_2 \lor X_1\rbrace$$

