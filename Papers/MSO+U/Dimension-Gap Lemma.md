[Dimension gap Lemma](MSO+U.pdf#page=3&selection=8,0,27,1&color=red)
Let $d \in\mathbb N$. There exists a [vector sequence](Sequences.md) of dimension $d$ which is not an [asymptotic mix](Asymptotically%20equivalent.md#Asymptotic%20mix) of any vector sequence of dimension $d-1$.

[Since we didn't care about the order in the definition of an asymptotic mix](MSO+U.pdf#page=3&selection=40,23,41,51&color=red) we generalize the vector sequence to a vector family.(Every sequence is a family, not every family is a sequence)
> [!IMPORTANT] Vector Family
> A vector family is an indexed set of vectors, namely it is the function
> $$f: I \to V$$
> for some vector space $V$ and some countable index set $I$.

As [index set we use vectors of natural numbers](MSO+U.pdf#page=3&selection=42,57,42,84&color=red).
Then the $d$-dimensional identity
$$id: \mathbb N^d \to \mathbb N^d$$
is not an asymptotic mix of any vector family
$$g: \mathbb N^d \to \mathbb N^{d-1}$$


__Induction Base Case:__
Let $d=1$
Then $id: \mathbb N^1 \to \mathbb N^1$ is not an asymptotic mix of any vector family
$g: \mathbb N^1 \to \mathbb N^{0}$
Since $\mathbb N^0 = ()$ it is clear that $g$ then has no number sequence and thus is $id$ is not an asymptotic mix of any $g$

__Induction Hypothesis:__
For an arbitrary but fixed $d-1$, let $id$ not be a an asymptotic mix of any vector family.

__Inductive Case:__
$d-1 \to d$
Assume that $id$ is an asymptotic mix of some $g: \mathbb N^d \to \mathbb N^{d-1}$. Consider the subset $\lbrace 0\rbrace \times \mathbb N^{d-1}$ of $id$, that is any $d$ dimensional vector with the first coordinate set to $0$.
Now the subset of $id$ is bounded by zero,
and therefore there must be a number sequence $g\in\bf g$ which is also bounded by $0$ [MSO+U, p.3](MSO+U.pdf#page=3&selection=132,68,141,27&color=red). Now observe that we can swap the entries of the vectors in $\bf g$ such that the first entry is always $0$. That is $\bf g$ is bounded on arguments from $\lbrace 0\rbrace \times \mathbb N^{d-1}$
Now let
$$g': \mathbb N^d \to \mathbb N^{d-1}$$ be the vector family obtained from $\bf g$ by removing the first coordinate.

Call $\pi_i: \mathbb N^d \to \mathbb N$ with $i \in \lbrace 2, \dots, d\rbrace$ the projection of the $i$ th coordinate, which satisfies $\pi_i \in id$ -

