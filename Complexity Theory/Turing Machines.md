

## Multi Tape Turing Machine


- Read only input tape
- Write only output tape
- 1 or more Work tapes

> K Tape Turing Machines
> $M = \langle Q, \Sigma, \Gamma, \Omega, \Delta, q_0, F\rangle$
> Where
> - $Q$ is the Finite set of states
> - $\Sigma\subset\Gamma$ is the input alphabet
> - $\Gamma \cup \lbrace \square\rbrace$ is the tape alphabet where $\square$ is the blank symbol
> - $\Omega$ is the output alphabet
> - $\Delta \subseteq (Q\setminus F) \times \Gamma^k \times Q \times \Gamma^k \times (\Omega \cup \lbrace \varepsilon  \rbrace) \times \lbrace -1, 0, 1\rbrace$ is the transition relation
> - $q_0$ is the initial state
> - $F\subseteq Q$ is the set of final states
> A transition $(p, a_1, \dots, a_k, q. b_1, \dots, b_k, c, d_1, \dots, d_k)\in \Delta$
> Currently state $p$ $k$ heads read symbols $a_1, \dots, a_k$ => Switch to state $q$ write $b_1, \dots, b_k$ on $k$ tapes, output $c$, move heads left/right according to $d_i$
> $M$ is __determinstict__ iff $\Delta$ is a function


__Remark:__ If $M$ is used as _language acceptor_, i.e the output is $0$ or $1$, we assume $F = \lbrace q_{acc}, q_{rej}\rbrace$, indicating acceptance/rejection. Mostly for nondeterministic TM's


> Configurations and computations
> Configuration of TM $M$ is a tuple $c = (q, u_1,i_1,u_2, i_2, \dots, u_k, i_k, v)$
> where:
> - $q$ is the current state
> - $u_i \in \Gamma^+$
> - $1 \le i_j \le |u_j| position of the i-th head
> - $v$ is the output word
> We write $c_1 \vdash_M c_2$ if $c_2$ is a successor configuration of $c_1$
> A __computation__ on $w\in \Sigma^*$ is a finite or infinite sequence $c_0, c_1, c_2, c_3 \dots$ with
> - $c_0 = (q_0, w, 1, \square, q, \dots, \square, 1, \varepsilon)$
> - $c_{i-1} \vdash_M c_i$ for all $i$
> A finite computation is halting if it ends in a configuration $(q, u_1, i_1, \dots, u_k, i_k, v)$ with $q\in F$- The word $v \in \Omega^*$ is called the output.
> The function computed by a deterministic TM $M$ is a partial function 
> $M: \Sigma^* \to \Omega^*$
> It is defined $M(x) =y \iff$ there exists a halting computation of $M$ on $x$ with output $y$.
> A function is computable if it is computed by some deterministic TM
> A language $L\subseteq \Sigma^*$ is decidable if the characteristic function $\chi_L: \Sigma^* \to \lbrace 1, 0\rbrace$ is computable
> A nondeterministic TM $M$ accepts the language $$L(M) = \lbrace x \in \Sigma^* | \exists \text{ halting computation of $M$ on $x$ with output $1$}\rbrace$$

__Convention__: Usually, we assume that the first tape is read-only




