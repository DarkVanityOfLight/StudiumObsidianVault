
## Task 1
AFA: $A = \langle Q, \Sigma, \Delta, F\rangle$

$A' = \langle Q, \Sigma, \Delta', q_0, Q\setminus F\rangle$
$\overline{L(A)} = L(A'), \forall w w\in L(a) \iff w\not\in L(A')$
$w\in L(A) \iff$ $0$ win $G\langle \langle V, E\rangle, T\rangle$, $G' = \langle\langle V', E\rangle, T'\rangle$

$V_0 = V_1'$
$V_1 = V_0'$
$T = \lbrace n \rbrace \times F$, $T' = \lbrace n \rbrace \times (Q\setminus F)$

$$\begin{align}
w\in L(A) &\iff 0 \text{ win }G\\
&\iff \exists \sigma_1 \forall \sigma_2 \text{reaches }(n, q) q\in F\\
&\iff \text{not} \exists\sigma_2\forall\sigma_1 \text{reaches}(n, q) q\in Q\setminus F\\
&\iff \text{not}(\exists \sigma_1\forall \sigma_2 \text{reaches}(n, q) \in T')\\
&\iff \text{not $0$ wins in} G' \\
&\iff 1 \text{ wins } G'\\
&\iff w\not \in L(A')
\end{align}$$


## Task 2

$$\begin{align}
&G(a \to F(b \lor c))\\
&\neg(\top U (\langle a\rangle\top \land \neg (\top U (\langle b\rangle\top \lor \langle c \rangle \top))))
\end{align}$$

- $Q = \lbrace p_\psi | \psi \in sub^\pm (y)\rbrace$
- $\Sigma = \lbrace a, b, c\rbrace$
- $q_0 = p_\phi$

$neg \phi = \underbrace{\top}_{\psi_1} U \underbrace{(a \land \neg(\top U (b\lor c)))}_{\phi_1}$
$\phi_1 = (a\land \underbrace{\neg (\top U (b \lor c))}_{\phi_2})$
$\phi_2 = \neg(\top U \underbrace{(b\lor c)}_{\phi_3}$

|                             | $a$                                                                            | $b$                                                                            | $c$                                                                            |
| --------------------------- | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| $p_\phi$                    | $\Delta(p_{\neg \phi}, a)$                                                     |                                                                                |                                                                                |
| $p_{\neg \phi}$             | $\Delta(p_{\phi_1, a}) \lor p_{\neg\phi}$                                      | $\Delta(p_{\phi_1, b}) \lor p_{\neg\phi}$                                      | $\Delta(p_{\phi_1, c}) \lor p_{\neg\phi}$                                      |
| $p_{\phi_1}$                | $\Delta(p_{\langle a \rangle \top}, a) \land \Delta(p_{\phi_2}, a)$            | $\Delta(p_{\langle a \rangle \top}, b) \land \Delta(p_{\phi_2}, b)$            | $\Delta(p_{\langle a \rangle \top},c) \land \Delta(p_{\phi_2}, c)$             |
| $p_{\langle a\rangle \top}$ | $p_\top$                                                                       | $\bot$                                                                         | $\bot$                                                                         |
| $p_{\phi_2}$                | $p_{\phi_2}$                                                                   | $p_\bot \land p_{\phi_2}$                                                      | $p_\bot \land p_{\phi_2}$                                                      |
| $p_{\neg \phi_2}$           | $\Delta(\phi_2, a) \lor p_{\neg \phi_2}$                                       |                                                                                |                                                                                |
| $p_{\phi_3}$                | $\Delta(p_{\langle b\rangle\top}, a) \lor \Delta(p_{\langle c\rangle\top}, a)$ | $\Delta(p_{\langle b\rangle\top}, b) \lor \Delta(p_{\langle c\rangle\top}, b)$ | $\Delta(p_{\langle b\rangle\top}, c) \lor \Delta(p_{\langle c\rangle\top}, c)$ |
> In the exercise he back substituted the values for the $\Delta$, but I didn't write that down, should be clear tho.


![[Exercise II 2024-12-03 14.37.15.excalidraw]]


__Finall__:
- Top is accepting.
- Until is not accepting -> not Until is accepting


## Task 3
> We didn't do this one

## Task 4

$$R = \lbrace a^{30n} | n\ge 30\rbrace$$
$$2 \cdot 3 \cdot 5 = 30$$

![[Exercise II 2024-12-03 14.59.59.excalidraw]]
> I think this automata is wrong actually
> This would add an additional $a$ at the start so $1 + 30\cdot n$

b) $|Q| \le 30$ NFA

$|w| = 30 \quad w \in L(A)$
$q_0\dots q_{30}$
$\exists i, j \in \lbrace 1, \dots, m\rbrace$
$q_i = q_j, \quad i < j$
$0 < |q_0 \dots q_i q_{j+1}, \dots, q_30| < 30$
$0 < |w'| < 30$
$\implies w' \in L(A)$
> This also not 100% correct because of the empty word, instead of shortening our word it would be easier to pump it up in length.
> Since the cycle has a min length of 1 and a max length of 29, this also leads to a non divisible number

