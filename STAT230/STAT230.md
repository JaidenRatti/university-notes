
Professor: [Erik Hintz](https://uwaterloo.ca/scholar/ehintz)

[[STAT230.pdf|Download PDF]]

[Github](https://github.com/JaidenRatti/university-notes/blob/main/STAT230/STAT230.pdf)

# Introduction to Probability

## Definitions of Probability

> [!info] Definition
> <u>Classical Definition of Probability</u>
> 
> $\frac{\text{number of ways an event can occur}}{\text{total \# of possible outcomes}}$
> 
> $^*$Provided things are equally likely.

> [!info] Definition
> <u>Relative Frequency</u>
> 
> The probability of an event is proportionate to number of times the event occurs in long repetitions. The probability of rolling a 2 is $\frac{1}{6}$ because after 6 million rolls, 2 will appear \~1 million times. (this is not very practical).

> [!info] Definition
> <u>Subjective Definition</u>
> 
> Persons belief on how likely something will happen (unclear since varies by person).

# Mathematical Probability Models

## Samples Spaces and Probability

<u>Sample Spaces & Sets</u>

Sample space $S$ is a set of distinct outcomes of an experiment with the property that in a single trial, only one outcome will occur.

-   Die: $S = \{1,2,3,4,5,6\}$ or $S = \{\text{even, odd}\}$

-   Number of coin flips until heads occurs: $S = \mathbb{N}^+$

-   Waiting time in minutes until a sunny day. $S = [0, \infty) = \{x \in \mathbb{R}: x \ge 0\}$

Sample space is discrete if it is finite or countably infinite (one-to-one correspondence with $\mathbb{N}$). Otherwise non-discrete.

$\mathbb{N}$ is discrete (countably infinite).

<u>Event</u> is a subset of a sample space $S$.

$A$ is an event if $A \subseteq S$ ($A$ is a subset of $S$, $A$ is contained in $S$).

- Die shows $6$: $A = \{6\}$

- $20$ or fewer tosses till heads. $A = \{1,\ldots,20\}$

-   $A = \{60,\ldots \infty\}$

Notation

1.  Element of: $x \in A \quad (x$ in $A)$

2.  Union: $A \cup B: \quad \{x | x \in A$ or $x \in B\}$

3.  Intersection: $A \cap B: \quad \{x | x \in A$ and $x \in B\}$

4.  Complement: $A^\complement: \{x | x \in S, x \in A\} = A^{\prime} = \overline{A}$

5.  Empty: $\emptyset$

6.  Disjoint $\implies A \cap B = \emptyset$

$2$ die rolled.

-   $S = \{(x,y):x,y\in \{(1,\ldots,6)\}$

-   $A = \{(x,y): (x,y) \in S \wedge x + y = 7\}$

    -   $A = \{(1,6),(2,5),(3,4),(4,3),(5,2),(6,1)\}$

-   $B^{\complement} = \{(x,y): (x,y) \in S \wedge x + y < 4\}$

    -   $B^{\complement} = \{(1,1),(1,2),(2,1)\}$

-   $A \cap B^{\complement} = \emptyset$

-   $A \cup B^{\complement} = \{A, B^{\complement}\}$

> [!info] Definition
> <u>Probability</u>
> 
> Let $\mathcal{S}$ denote the set of all events on a given sample $S$. Probability defined on $\mathcal{S}$ is defined as
> $$
> \begin{align*}
>     P: \mathcal{S} \to [0,1]
> \end{align*}
> $$

1.  Scale: $0 \le P(A) \le 1$

2.  $P(S) = 1$

3.  Additivity (infinite): $P(\bigcup_{i=1}^{\infty}A_i) = \sum_{i=1}^{\infty}P(A_i)$

> e.g. $A_1 = \{1\}, A_2=\{2\}, A_3 = A_4 = \emptyset$
> 
> $P(1$ or $2) = P(A_1) + P(A_2)$

$S$ (discrete) and $A \subset S$ is an event.

$A$ is indivisible $\iff A$ is a simple point, otherwise compound.

> e.g.
> 
> $S = \{1,2,3,4,5,6\}$
> $A = \{1\} \leftarrow$ simple
> $B = \{2,4,6\} \leftarrow$ compound.

Assign so that

1.  $0 \le P(a_i) \le 1$

2.  $\sum_{i}P(a_i) = 1$

$$
\begin{align*}
    \{P(a_i): i = 1,2,3,\ldots\} \quad =\text{probability distribution}
\end{align*}
$$

$S = \{a_1,a_2,\ldots\}$ discrete, $A \subset S$ is an event.
$$
\begin{align*}
    P(A) = \sum_{a_i \in A}P(a_i)
\end{align*}
$$

$A$ = Number is odd

$P(i) = \frac{1}{6}$ for $1,2,3,4,5,6$ 
$$
\begin{align*}
    P(A) &= P(1) + P(3) + P(5) \\
    &= \frac{1}{6} + \frac{1}{6} + \frac{1}{6} \\
    &= \frac{3}{6} \\
    &= \frac{1}{2}
\end{align*}
$$

Sample space $S$ is equally likely if probability of every outcome is the same.

$|A| = \#$ of elements in set. 
$$
\begin{align*}
    1 = P(S) = \sum_{i=1}^{|S|}P(a_i) &= P(a_i)|S| \\
    P(a_i)&=\frac{1}{|S|}
\end{align*}
$$

$$
\begin{align*}
    P(A) = \sum_{i: a_i \in A} P(a_i) = \frac{|A|}{|S|}
\end{align*}
$$

# Probability and Counting Techniques

> [!check] Fact
> $A$ and $B$ are disjoint $A \cap B = \emptyset$, then 
> $$
> \begin{align*}
>     |A \cup B| = |A| + |B|
> \end{align*}
> $$

## Addition and Multiplication Rules

<u>Addition Rule</u>

Sum larger than 8.

$B =$ Sum of Die larger than 8

$A_9 =$ Sum 9, $A_{10}=$ Sum 10, $A_{11} =$ Sum 11, $A_{12} =$ Sum 12.

$B = A_{9} \cup A_{10} \cup A_{11} \cup A_{12}$ all $A_j$ are disjoint.

$$
\begin{align*}
    |B| &= |A_9| + |A_{10}| + |A_{11}| + |A_{12}| \\
    &= 4 + 3 + 2 + 1 \\
    & = 10
\end{align*}
$$

> [!info] Definition
> Thus,
> $$
> \begin{align*}
>     |A| = |\bigcup_{i=1}^{n}A_i| = \sum_{i=1}^n|A_i|
> \end{align*}
> $$

<u>Multiplication Rules</u>

Ordered $k-$tuple, $(a_1, a_2, \ldots, a_k)$. $n_1$ choices for $a_1$, $n_k$ choices for $a_k$ etc.

> [!info] Definition
> $|A| = n_1n_1 \ldots n_k = \prod_{i=1}^kn_i$

If there are $p$ ways to do task 1, and $q$ ways to do task 2, there are $p \times q$ ways to do tasks 1 and 2.

With replacement: When the object is selected, put it back after.

Without replacement: Once an object is picked, it stays out of the pool.

## Counting Arrangements or Permutations

> [!info] Definition
> <u>Factorials</u>
> 
> $n$ distinct objects, $n$ factorial. 
> $$
> \begin{align*}
>     n! = n \cdot (n-1) \cdot (n - 2) \cdots 2 \cdot 1
> \end{align*}
> $$

$0! = 1$ and $n! = n \cdot (n-1)!$

10 people standing next to each other, $10! = 3628800$ arrangements.

Out of 5 students, must choose 1 president and 1 secretary. $5 \times 4 = 20$.

Note, Stirling's Approximation. 
$$
\begin{align*}
    n! \approx \sqrt{2\pi n}\left(\frac{n}{e}\right)^n
\end{align*}
$$

> [!info] Definition
> <u>Permutations</u>
> 
> $n$ distinct objects, permutation of size $k$ is an <u>ordered</u> subset of $k$ individuals. (without replacement)
> $$
> \begin{align*}
>     n^{(k)} = n(n-1) \ldots (n-k+1) = \frac{n!}{(n-k)!}
> \end{align*}
> $$

With replacement, 
$$
\begin{align*}
    n^k = n(n)\ldots(n) \quad k \text{ times}
\end{align*}
$$

$n$ to the $k$ factors.

Our example of president and secretary above can thus be seen as $5^{(2)} = 5 \times 4$.

## Counting Subsets or Combinations

> [!question]
> If we have $5$ members on a club, how can we select $2$ to serve on a committee?

Here, order does not matter. Unlike a permutation, this is a combination.

In general, if we have $k$ objects, there are $k!$ ways to reorder such objects. We can therefore get the combination count by dividing the permutation count $n^{(k)}$ by the number of ways of ordering the objects $k!$.

> [!info] Definition
> <u>Definition</u>
> 
> Given $n$ distinct objects, a combination of size $k$ is an unordered subset of $k$ of the objects (without replacement). The number of combinations of size $k$ taken from $n$ objects is denoted
> $\binom{n}{k}$, which reads \"$n$ choose $k$, and 
> $$
> \begin{align*}
>     \binom{n}{k} = \frac{n^{(k)}}{k!} = \frac{n!}{(n-k)!k!}
> \end{align*}
> $$

For combinatorial proofs of these identities see [[MATH239]].

> For our previous example we have
> 
> $$
> \begin{align*}
>     \binom{n}{k} &= \frac{n!}{(n-k)!k!}\\
>     &= \frac{5!}{3!2!}\\
>     &= 10
> \end{align*}
> $$

<u>Properties of $\binom{n}{k}$</u>

1.  $n^{(k)} = \frac{n!}{(n-k)!} = n(n-1)^{(k-1)}$ for $k \ge 1$

2.  $\binom{n}{k} = \frac{n!}{k!(n-k)!} = \frac{n^{(k)}}{k!}$

3.  $\binom{n}{k} = \frac{n!}{(n-k)!k!} = \frac{n!}{(n-(n-k))!(n-k)!} = \binom{n}{n-k}$

4.  If we define $0! = 1$, then $\binom{n}{0} = \binom{n}{n} = 1$

5.  $\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$

6.  Binomial Theorem $(1 + x)^n = \binom{n}{0} + \binom{n}{1}x + \binom{n}{2}x^2 + \ldots + \binom{n}{n}x^n$

> <u>Example</u>
> 
> Group of $5$ women and $7$ men, a committee of $2$ women and $3$ men is formed at random. $2$ of them men dislike each other. What is the probability they don't serve together?
> 
> First, get the size of the sample space $|S|$.
> 
> Pick $2$ women from $5$ women, $\binom{5}{2}$
> 
> Pick $3$ men from $7$ men, $\binom{7}{3}$
> 
> Thus $|S| = \binom{5}{2}\binom{7}{3}$
> 
> Consider the event $A = \{1$ and $2$ do not serve in the committee together$\}$
> 
> Consider $A^{\complement} = \{$ 1 and 2 in the committee together$\}$
> 
> The size of the sample space $|A^{\complement}|$ is given by:
> 
> Pick $2$ women from $5$ women, $\binom{5}{2}$.
> 
> $1$ and $2$ are in the committee already, we need to pick $1$ man from the $5$ left, $\binom{5}{1}$.
> 
> Thus, 
> $$
> \begin{align*}
>     P(A) = 1 - P(A^{\complement}) = 1 - \frac{|A^{\complement}|}{|S|} = 1 - \frac{\binom{5}{2}\binom{5}{1}}{\binom{5}{2}\binom{7}{3}} = \frac{\binom{5}{2}[\binom{7}{3} - \binom{5}{1}]}{\binom{5}{2}\binom{7}{3}}
> \end{align*}
> $$

## Arrangements when Symbols are Repeated

> [!info] Definition
> <u>Definition</u>
> 
> Consider $n$ objects of $k$ types. Suppose $n_1$ objects of type $1$, $n_2$ objects of type $2$, and $n_k$ objects of type $k$. Thus there are,
> 
> $$
> \begin{align*}
>     \frac{n!}{n_1!n_2!\ldots n_k!}
> \end{align*}
> $$
> distinguishable arrangements of $n$ objects. This is the multinomial coefficient.

> Letters of \"SLEEVELESS\" are arranged at random. What is the probability the word begins and ends with \"S\"?
> 
> Sample space, $|S| = \frac{10!}{4!3!2!1!} = 12600$
> 
> Event, $|A| = \frac{8!}{1!4!2!1!} = \frac{40320}{48} = 840$
> 
> Thus $P(A) = \frac{840}{12600} = \frac{1}{15}$

## Useful Series and Sums

> [!tldr] Theorem
> Finite Geometric Series: 
> $$
> \begin{align*}
>     \sum_{i=0}^{n-1}t^i = 1 + t + t^2 + \ldots + t^{n-1} = \frac{1-t^n}{1-t} \text{ if } t \ne 1\\
> \end{align*}
> $$

> [!tldr] Theorem
> Infinite Geometric series if $|t| < 1$: 
> $$
> \begin{align*}
>     \sum_{x=0}^{\infty} t^x = 1 + t + t^2 + \ldots = \frac{1}{1-t}
> \end{align*}
> $$

> [!tldr] Theorem
> Binomial Theorem $(i)$, if $n$ is a positive integer and $t$ is any real number: 
> $$
> \begin{align*}
>     (1+t)^n = 1 + \binom{n}{1}t^2 + \binom{n}{2}t^2 + \ldots + \binom{n}{n}t^n = \sum_{x=0}^n \binom{n}{x}t^x
> \end{align*}
> $$

> [!tldr] Theorem
> Binomial Theorem $(ii)$, if $n$ is not a positive integer but $|t| < 1$:
> $$
> \begin{align*}
>     (1+t)^n = \sum_{x=0}^{\infty}\binom{n}{x}t^x
> \end{align*}
> $$

> [!tldr] Theorem
> Multinomial Theorem: 
> 
> $$
> \begin{align*}
>     (t_1 + t_2 + \ldots t_k)^n  = \sum \frac{n!}{x_1!x_2! \ldots x_k!}t_1^{x_1}t_2^{x_2}\ldots t_k^{x_k}
> \end{align*}
> $$
> where the summation is over all non-negative integers $x_1, x_2, \ldots, x_k$ such that $\sum_{i=1}^{k}x_i = n$ where $n$ is a positive integer.

> [!tldr] Theorem
> Hypergeometric Identity: 
> $$
> \begin{align*}
>     \binom{a+b}{n} = \sum_{x=0}^{\infty}\binom{a}{x}\binom{b}{n-x}
> \end{align*}
> $$

> [!tldr] Theorem
> Exponential Series: 
> 
> $$
> \begin{align*}
>     e^t = \frac{t^0}{0!} + \frac{t^1}{1!} + \frac{t^2}{2!} + \ldots = \sum_{x=0}^{\infty}\frac{t^n}{n!}
> \end{align*}
> $$
> for all $t$ in the real numbers.

A related identity: 
$$
\begin{align*}
    e^t = \lim_{n \to \infty}\left(1 + \frac{t}{n}\right)^n
\end{align*}
$$

Series involving integers: 
$$
\begin{align*}
    1 + 2 + 3 + \ldots + n &= \frac{n(n+1)}{2}\\
    1^2 + 2^2 + 3^3 + \ldots + n^2 &= \frac{n(n+1)(2n+1)}{6}\\
    1^3 + 2^3 + 3^3 + \ldots + n^3 &= \left[\frac{n(n+1)}{2}\right]^2
\end{align*}
$$

# Probability Rules and Conditional Probability

## General Methods

Rules: $P(S) = \sum_{\text{all} i} P(a_i) = 1$

For any event $A, 0 \le P(A) \le 1$.

If $A$ and $B$ are two events with $A \subseteq B$, then $P(A) \le P(B)$.

> [!check] Fact
> <u>Fundamental Laws of Set Algebra</u>
> 
> Commutativity 
> $$
> \begin{align*}
>     A \cup B = B \cup A \quad A \cap B = B \cap A
> \end{align*}
> $$
> 
> Associativity 
> $$
> \begin{align*}
>     (A \cup B) \cup C &= A \cup (B \cup C) \\
>     (A \cap B) \cap C &= A \cap (B \cap C)
> \end{align*}
> $$
> 
> Distributivity 
> $$
> \begin{align*}
>     A \cup (B \cap C) = (A \cup B) \cap (A \cup C)\\
>     A \cap (B \cup C) = (A \cap B) \cup (A \cap C)
> \end{align*}
> $$
> 
> <u>De Morgan's Law</u> 
> $$
> \begin{align*}
>     (\overline{A \cup B}) = \overline{A} \cap \overline{B}
> \end{align*}
> $$
> The complement of a union is the intersection of the complements. 
> 
> $$
> \begin{align*}
>     (\overline{A \cap B}) = \overline{A} \cup \overline{B}
> \end{align*}
> $$
> The complement of an intersection is the union of the complements.
> 
> Applied for $n$ events 
> $$
> \begin{align*}
>     \overline{(A_1 \cup A_2 \cup \ldots \cup A_n)} = \overline{A_1} \cap \overline{A_2} \cap \ldots \cap \overline{A_n}
> \end{align*}
> $$

## Rules for Unions of Events

For arbitrary events $A,B, C$,

> [!check] Fact
> If $A$ and $B$ are <u>disjoint</u> $(A \cap B = \emptyset)$ then,
> $$
> \begin{align*}
>     P(A \cup B) = P(A) + P(B)
> \end{align*}
> $$

> [!check] Fact
> What if $A \cap B \ne \emptyset$?
> 
> Then 
> $$
> \begin{align*}
>     P(A \cup B) = P(A) + P(B) - P(A \cap B)
> \end{align*}
> $$

> [!check] Fact
> The probability of the complement event is, 
> $$
> \begin{align*}
>     P(A) = 1 - P(\overline{A})
> \end{align*}
> $$
> 
> If $A,B,$ and $C$ are disjoint (mutually exclusive), then
> $$
> \begin{align*}
>     P(A \cup B \cup C) = P(A) + P(B) + P(C)
> \end{align*}
> $$
> 
> Otherwise, 
> $$
> \begin{align*}
>     P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)
> \end{align*}
> $$
> 
> In general,
> $$
> \begin{align*}
>     P(\bigcup_{i=1}^nA_1) = \sum_{i}P(A) - \sum_{i < j}P(A_iA_j) + \sum_{i < j < k}P(A_iA_jA_k) - \sum_{i < j < k < 1}P(A_iA_jA_kA_1) + \ldots
> \end{align*}
> $$

Note, $P(A \cap B)$ is often written as $P(AB)$

## Intersection of Events and Independence

<u>Independent Events</u>

Rolling die twice is an example of independent events. The outcome of the first doesn't affect the second.

> [!info] Definition
> Events are independent if and only if 
> $$
> \begin{align*}
>     P(A \cap B) = P(A)P(B)
> \end{align*}
> $$

$A =$\"roll $6$ on first\" $B =$\"roll $6$ on second\"

$$
\begin{align*}
    P(A \cap B) = P(\text{"both 6"}) = \frac{1}{36} = P(A)P(B)
\end{align*}
$$

Not independent. $C=$ First roll is $6$, $D=$ first roll is even.

$P(C \cap D) = \frac{1}{6}$

$$
\begin{align*}
    P(C)P(D) = \frac{1}{12} \ne P(C \cap D)
\end{align*}
$$

A common misconception is that if $A$ and $B$ are mutually exclusive, then $A$ and $B$ are independent.

> [!check] Fact
> If $A$ and $B$ are independent, $A$ and $\overline{B}$ are independent. Law of total probability. 
> $$
> \begin{align*}
>     P(A \cap \overline{B})\\
>     &= P(A) - P(A \cap B) \\
>     &= P(A) - P(A)P(B) \\
>     &= P(A)[1-P(B)] \\
>     &= P(A)P(\overline{B})
> \end{align*}
> $$

> [!check] Fact
> We can also see, 
> $$
> \begin{align*}
>     &P(A) = P(A \cap B) + P(A \cap \overline{B})
> \end{align*}
> $$

## Conditional Probability

> [!info] Definition
> $P(A|B)$ represents the probability that event $A$ occurs, when we know that $B$ occurs. This is the conditional probability of $A$ given $B$.
> $$
> \begin{align*}
>     P(A|B) = \frac{P(A \cap B)}{P(B)} \quad \text{provided } P(B) > 0
> \end{align*}
> $$

> [!check] Fact
> If $A$ and $B$ are independent, then 
> $$
> \begin{align*}
>     &P(A \cap B) = P(A)P(B)\\
>     &P(A|B) = \frac{P(A)P(B)}{P(B)} = P(A) \quad \text{provided } P(B) > 0
> \end{align*}
> $$
> 
> $A$ and $B$ are independent events if and only if either of the following statements is true 
> $$
> \begin{align*}
>     P(A|B) = P(A) \quad \text{or} \quad P(B|A) = P(B)
> \end{align*}
> $$

> <u>Example</u>
> 
> $A$ = The sum of two die is 10
> $B$ = The first die is 6 
> $$
> \begin{align*}
>     P(B|A) = \frac{P(B \cap A)}{P(A)} = \frac{\frac{1}{36}}{\frac{3}{36}} = \frac{1}{3}
> \end{align*}
> $$

If $P(A) = 0$ or $P(B) = 0$, then $A$ and $B$ are independent.

Properties

-   $P(B|B) = 1$

-   $0 \le P(A|B) \le 1$

-   If $A \subseteq C, P(A|B) \le P(C|B)$

-   $P(A_1 \cup A_2 | B) = P(A_1 | B) + P(A_2 | B) - P(A_1 \cap A_2 | B)$

-   If $A_1$ and $A_2$ are disjoint:    $P(A_1 \cup A_2 | B) = P(A_1|B) + P(A_2|B)$

-   $P(\overline{A}|B) = 1 - P(A|B)$

## Product Rules, Law of Total Probability and Bayes' Theorem

> [!check] Fact
> <u>Product Rules</u>
> 
> For events $A$ and $B$, 
> $$
> \begin{align*}
>     P(A \cap B) = P(B)P(A|B) = P(A)P(B|A)
> \end{align*}
> $$

That means if we know $P(A|B)$ and $P(B)$; or $P(B|A)$ and $P(A)$, we can find $P(A \cap B)$.

More events:

-   $P(A \cap B) = P(A)P(B|A)$

-   $P(A \cap B \cap C) = P(A)P(B|A)P(C|A \cap B)$

-   $P(A \cap B \cap C \cap D) = P(A)P(B|A)P(C|A \cap B)P(D | A \cap B \cap C)$

> [!info] Definition
> <u>Law of Total Probability</u>
> 
> Let $A_1, A_2, \ldots, A_k$ be a partition of the sample space $S$ into disjoint (mutually exclusive) events, that is
> 
> $$
> \begin{align*}
>     A_1 \cup A_2 \cup \ldots \cup A_k = S \quad \text{and} \quad A_i \cap A_j = \emptyset \text{ if } i \ne j
> \end{align*}
> $$
> Let $B$ be an arbitrary event in $S$. Then
> $$
> \begin{align*}
>     P(B) &= P(BA_1)+ P(BA_2) + \ldots + P(BA_k)\\
>     &= \sum_{i=1}^k P(B|A_i)P(A_i)
> \end{align*}
> $$
> 
> A common way in which this is used is that 
> 
> $$
> \begin{align*}
>     P(B) = P(B|A)P(A) + P(B|\overline{A})P(\overline{A})
> \end{align*}
> $$
> since $A$ and $\overline{A}$ partition $S$.

> [!tldr] Theorem
> 
> <u>Bayes Theorem</u>
> Suppose $A$ and $B$ are events defined on a sample space $S$. Suppose also that $P(B) > 0$. Then 
> $$
> \begin{align*}
>     P(A|B) = \frac{P(B|A)P(A)}{P(B)} = \frac{P(B|A)P(A)}{P(B|\overline{A})P(\overline{A}) + P(B|A)P(A)}
> \end{align*}
> $$

Proof: 
$$
\begin{align*}
    \frac{P(B|A)P(A)}{P(B|\overline{A})P(\overline{A}) + P(B|A)P(A)} &= \frac{P(AB)}{P(\overline{A}B)+ P(AB)}\\
    &= \frac{P(AB)}{P(B)} \\
    &= P(A|B) \quad \blacksquare
\end{align*}
$$


# Discrete Random Variables

## Random Variables and Probability Functions

> [!info] Definition
> 
> A random variable is a function that assigns a real number to each point in a sample space $S$. Often a random variable is abbreviated with RV or rv.

> [!info] Definition
> 
> The values that a random variable can take on are called the range of the random variable. We often denote the range of a random variable $X$ by $X(S)$.

> <u>Example</u>
> 
> If we roll a 6-sided dice, our sample space is $S = \{(1,1),(1,2),\ldots,(6,5),(6,6)\}$ and if we define $X =$ sum of die rolls, the range is $\{2,3,\ldots,11,12\}$

> [!info] Definitions
> 
> We say that a random variable is discrete if it takes values in a countable set (finite or countably infinite).
> 
> We say that a random variable is continuous if it takes values in some interval of real numbers, e.g. $[0,1],(0,\infty),\mathbb{R}$.
> 
> Important: Don't forget that a random variable can be infinite and discrete.

> [!info]Definition
> 
> Let $X$ be a discrete random variable with range $A$. The probability function (p.f.) of $X$ is the function 
> 
> $$
> \begin{align*}
>     f(x) = P(X=x), \quad \text{defined for all } x \in A
> \end{align*}
> $$

The set of pairs $\{(x,f(x)):x \in A\}$ is called the probability distribution of $X$.

A probability function has two important properties:

1.  $0 \le f(x) \le 1$ for all $x \in A$

2.  $\sum_{\text{all } x \in A}f(x) = 1$

> <u>Example</u>
> 
> A random variable $X$ has a range $A = \{0,1,2\}$ with $f(0) = 0.19, f(1) = 0.2k^2, f(2) = 0.8k^2$, what values of $k$ makes $f(x)$ a probability function.
> 
> From our rules, 
> $$
> \begin{align*}
>     &0.19 + 0.2k^2 + 0.8k^2 = 0.19 + k^2 = 1 \\
>     \implies &k^2 = 0.81 \\
>     &k = \pm 0.9
> \end{align*}
> $$

> [!info] Definition
> The Cumulative Distribution Function (CDF) of a random variable $X$ is 
> 
> $$
> \begin{align*}
>     F(x) = P(X \le x), \text{ define for all } x \in \mathbb{R}
> \end{align*}
> $$
> We use the shorthand that $X \sim F$ if $X$ has CDF $F$. Here, 
> 
> $$
> \begin{align*}
>     P(X \le x) = P(\{a \in S: X(a) \le x\})
> \end{align*}
> $$
> where $\{X \le a\}$ is the event that contains all outcomes with $X(a) \le x$.
> 
> In general, for any $x \in \mathbb{R}$ 
> $$
> \begin{align*}
>     F(x) = P(X \le x) = \sum_{u \le x}P(X = u) = \sum_{u \le x}f(u)
> \end{align*}
> $$

The CDF satisfies that

1.  $0 \le F(x) \le 1$

2.  $F(x) \le F(y)$ for $x < y$ (and we say $F(x)$ is a non-decreasing function of $x$)

3.  $\lim_{x \to -\infty}F(x) = 0$, and $\lim_{x\to\infty}F(x) = 1$

4.  $\lim_{x \to a^+}F(x) = F(a)$ (right continuous)

If $X$ takes value on $a_1 < a_2 < \ldots < a_n < \ldots$, we can get probability function from CDF: 
$$
\begin{align*}
    f(a_i) = F(a_i) - F(a_{i-1})
\end{align*}
$$

In general, we have 
$$
\begin{align*}
    P(a<X\le b) = F(b) - F(a)
\end{align*}
$$

Note, we often use
$$
\begin{align*}
    P(X \ge 1) = 1 - P(X < 1) = 1-P(x \le 0)
\end{align*}
$$

> [!info] Definition
> <u>Definition</u>
> 
> Two random variables $X$ and $Y$ are said to have the same distribution if $F_X(x) = F_Y(x)$ for all $x \in \mathbb{R}$. We denote this by
> 
> $$
> \begin{align*}
>     X \sim Y
> \end{align*}
> $$

Note, $X$ and $Y$ having the same distribution does not mean $X = Y$.

## Discrete Uniform Distribution

<u>Setup</u>

Suppose the range of $X$ is $\{a,a+1,\ldots,b\}$ where $a$ and $b$ are integers and suppose all values are equally probable. Then $X$ has a Discrete Uniform Distribution on the set $\{a,a+1,\ldots,b\}$. The
variables $a$ and $b$ are called the parameters of the distribution.

<u>Illustrations</u>

If $X$ is the number obtained when a die is rolled, then $X$ has a discrete Uniform distribution with $a = 1$ and $b = 6$.

> [!info] Definition
> <u>Probability Function</u>
> 
> There are $b-a+1$ values in the set $\{a,a+1,\ldots,b\}$ so the probability of each value must be $\frac{1}{b-a+1}$ in order for $\sum_{x=a}^bf(x) = 1$. Therefore 
> $$
> \begin{align*}
>     f(x) = P(X=x) = \begin{cases}
>         \frac{1}{b-a+1} \quad \text{for } x = a,a+1,\ldots,b\\
>         0 \quad \text{otherwise}
>     \end{cases}
> \end{align*}
> $$

> <u>Example</u>
> 
> Suppose a fair die is thrown once and let $X$ be the number on the face. Find the cumulative distribution function of $X$.
> 
> <u>Solution</u>
> 
> This is an example of a Discrete Uniform distribution on the set $\{1,2,3,4,5,6\}$ having $a=1,b=6$ and probability function
> 
> $$
> \begin{align*}
>     f(x) = P(X=x) = \begin{cases}
>         \frac{1}{6} \quad \text{for } x = 1,2,\ldots,6\\
>         0 \quad \text{otherwise}
>     \end{cases}
> \end{align*}
> $$
> The cumulative distribution function is $F(x) = P(X\le x)$, 
> 
> $$
> \begin{align*}
>     F(x) = P(X \le x) = \begin{cases}
>         0 \quad \text{for } x < 1\\
>         \frac{[x]}{6} \quad \text{for } 1 \le x < 6\\
>         1 \quad \text{for} x \ge 6
>     \end{cases}
> \end{align*}
> $$
> where $[x]$ is the largest integer less than or equal to $x$.

> <u>Example</u>
> 
> Let $X$ be the largest number when a die is rolled 3 times. First find the cumulative distribution function, and then find the probability function of $X$.
> 
> <u>Solution</u>
> 
> This is another example of a distribution constructed from the Discrete Uniform. 
> $$
> \begin{align*}
>     S = \{(1,1,1),(1,1,2),\ldots,(6,6,6)\}
> \end{align*}
> $$
> 
> The probability that the largest number is less than or equal to $x$ is,
> 
> $$
> \begin{align*}
>     F(x) = \frac{x^3}{6^3}
> \end{align*}
> $$
> for $x = 1,2,3,4,5,6$. Here is the CDF for all real values of $x$: 
> 
> $$
> \begin{align*}
>     F(x) = P(X \le x) = \begin{cases}
>         \frac{[x]^3}{216} \quad \text{for } 1 \le x < 6\\
>         0 \quad \text{for } x < 1\\
>         1 \quad \text{for } x \ge 6
>     \end{cases}
> \end{align*}
> $$


To find the p.f. we may use the fact that $x \in \{1,2,3,4,5,6\}$ we have $P(X = x) = P(X \le x) - P(X < x)$ so that 

$$
\begin{align*}
    f(x) &= F(x) - F(x-1)\\
    &= \frac{x^3-(x-1)^3}{216}\\
    &=\frac{[x-(x-1)][x^2+x(x-1)+(x-1)^2]}{216}\\
    &=\frac{3x^2 - 3x + 1}{216} \quad \text{for } x = 1,2,3,4,5,6 \quad \blacksquare
\end{align*}
$$


## Hypergeometric Distribution

<u>Setup</u>

Consider a population of $N$ objects, of which $r$ are considered \"successes\" (S) and the remaining $N-r$ are considered \"failures\" (F).

Suppose that a subset of size $n$ is chosen at random from the population without replacement

We say that the random variable $X$ has a hypergeometric distribution if $X$ denotes the number of successes in the subset (shorthand: $X \sim hyp(N,r,n)$).

-   $N$: Number of objective

-   $r$: Number of successes

-   $n$: Number of draws

<u>Illustrations</u>

Drawing $2$ balls without replacement from a bag with $3$ blue balls and $4$ red balls. Let $X$ denote the number of blue balls drawn. Then
$$
\begin{align*}
    X \sim hyp(7,3,2)
\end{align*}
$$

Drawing $5$ cards from a deck of cards. Let $X$ denote the number of aces. Then 
$$
\begin{align*}
    X \sim hyp(52,4,5)
\end{align*}
$$

> [!info] Definition
> <u>Probability Function</u>
> 
> Suppose $X \sim hyp(N,r,n)$ 
> $$
> \begin{align*}
>     f_X(x) = \frac{\binom{r}{x}\binom{N-r}{n-x}}{\binom{N}{n}} \quad max\{0,n-(N-r)\} \le x \le min\{r,n\}
> \end{align*}
> $$

$x \le min\{r,n\}$

-   $x \le n$: the number of successes drawn cannot exceed the number drawn

-   $x \le r$: we have at most $r$ success

$x \ge max\{0,n-(N-r)\}$

-   $x \ge 0$ obviously

-   $x \ge n - (N-r)$: if $n$ exceeds the number of failures $N-r$, we have at least $n-(N-r)$ of successes.

We can verify the probability function of the hypergeometric distribution sums to $1$. 
$$
\begin{align*}
    \sum_{\text{all }x}f_X(x) = \sum_{\text{all }x}\frac{\binom{r}{x}\binom{N-r}{n-x}}{\binom{N}{n}} = \frac{1}{\binom{N}{n}}\sum_{\text{all }x}\binom{r}{x}\binom{N-r}{n-x} = \frac{\binom{r+N-r}{n}}{\binom{N}{n}} = 1
\end{align*}
$$

> <u>Example</u>
> 
> Consider drawing a $5$-card hand at random from a standard $52$-card deck. What is the probability that the hand contains at least $3$ K's?
> 
> $X:$ the number of K in hand.
> Success type: $13$ K's Failure type: Not K cards
> $N = 52 \quad r = 13 \quad n = 5$
> $X \sim hyp(52,13,5)$ 
> $$
> \begin{align*}
>     P(X \ge 3) &= P(X = 3) + P(X = 4) + P(X = 5)\\
>     &= \frac{\binom{13}{3}\binom{39}{2}}{\binom{52}{5}} + \frac{\binom{13}{4}\binom{39}{1}}{\binom{52}{5}} + \frac{\binom{13}{5}\binom{39}{0}}{\binom{52}{5}} \\
>     &= 0.00175
> \end{align*}
> $$

## Binomial Distribution

> [!info] Definition
> <u>Definition</u>
> 
> A Bernoulli trial with probability of success $p$ is an experiment that results in either a success or failure, and the probability of success is $p$.

<u>Setup</u>

Consider an experiment in which $n$ Bernoulli trials are independently formed, each with probability of success $p$. $X$ denotes the number of successes from $n$ trials. 

$$
\begin{align*}
    X \sim Binomial(n,p)
\end{align*}
$$
<u>Illustrations</u>

Flip a coin independently $20$ times, let $X$ denote the number of heads observed. Then 

$$
\begin{align*}
    X \sim Binomial(20,0.5)
\end{align*}
$$


Drawing $2$ balls with replacement from a bag with $3$ blue balls and $4$ red balls. Let $X$ denote the number of blue balls drawn. 

$$
\begin{align*}
    X \sim Binomial(2,\frac{3}{7})
\end{align*}
$$


Assumptions:

1.  Trials are independent

2.  The probability of success, $p$, is the same in each Bernoulli trial

> [!info] Definition
> <u>Probability Function</u> 
> $$
> \begin{align*}
>     f(x) = \binom{n}{x}p^x(1-p)^{n-x} \quad x = 0,1,\ldots,n
> \end{align*}
> $$

Proof that $\sum_{\text{all} x} f(x) = 1$ for $0 < p < 1$:
$$
\begin{align*}
    \sum_{x=0}^nf(x) &= \sum_{x=0}^n\binom{n}{x}p^x(1-p)^{n-x}\\
    &= (1-p)^n \sum_{x=0}^n\binom{n}{x}\left(\frac{p}{1-p}\right)^x\\
    &= (1-p)^n \left(1 + \frac{p}{1-p}\right)^n \\
    &= (1-p)^n\left(\frac{1-p+p}{1-p}\right)^n \\
    &= 1^n = 1
\end{align*}
$$

If $N$ is very large, and we keep the number of success $r = pN$ where $p \in (0,1)$. We choose a relatively small $n$ without replacement from $N$.

Let $X \sim hyp(N,r,n)$ and $Y \sim Binomial(n,p)$. Then
$$
\begin{align*}
    P(X = k) \approx P(Y=k)
\end{align*}
$$

The approximation is good if $N$ and $r$ are large compared to $n$.

## Negative Binomial Distribution

<u>Setup</u>

Consider an experiment in which Bernoulli trials are independently performed, each with probability of success $p$, until exactly $k$ successes are observed. Then if $X$ denotes the number of failures before observing $k$ successes, we say that $X$ is Negative Binomial with parameters $k$ and $p$. 

$$
\begin{align*}
    X \sim NB(k,p)
\end{align*}
$$
Let $Y$ be the number of trials until exactly $k$ successes are observed. We have $Y = X + k$.

<u>Illustrations</u>

Flip a coin until $5$ heads are observed, and let $X$ denote the number of tails observed. Then 

$$
\begin{align*}
    X \sim NB(5,0.5)
\end{align*}
$$


> [!info] Definition
> <u>Probability Function</u>
> 
> $$
> \begin{align*}
>     f(x) = \binom{x + k-1}{k-1}p^k(1-p)^k, \quad x = 0,1,2,\ldots
> \end{align*}
> $$


Proof it is valid 

$$
\begin{align*}
    \sum_{x=0}^{\infty}f(x) &= \sum_{x=0}^{\infty}\binom{-k}{x}(-1)^xp^k(1-p)^k\\
    &= p^k \sum_{x=0}^{\infty}\binom{-k}{x}[(-1)(1-p)]^x \\
    &= p^k[1 + (-1)(1-p)]^{-k} \quad \text{if } 0 < p < 1\\
    &= p^kp^{-k}\\
    &= 1 \blacksquare
\end{align*}
$$


## Geometric Distribution

<u>Setup</u>

Geometric distribution is a special case of the Negative Binomial where we stop after the first success $k=1$. 
$$
\begin{align*}
    X \sim Geo(p)
\end{align*}
$$

> [!info] Definition
> <u>Probability Function</u> 
> $$
> \begin{align*}
>     f(x) = (1-p)^xp, \quad x = 0,1,2,3,\ldots
> \end{align*}
> $$

Geometric Distribution: CDF
For an integer $x$, the CDF of $X$ is 

$$
\begin{align*}
    F(x) &= P(X \le x)\\
    &= \sum_{t=0}^x(1-p)^xp\\
    &=p\sum_{t=0}^x(1-p)^x\\
    &=p\frac{1-(1-p)^{x+1}}{1-(1-p)}\\
    &= 1-(1-p)^{x+1}
\end{align*}
$$
So $F(x) = 1 - (1-p)^{[x]+1}$ for $x \ge 0$, and 0 otherwise.

> <u>Example</u>
> 
> The number of times I have to roll $2$ dice before I get snake eyes.
> 
> $$
> \begin{align*}
>     X \sim Geo(\frac{1}{36})
> \end{align*}
> $$


## Poisson Distribution (from Binomial)

As $n \to \infty$ and $p \to 0$, the binomial function approaches

$$
\begin{align*}
    f(x) \approx e^{-\mu}\frac{\mu^x}{x!}
\end{align*}
$$
for $\mu = np$

<u>Setup</u>

Let $\mu = np$. Then if $n$ is large, and $p$ is close to zero,

$$
\begin{align*}
    \binom{n}{x}p^x(1-p)^{n-x} \approx e^{-\mu}\frac{\mu^x}{x!}
\end{align*}
$$


> [!info] Definition
> <u>Probability Function</u>
> 
> A random variable $X$ has a Poisson distribution with parameter $\mu$ ($X \sim Poission(\mu)$) if 
> $$
> \begin{align*}
>     f(x) = e^{-\mu}\frac{\mu^x}{x!}, \quad x=0,1,2,3,\ldots
> \end{align*}
> $$

## Poisson Distribution from Poisson Process

A process satisfying the following $3$ conditions is called a Poisson process.

1.  Independence: The number of occurrences in non-overlapping intervals are independent. For $t > s, (X_t - X_s)$ and $X_s$ are independent.

2.  Individuality or Singularity: Events occur singly, not in clusters. $P(2$ or more events in $(t,t+\Delta t)) = o(\Delta t)$ as $\Delta t \to 0$.

3.  Homogeneity or Uniformity: Events occur at a uniform rate $\lambda$ (in events per unit of time). $P($one event in $(t,t+\Delta t)) = \lambda \Delta_t + o(\Delta t)$ as $\Delta t \to 0.$

<u>Little o</u>

A function $g(\Delta t)$ is $o(\Delta t)$ as $\Delta t \to 0$ if
$$
\begin{align*}
    \lim_{\Delta t \to 0}\frac{g(\Delta t)}{\Delta t} = 0
\end{align*}
$$

Poisson Distribution

If $X_t$ is a Poisson counting process with a rate of $\lambda$ per unit. Then, 

$$
\begin{align*}
    X_t \sim Poisson(\lambda t)
\end{align*}
$$
and 

$$
\begin{align*}
    f_t(x) = \frac{e^{-\lambda t}(\lambda t)^x}{x!}, \quad \text{for } x = 0,1,2,\ldots
\end{align*}
$$


> <u>Examples</u>
> 
> Suppose that trucks arrive at a receiving dock with an average arrival rate of $3$ per hour. What is the probability exactly $5$ trucks will arrive in a two-hour period?
> 
> We have $\lambda = 3, t = 2$. 
> 
> $$
> \begin{align*}
>     P(X_t = 5) = \frac{e^{-(3 \times 2)}(3 \times 2)^5}{5!}
> \end{align*}
> $$


## Combining Models

> Website hits for a given website occur according to a Poisson process with a rate of $100$ hits per minute. A second is a break if there are no hits in that second.
> 
> What is the probability of a break in any given second?
> 
> $P(A) = \frac{e^{-\lambda}\lambda^0}{0!}=e^{\frac{-100}{60}} = 0.189$
> 
> Compute the probability of observing exactly $10$ breaks in $60$ consecutive seconds.
> 
> $p = P(A) = 0.189$, for $X \sim Binomial(60,p)$
> 
> $$
> \begin{align*}
>     P(X=10 = \binom{60}{10}p^{10}(1-p)^{60-10} = 0.124
> \end{align*}
> $$
> 
> Compute the probability that one must wait for $30$ seconds to get $2$ breaks.
> 
> Let $Y$ be the seconds we wait for $2$ breaks. We want $P(Y=30)$.
> 
> Negative Binomial Distribution: $Y - 1 \sim NB(2,p)$ 
> $$
> \begin{align*}
>     P(Y=30) = P(Y - 1 = 29) = \binom{29}{1}p^2(1-p)^{30-2} = 0.00295
> \end{align*}
> $$

# Expected Value and Variance

## Summarizing Data on Random Variables

Median: A value such that half the results are below it and half above it, when the results are arranged in numerical order.

Mode: Value which occurs most often.

Mean: The mean of $n$ outcomes $x_1, \ldots, x_n$ for a random variable $X$ is $\sum_{i=1}^n\frac{x_i}{n}$

## Expectation of a Random Variable

> [!info] Definition
> Let $X$ be a discrete random variable with $range(X) = A$ and probability function $f(x)$. The expected value of $X$ is given by
> $$
> \begin{align*}
>     E(X) = \sum_{x \in A}xf(x)
> \end{align*}
> $$

Suppose $X$ denotes the outcome of one fair six sided die roll. Compute $E(X)$.

We know $X \sim \mathcal{U}(1,6):$ that is, $f(x) = \frac{1}{6} \quad x=1,2,\ldots,6$.

And so,
$$
\begin{align*}
    E(X) = 1 \times \frac{1}{6} + 2 \times \frac{1}{6} + \ldots + 6 \times \frac{1}{6} = 3.5
\end{align*}
$$

<u>Possible Range</u>

Suppose $X$ is a random variable satisfying $a \le X \le b$ for all possible values of $X$. We have, 
$$
\begin{align*}
    &a \le E(x) \le b
    \\
    a = a\sum_{x \in A}f(x) = \sum_{x \in A}af(x) &\le \sum_{x \in A}xf(x) \le \sum_{x \in A}bf(x) = b\sum_{x \in A}f(x) = b
\end{align*}
$$

<u>Expectation of $g(X)$</u>

Let $X$ be a discrete random variable with $range(X) = A$ and probability function $f(x)$. The expected value of some function $g(X)$ of $X$ is given by 
$$
\begin{align*}
    E[g(X)] = \sum_{x \in A}g(x)f(x)
\end{align*}
$$

<u>Proof</u>
$$
\begin{align*}
    E[g(X)] &= \sum{y \in B}yF_Y(y)\\
    &= \sum_{y \in B}y\sum_{x \in D_y}f(x)\\
    &= \sum_{y \in B}\sum_{x in D_y}g(x)f(x)\\
    &= \sum_{x \in A}g(x)f(x) \quad \blacksquare
\end{align*}
$$

<u>Linearity Properties of Expectation</u>

For constants $a$ and $b$, 
$$
\begin{align*}
    E[ag(X) + b] = aE[g(X)] + b
\end{align*}
$$

<u>Proof</u> 
$$
\begin{align*}
    E[ag(X) + b] &= \sum_{\text{all } x}[ag(x) + b]f(x) \\
    &= \sum_{\text{all }x}[ag(x)f(x) + bf(x)]\\
    &= a\sum_{\text{all }x}g(x)f(x) + b \sum_{\text{all }x}f(x) \\
    &= aE[g(X)] + b \quad \blacksquare
\end{align*}
$$

Thus it is also easy to show 
$$
\begin{align*}
    E[ag_1(X) + bg_2(X)] = aE[g_1(X)] + bE[g_2(X)]
\end{align*}
$$

The expectation of a sum is the sum of the expectations.

## Means and Variances of Distributions

<u>Expected value of a Binomial random variable</u>

Let $X \sim Binomial(n,p)$. Find $E(X)$. 
$$
\begin{align*}
    E(X) &= \sum_{x=0}^n x \binom{n}{x}p^x(1-p)^{n-x}\\
    &= \sum_{x=0}^n x \frac{n!}{x!(n-x)!}p^x(1-p)^{n-x}\\
    &= \sum_{x=1}^n \frac{n(n-1)!}{(x-1)![(n-1)-(x-1)]!}pp^{x-1}(1-p)^{(n-1)-(x-1)}\\
    &= np(1-p)^{n-1}\sum_{x=1}^n \binom{n-1}{x-1}\left(\frac{p}{1-p}\right)^{x-1}\\
    \text{Let } y = x -1\\
    &= np(1-p)^{n-1}\sum_{y=0}^{n-1}\binom{n-1}{y}\left(\frac{p}{1-p}\right)^y \\
    &= np(1-p)^{n-1}\left(1 + \frac{p}{1-p}\right)^{n-1} \\
    &= np(1-p)^{n-1}\frac{(1-p+p)^{n-1}}{(1-p)^{n-1}} \\
    &= np
\end{align*}
$$

> <u>Example</u>
> 
> If we toss a coin $n = 100$ times, with probability $p = 0.5$ of a head, we'd expect 
> $$
> \begin{align*}
>     E[X] = 100 \times 0.5 = 50 \text{ heads}
> \end{align*}
> $$

Hypergeometric Distribution

If $X \sim hyp(N,r,n)$, then $E[X] = n\frac{r}{N}$

Geometric Distribution

If $X \sim Geo(p)$, then $E[X] = \frac{1-p}{p}$

Negative Binomial

If $X \sim NB(k,p)$, then $E[X] = \frac{(1-p)}{p}k$

Poisson Distribution

If $X \sim Poi(\mu)$, then $E[X] = \mu$

<u>Variances of Distribution</u>

Using the expected value is one way of predicting the value of a random variable. But we might want to know \"how likely will observed data be exactly (or close to) the expected value?\"

One may wonder how much a random variable tends to deviate from its mean. Suppose $E[X] = \mu$

Expected deviation:
$$
\begin{align*}
    E[(X - \mu)] = E[X] - \mu = 0
\end{align*}
$$

Expected absolute deviation: 
$$
\begin{align*}
    E[|X - \mu|] = \sum_{x \in A}|X - \mu|f(x)
\end{align*}
$$

Expected squared deviation: 
$$
\begin{align*}
    E[(X-\mu)^2] = \sum_{x \in A}(X-\mu)^2f(x)
\end{align*}
$$

> [!info] Definition
> <u>Variance</u>
> 
> The variance of a random variable $X$ is denoted $Var(X)$, and is defined by 
> 
> $$
> \begin{align*}
>     \sigma^2 = Var(X) = E[(X - E[X])^2]
> \end{align*}
> $$

or sometimes, 
$$
\begin{align*}
    Var(X) = E(X^2) - [E(X)]^2
\end{align*}
$$

We derive this by 
$$
\begin{align*}
    Var(X) &= E[(X - E[X])^2] \\
    &= E[X^2 - 2E[X]X+(E[X])^2] \\
    &= E[X^2] - 2E[X]E[X] + (E[X])^2 \\
    &= E[X^2] - (E[X])^2
\end{align*}
$$

Suppose $X$ satisfies $P(X=0) = \frac{1}{2} = P(X=1)$. What is $Var(X)$?

$E[X] = 0.5 \quad \text{and} \quad E[X^2] = 0.5$
$Var(X) = E[X^2] - E[X]^2 = 0.25$

For all random variables $X$, $Var(X) \ge 0$. $Var(X) = 0$ if and only if $P(X = E[X]) = 1$. $E[X^2] \ge (E[X])^2$

> [!info] Definition
> <u>Standard Deviation</u>
> 
> The standard deviation of a random variable $X$ is denoted $SD(X)$, and defined by
> $$
> \begin{align*}
>     \sigma = SD(X) = \sqrt{Var(X)}
> \end{align*}
> $$

<u>Variance of a Linear Transformation</u>

If $a$ and $b$ are constants, and $Y = aX + b$, then 

$$
\begin{align*}
    Var(Y) = a^2Var(X)
\end{align*}
$$
the constant $b$ does not affect anything. $SD(Y) = aSD(X)$

Variances of distributions 

$$
\begin{align*}
    X \sim Binomial(n,p) &\to Var(X) = np(1-p) \\
    X \sim hyp(N,r,n) &\to Var(X) = n\frac{r}{N}\left(1-\frac{r}{N}\right)\left(\frac{N-n}{N-1}\right) \\
    X \sim Geo(p) &\to Var(X) = \frac{(1-p)}{p^2} \\
    X \sim NB(k,p) &\to Var(X) = \frac{(1-p)}{p^2}k \\
    X \sim Poi(\mu) &\to Var(X) = \mu\\
    X \sim \mathcal{U}(a,b) &\to Var(X) = \frac{(b-a+1)^2-1}{12}
\end{align*}
$$


# Continuous Random Variables

## General Terminology and Notation

> [!info] Definition
> 
> A random variable $X$ is said to be continuous if its range is an interval $(a,b) \subset \mathbb{R}$. $X$ is continuous if it can take any value between $a$ and $b$.
> 
> We can't use $f(x) = P(X = x)$ with continuous distributions because $P(X=x) = 0$.

Suppose $X$ is a crv with range $[0,4]$. We now use integrals instead of sums. 
$$
\begin{align*}
    \int_0^4f(x)dx = 1
\end{align*}
$$

<u>Probability Density Function</u>

We say that a continuous random variable $X$ has probability density function $f(x)$ if
$$
\begin{align*}
    f(x) \ge 0 \quad \forall x \in \mathbb{R}\\
    \int_{-\infty}^{\infty}f(x)dx = 1\\
    P(a \le X \le b) = \int_a^bf(x)dx
\end{align*}
$$

For a four number spinner, if $X$ is where the spinner stops, we can define our pdf as: 
$$
\begin{align*}
    f(x)=\begin{cases}
        0.25 \quad \text{if } 0 \le x \le 4\\
        0 \quad \text{otherwise}
    \end{cases}
\end{align*}
$$

We can see that this satisfies $\int_{-\infty}^{\infty}f(x)dx = 1$

$$
\begin{align*}
    \int_{-\infty}^{\infty} f(x)dx = \int_{-\infty}^0 0dx + \int_0^4 0.25dx + \int_4^{+\infty}0dx = 4 \times 0.25 = 1
\end{align*}
$$

Spinner Example

$P(1 \le X \le 2)$ 
$$
\begin{align*}
    P(1 \le X \le 2) &= \int_1^2f(x)dx \\
    &= \int_1^2 0.25dx \\
    &= 0.25x\vert_1^2 \\
    &= 0.25 \cdot 2 - 0.25 \cdot 1 = 0.25
\end{align*}
$$

> [!info] Definition
> 
> The support of a $pdf f(x)$ is defined as 
> $$
> \begin{align*}
>     supp(f) = \{x \in \mathbb{R}: f(x) \ne 0\}
> \end{align*}
> $$

> <u>Example</u>
> 
> Suppose that $X$ is a continuous random variable with probability density function
> $$
> \begin{align*}
>     f(x) = \begin{cases}
>         cx(1-x) \quad \text{if } 0 \le x \le 1\\
>         0 \quad \text{otherwise}
>     \end{cases}
> \end{align*}
> $$
> 
> Compute $c$ so that this is a valid pdf. 
> $$
> \begin{align*}
>     \int_{-\infty}^{\infty}f(x)dx &= \int_0^1 cx(1-x)dx = 1 \\
>     &\implies c \int_0^1 x - x^2dx = 1 \\
>     &\implies x\left[\frac{x^2}{2}-\frac{x^3}{3}\right]_0^1 = 1\\
>     &\implies c\left[\frac{1}{2} - \frac{1}{3}\right] = 1 \\
>     &\implies c = 6
> \end{align*}
> $$
> 
> Compute $P(X > \frac{1}{2})$ 
> $$
> \begin{align*}
>     P(X > \frac{1}{2}) &= \int_{1/2}^1 6x(1-x)dx \\
>     &= 6\left[\frac{x^2}{2} - \frac{x^3}{3}\right]_{1/2}^1 \\
>     &= 6\left(\left[\frac{1}{2} - \frac{1}{3}\right] - \left[\frac{1/4}{2} - \frac{1/8}{3}\right]\right) \\
>     &= 6\left[\frac{1}{6} - \frac{1}{12}\right] \\
>     &= \frac{1}{2}
> \end{align*}
> $$

Note 
$$
\begin{align*}
    &P(X=a) \ne f(x) \\
    &P(a \le X \le b) = P(a < X < b) = P(a \le X < b) = P(a < x \le b)
\end{align*}
$$

> [!info] Definition
> 
> The Cumulative Distribution Function of a random variable $X$ is
> $$
> \begin{align*}
>     F(x) = P(X \le x)
> \end{align*}
> $$

If $X$ is continuous with pdf $f(x)$, then 
$$
\begin{align*}
    F(x) = \int_{-\infty}^xf(u)du
\end{align*}
$$

By the fundamental theorem of calculus
$$
\begin{align*}
    f(x) = \dfrac{d}{dx}F(x)
\end{align*}
$$

Properties:

1.  $F(x)$ is defined for all real $x$

2.  $F(x)$ is a non-decreasing function of $x$ for all real $x$

3.  $\lim_{x \to -\infty}F(x) = 0$ and $\lim_{x \to \infty}F(x) = 1$

4.  $P(a < X \le b) = F(b) - F(a)$

5.  Since $P(X = a) = 0$, we have $P(a \le X \le b) = F(b) - F(a)$

> Spinner example, 
> $$
> \begin{align*}
>     F(x) = \int_{-\infty}^xf(u)du = \int_0^x 0.25dx = 0.25x
> \end{align*}
> $$
> 
> Thus, 
> $$
> \begin{align*}
>     F(x) = \begin{cases}
>         0 \quad \text{if } x < 0\\
>         0.25x \quad 0 \le x < 4 \\
>         1 \quad x \ge 4
>     \end{cases}
> \end{align*}
> $$
> 
> We can then get the pdf by 
> $$
> \begin{align*}
>     f(x) &= \dfrac{d}{dx}F(x) \\
>     &= \dfrac{d}{dx}0.25x = 0.25
> \end{align*}
> $$

General approach to find $F(x)$ from $f(x)$

-   Treat each piece of $f(x)$ separately

-   Note $F(x) = 0$ for $x <$ the minimum value in the support of $f(x)$

-   Note $F(x) = 1$ for $x \ge$ the maximum value in the support of $f(x)$

-   Find $F(x) = \int_{-\infty}^x f(u)du$

General approach to find $f(x)$ from $F(x)$

-   Treat each piece of $F(x)$ separately

-   Find $f(x) = \dfrac{d}{dx}F(x)$

Note 
$$
\begin{align*}
    P(a \le X \le b) = F(b) - F(a) = \int_{-\infty}^bf(x)dx - \int_{-\infty}^af(x)dx = \int_a^bf(x)dx
\end{align*}
$$

<u>Quantile</u>

Suppose $X$ is a continuous random variable with CDF $F(x)$. The $p^{\text{th}}$ quantile of $X$ is the value $q(p)$ such that
$$
\begin{align*}
    P(X \le q(p)) = p
\end{align*}
$$

If $p = 0.5$, then $q(0.5)$ is the median of X. We can find a given quantile by solving $F(x) = p$ for $x$.

<u>Change of Variables</u>

What if we want to find the CDF or pdf of a function of $X$? For the spinner example, the winning is inverse of the point we spin. Hence, the winning is $Y = \frac{1}{X}$, and we want to find 
$$
\begin{align*}
    F_Y(y) = P(Y \le y)
\end{align*}
$$

Specific example 
$$
\begin{align*}
    P(Y \le 2) = P(X^{-1} \le 2) = P(X \ge 0.5) = \frac{7}{8}
\end{align*}
$$

How can we generalize this approach to $P(Y \le y)$

The process

1.  Find the range of values of $Y$

2.  Write the CDF of $Y$ as a function of $X$

3.  Use $F_X(x)$ to find $F_Y(y)$

4.  Differentiate $F_Y(y)$ if we want the pdf of $Y$, $f_Y(y)$

> Spinner example:
> 
> Since $X \in [0,4]$, we know $Y \in [\frac{1}{4}, \infty]$
> 
> Write the CDF of $Y$ as a function of $X$. Let $y \in [\frac{1}{4},\infty)$. 
> $$
> \begin{align*}
>     F_Y(y) &= P(Y \le y) = P\left (\frac{1}{X} \le y\right ) \\
>     &= P\left (X \ge \frac{1}{y}\right ) \\
>     &= 1 - P\left (X < \frac{1}{y}\right) \\
>     &= 1 - F_X\left(y^{-1}\right)
> \end{align*}
> $$
> 
> Then use $F_X(x)$ to find $F_Y(y)$.
> 
> $F_Y(y) = 1 - F_X(Y^{-1})$, and we know
> $$
> \begin{align*}
>     F_X(x) = \frac{x}{4} \quad x \in [0,4]\\
>     F_X(y^{-1}) = \frac{y^{-1}}{4} = \frac{1}{4y}
> \end{align*}
> $$
> 
> Thus, 
> $$
> \begin{align*}
>     F_Y(y) = \begin{cases}
>         0 \quad y < \frac{1}{4} \\
>         1 - \frac{1}{4y} \quad y \ge \frac{1}{4}
>     \end{cases}
> \end{align*}
> $$
> 
> Differentiate $F_Y(y)$ if we want the pdf of $Y$, $f_Y(y)$. We have $F_Y(y) = 1 - \frac{1}{4y}$ for $y \ge \frac{1}{4}$, so the pdf is
> $$
> \begin{align*}
>     f_Y(y) = \dfrac{d}{dy}F_Y(y) = \frac{1}{4y^2}, \quad y \ge \frac{1}{4}
> \end{align*}
> $$

<u>Expectation, Mean, and Variance for Continuous Random
Variables</u>

If $X$ is a continuous random variable with $pdf f(x)$, and $g : \mathbb{R} \to \mathbb{R}$, then 
$$
\begin{align*}
    E(g(X)) = \int_{-\infty}^{\infty}g(x)f(x)dx
\end{align*}
$$

Thus, 
$$
\begin{align*}
    &E(X) = \int_{-\infty}^{\infty}xf(x)dx \\
    &Var(X) = E([X-E(X)]^2) = \int_{-\infty}^{\infty}(x-E(X))^2f(x)dx
\end{align*}
$$

Note that the shortcut still holds.

Example 
$$
\begin{align*}
    f(x) = \begin{cases}
        6x(1-x) \quad \text{if } 0 \le x \le 1 \\
        0 \quad \text{otherwise}
    \end{cases}
\end{align*}
$$

$$
\begin{align*}
    E(X) &= \int_{-\infty}^{\infty}xf(x)dx = 0 + \int_0^1 x \cdot 6x(1-x)dx + 0 \\
    &= 6\left [\frac{1}{3}-\frac{1}{4}\right ]_0^1 \\
    &= 0.5
\end{align*}
$$

Now solve for $Var(X)$ 
$$
\begin{align*}
    E(g(X)) &= \int_{-\infty}^{\infty}g(x)f(x)dx \\
    E(X^2) &= 0 + \int_0^1 x^26x(1-x)dx + 0 \\
    &= \int_0^1(6x^3 - 6x^4)dx \\
    &= 6\left [\frac{x^4}{4} - \frac{x^5}{5}\right ]_0^1 \\
    &= 6 \left [\frac{1}{4} - \frac{1}{5}\right ] = 0.3
\end{align*}
$$

Thus, 
$$
\begin{align*}
    Var(X) = E[X^2] - (E[x])^2 = 0.3 -0.25 = 0.05
\end{align*}
$$

## Continuous Uniform Distribution

> [!info] Definition
> 
> We say that $X$ has a continuous uniform distribution on $(a,b)$ if $X$ takes values in $(a,b)$ (or $[a,b]$) where all subintervals of a fixed length have the same probability.
> 
> $X$ has pdf 
> $$
> \begin{align*}
>     f(x) = \begin{cases}
>         \frac{1}{b-1} \quad x \in (a,b) \\
>         0 \quad \text{otherwise}
>     \end{cases}
> \end{align*}
> $$
> 
> then the CDF is 
> $$
> \begin{align*}
>     F(x) = \begin{cases}
>         0 &x < a \\
>         \int_a^x \frac{1}{b-a}du = \frac{x-a}{b-a} &a \le x \le b \\
>         1 & x > b
>     \end{cases}
> \end{align*}
> $$

<u>Continuous Uniform: Mean and Variance</u> 

$$
\begin{align*}
    E(X) = \frac{(a + b)}{2}
\end{align*}
$$
$$
\begin{align*}
    E(X^2) &= \int_{-\infty}^{\infty}x^2f(x)dx = \int_a^b x^2 \frac{1}{b-a}dx = \frac{1}{(b-a)}\left (\frac{x^3}{3}\vert_a^b \right ) = \frac{b^3-a^3}{3(b-a)} \\
    &= \frac{(b-a)(b^2+ab+a^2)}{3(b-a)} = \frac{b^2+ab+a^2}{3}
\end{align*}
$$

$$
\begin{align*}
    Var(X) &= E(X^2) - [E(X)]^2 \\
    &= \frac{b^2 + ab + a^2}{3} - \left (\frac{b+a}{2}\right )^2 \\
    &= \frac{4b+4ab+4a^2-3b^2-6ab-3a^2}{12} \\
    &= \frac{b^2-2ab + a^2}{12} \\
    &= \frac{(b-a)^2}{12}
\end{align*}
$$

## Exponential Distribution

Consider cars arriving following a Poisson process. The number of cars arriving in $t$ minutes follows $Poi(\lambda t)$

Let $X =$ the time you wait before you see the first car, in minutes. This is a crv.

CDF 
$$
\begin{align*}
    F(x) &= P(X \le x) \\
    &= P(\text{time to 1st event } > x) \\
    &= 1 - P(\text{no event occurs in } (0,x)) \\
    &= 1 - P(Y_x = 0)
\end{align*}
$$

where $Y_x \sim Poi(\lambda x)$ is the number of events in $(0,x)$.

Thus, 
$$
\begin{align*}
    F(x) &= 1 - \frac{e^{-\lambda x}(\lambda x)^0}{0!} = 1 - e^{-\lambda x}
\end{align*}
$$

Taking the derivative gives the pdf: 
$$
\begin{align*}
    f(x) = \begin{cases}
        \lambda e^{-\lambda x} \quad x > 0 \\
        0 \quad x \le 0
    \end{cases}
\end{align*}
$$

<u>Exponential Distribution</u>

Let $\theta = \frac{1}{\lambda}$ provide an alternate parameterization of the exponential distribution.

> [!info] Definition
> 
> We say that $X$ has an exponential distribution with parameter $\theta$ $(X \sim exp(\theta))$ if the density of $X$ is 
> $$
> \begin{align*}
>     f(x) = \begin{cases}
>         \frac{1}{\theta}e^{-x/\theta} \quad x > 0 \\
>         0 \quad x \ge 0
>     \end{cases}
> \end{align*}
> $$

The CDF becomes $F(x) = 1 - e^{x/\theta}$ for $x \ge 0$.

In general, for any Poisson process with rate $\lambda$, the time between events will follow an exponential distribution $exp(\theta = 1/\lambda)$

Now we want to compute $E[X]$ and $Var(X)$. We will need to solve

$$
\begin{align*}
    E[X] = \int_{-\infty}^{\infty}xf(x)dx = \int_0^{\infty}x \frac{1}{\theta}e^{-x/\theta}dx
\end{align*}
$$
and

$$
\begin{align*}
    E[X^2] = \int_0^{\infty}x^2\frac{1}{\theta}e^{-x/\theta}dx
\end{align*}
$$


We can use the Gamma function.

> [!info] Definition
> 
> The Gamma function, $\Gamma(\alpha)$ is defined for all $\alpha > 0$ as
> $$
> \begin{align*}
>     \Gamma(\alpha) = \int_0^{\infty}y^{\alpha - 1} e^{-y}dy
> \end{align*}
> $$

Note

-   $\Gamma(\alpha) = (\alpha -1)\Gamma(\alpha -1)$

-   If $a \in \mathbb{Z}^+$, then $\Gamma(\alpha) = (\alpha - 1)!$

The Gamma function tells us that if $\alpha$ is a positive integer, then
$$
\begin{align*}
    \int_0^{\infty}y^{\alpha -1}e^{-y}dy = (\alpha -1)!
\end{align*}
$$

If we write $y = \frac{x}{\theta}$, then $dx = \theta dy$ and
$$
\begin{align*}
    E[X] &= \int_0^{\infty}x\frac{1}{\theta}e^{-x/\theta}dx \\
    &= \int_0^{\infty}ye^{-y}\theta dy \\
    &= \theta \int_0^{\infty}y^1e^{-y}dy
\end{align*}
$$

Because 

$$
\begin{align*}
    \Gamma(\alpha) = \int_0^{\infty}y^{\alpha-1}e^{-y}dy = (\alpha -1)!
\end{align*}
$$
$$
\begin{align*}
    E[X] &= \theta \int_0^{\infty}y^1e^{-y}dy \\
    &= \theta \Gamma(2) \\
    &= \theta (1!) = \theta
\end{align*}
$$

We can use the same trick with Variance to see that $Var(X) = \theta^2$

<u>Memoryless Property</u> 
$$
\begin{align*}
    P(X > t + x | X > t) &= P(X > x)\\
    P(a \le X - t \le b | X > t) &= P(a \le X \le b)
\end{align*}
$$

## Computer Generated Random Numbers

Transform simulated observations from $U \sim \mathcal{U}(0,1)$ to obtain observations from $X$ with CDF $F$. Find a function $h$ such that $X = h(U)$. 
$$
\begin{align*}
    F(x) &= P(X \le x) \\
    &= P(h(U) \le x) \\
    &= P(U \le h^{-1}(x)) \quad \text{assuming } h \text{ is strictly increasing} \\
    &= h^{-1}(x) \quad \text{given the CDF of } \mathcal{U} \sim \mathcal{U}(0,1)
\end{align*}
$$

Assuming $F$ is continuous and strictly increasing, our result $F(\cdot) = h^{-1}(\cdot)$ implies
$$
\begin{align*}
    h = F^{-1}
\end{align*}
$$

> <u>Example</u>
> 
> Consider the CDF of the $geo(p)$ distribution 
> $$
> \begin{align*}
>     F(x) = \begin{cases}
>         1-(1-p)^{[x]+1} \quad x \ge 0 \\
>         0 \quad x < 0
>     \end{cases}
> \end{align*}
> $$
> 
> Find a transformation $h$ so that if $U \sim \mathcal{U}(0,1), X = h(u)$ has CDF $F$.
> 
> CDF is not continuous nor strictly increasing so we have to use the generalized inverse $F^{-1}(u) = inf\{x; F(x) \ge u\}$. For a given $0 \le u \le 1$: 
> $$
> \begin{align*}
>     F(x) &\ge u \\
>     1 - (1-p)^{[x]+1} &\ge u \\
>     (1-p)^{[x]+1} &\le 1 - u \\
>     ([x]+1)\log(1-p) &\le \log(1-u) \\
>     [x] & \ge \frac{\log(1-u)}{\log(1-p)} -1 
> \end{align*}
> $$
> 
> The smallest $x$ that satisfies the equation above is 
> $$
> \begin{align*}
>     x = \left \lceil \frac{\log(1-u)}{\log(1-p)}-1 \right \rceil
> \end{align*}
> $$
> 
> Thus $h(u) = inf\{x;F(x) \ge u\} = \left \lceil \frac{\log(1-u)}{\log(1-p)}-1 \right \rceil$

## Normal Distribution

Characteristics: Symmetric about a mean value, more concentrated around the mean than the tails (and unimodal).

> [!info] Definition
> 
> $X$ is said to have a normal distribution (or Gaussian distribution) with mean $\mu$ and variance $\sigma^2$ if the density of $X$ is
> 
> $$
> \begin{align*}
>     f(x) = \frac{1}{\sqrt{2\pi \sigma^2}}e^{\frac{-(x-\mu)^2}{2\sigma^2}}, \quad x \in \mathbb{R}
> \end{align*}
> $$
> or $X \sim \mathcal{N}(\mu, \sigma^2)$, or $X \sim G(\mu, \sigma)$.

Properties:

1.  Symmetric about its mean: If $X \sim \mathcal{N}(\mu, \sigma^2)$, then $P(X \le \mu - t) = P(X \ge \mu + t)$

2.  Density of unimodal: Peak is at $\mu$. The mode, median, and mean are the same $\mu$.

3.  Mean and Variance are the parameters: $E(X) = \mu$, and $Var(X) = \sigma^2$

A classic problem, if $X \sim \mathcal{N}(\mu, \sigma^2)$, then what is the value of

$$
\begin{align*}
    P(a \le X \le b) = \int_a^b \frac{1}{\sqrt{2\pi \sigma^2}}e^{\frac{-(x-\mu)^2}{2\sigma^2}}dx = ???
\end{align*}
$$


This integral is weird.

> [!info] Definition
> 
> We say that $X$ is a standard normal random variable if $X \sim \mathcal{N}(0,1)$. The probability density function is:
> 
> $$
> \begin{align*}
>     \varphi(x) = \frac{1}{\sqrt{2\pi}}e^{\frac{-x^2}{2}}
> \end{align*}
> $$
> 
> 
> The CDF is 
> 
> $$
> \begin{align*}
>     \phi(x) = \int_{-\infty}^x \frac{1}{\sqrt{2\pi}}e^{\frac{-y^2}{2}}dy
> \end{align*}
> $$


Standard Normal Tables (Z-Tables). Values of the function $\phi(x)$ are tabulated in Standard Normal Tables.

We use symmetry:

$$
\begin{align*}
    &P(|Z|\le c) = 0.2 \\
    \implies &P(Z \le -c) + P(Z \ge c) = 0.8 \\
    \implies &P(Z \ge c) = 0.4 \\
    \implies &P(Z \le c) = 0.6
\end{align*}
$$


<u>Standardization</u>

> [!tldr] Theorem
> 
> If $X \sim \mathcal{N}(\mu,\sigma^2)$, then defining 
> 
> $$
> \begin{align*}
>     Z = \frac{X - \mu}{\sigma}
> \end{align*}
> $$
> we have $Z \sim \mathcal{N}(0,1)$.

An important consequence of $X \sim \mathcal{N}(\mu, \sigma^2)$:

$$
\begin{align*}
    P(X \le x) = P\left ( \frac{X - \mu}{\sigma} \le \frac{x - \mu}{\sigma}\right ) = P\left (Z \le \frac{x - \mu}{\sigma}\right )
\end{align*}
$$
where $Z \sim \mathcal{N}(0,1)$

The process to find $P(Z \le x)$ when $X \sim \mathcal{N}(\mu, \sigma^2)$:

1.  Compute $\frac{x-\mu}{\sigma}$

2.  Use standard normal tables to find $P\left (Z \le \frac{x-\mu}{\sigma}\right)$

3.  This equals $P(X \le x)$

$$
\begin{align*}
    P(X > x) &= P\left(Z > \frac{x - \mu}{\sigma}\right) \\
    P( a < X < b) &= P\left( \frac{a-\mu}{\sigma} < Z < \frac{b - \mu}{\sigma}\right)
\end{align*}
$$
where $Z \sim \mathcal{N}(0,1)$.

Let $X \sim \mathcal{N}(\mu,\sigma)$. Find $a$ such that $P(X \le a) = 0.6$; this is the $60$th percentile of $Z$.

$$
\begin{align*}
    P\left(\frac{X -\mu}{\sigma} \le \frac{a - \mu}{\sigma}\right) = 0.6 \implies \frac{a - \mu}{\sigma} = \Phi^{-1}(0.6)
\end{align*}
$$
So $a = \sigma \Phi^{-1}(0.6) + \mu$

# Multivariate Distributions

## Basic Terminology and Techniques

So far we've only considered univariate distributions.

Suppose that $X$ and $Y$ are discrete random variables defined on the sample space. The joint probability function of $X$ and $Y$ is

$$
\begin{align*}
    f(x,y) = P(\{X = x\} \cap \{Y = y\}) x \in X(S), y \in Y(S)
\end{align*}
$$
a shorthand is, 

$$
\begin{align*}
    f(x,y) = P(X = x, Y =y)
\end{align*}
$$


For a collection of $n$ discrete random variables, $X_1, \ldots, X_n$, the joint probability function is defined as 

$$
\begin{align*}
    f(x_1, x_2, \ldots, x_n) = P(X_1 = x_1, X_2 = x_2, \ldots, X_n = x_n)
\end{align*}
$$


For example if we rolled three dice, and let $X_i$ denote the result on the $i^{\text{th}}$ die, we'd have $f(x_1, x_2, x_3) = \frac{1}{216}$

Properties:

1.  $0 \le f(x,y) \le 1$

2.  $\sum_{x,y}f(x,y) = 1$

Computing probability from the joint probability function:

Let $A$ be a subset of $(x,y)$ values that $(X,Y)$ could take. Then

$$
\begin{align*}
    P((X,Y) \in A) = \sum_{(x,y) \in A} f(x,y)
\end{align*}
$$


> [!info] Definition
> 
> Suppose that $X$ and $Y$ are discrete random variables with joint probability function $f(x,y)$. The marginal probability function of $X$ is 
> 
> $$
> \begin{align*}
>     f_X(x) = P(X = x) = \sum_{y \in Y(S)}f(x,y), \quad x \in X(S)
> \end{align*}
> $$
> Similarly, the marginal distribution of $Y$ is
> 
> $$
> \begin{align*}
>     f_Y(y) = P(Y = y) = \sum_{x \in X(S)} f(x,y), \quad y \in Y(S)
> \end{align*}
> $$


> [!info] Definition
> 
> Suppose that $X$ and $Y$ are discrete random variables with joint probability function $f(x,y)$ and marginal probability functions $f_X(x)$ and $f_Y(y)$. $X$ and $Y$ are said to be independent random variables if and only if 
> 
> $$
> \begin{align*}
>     f(x,y) = f_X(x)f_Y(y), \quad  \forall x \in X(S), y \in Y(S)
> \end{align*}
> $$
> This is the same as saying 
> 
> $$
> \begin{align*}
>     P(X=x, Y=y) = P(X=x)P(Y=y), \quad \forall x,y
> \end{align*}
> $$


Rolling two 6-sided dice with $X =$ the outcome on the first die and $Y =$ the outcome on the second die: 

$$
\begin{align*}
    f(x,y) = \frac{1}{36}, \quad x,y \in \{1,2,3,4,5,6\}
\end{align*}
$$
but we also know

$$
\begin{align*}
    f_X(x) = \frac{1}{6}, f_Y(y) = \frac{1}{6} \quad x,y \in \{1,2,3,4,5,6\}
\end{align*}
$$
and so $f(x,y) = \frac{1}{36} = \frac{1}{6} \times \frac{1}{6} = f_X(x)f_Y(y)$ and we have independence.

This abstracts to size $n$.

<u>Definition</u>

The conditional probability function of $X$ given $Y = y$ is denoted $f_{X \vert Y}(x \vert y)$, and is defined to be 
$$
\begin{align*}
    f_{X \vert Y}(x \vert y) = P( X = x \vert Y = y) = \frac{P(X = x, Y=y)}{P(Y=y)} = \frac{f(x,y)}{f_Y(y)}
\end{align*}
$$

What about functions of random variables?

Suppose that 
$$
\begin{align*}
    h : \mathbb{R}^2 \to \mathbb{R}
\end{align*}
$$

For jointly distributed random variables $X$ and $Y$, $\mathcal{U} = h(X,Y)$ is a random variable. If $X$ and $Y$ have joint p.f. $f(x,y)$, then the probability function of $\mathcal{U}$ is given by: 
$$
\begin{align*}
    f_{\mathcal{U}} = P(\mathcal{U} = t) = \sum_{(x,y):h(x,y) = t}f(x,y)
\end{align*}
$$

-   If $X \sim Binomial(n,p)$ and $Y \sim Binomial(m,p)$ independently, then $X + Y \sim Binomial(n+m,p)$

-   If $X \sim Poi(\mu_1)$ and $Y \sim Poi(\mu_2)$ independently, then $X + Y \sim Poi(\mu_1 + \mu_2)$

## Multinomial Distribution

> [!info] Definition
> 
> Multinomial Distribution: Consider an experiment in which:
> 
> 1.  Individual trials have $k$ possible outcomes, and the probabilities of each individual outcome are denoted $p_i, i = 1, \ldots, k$, so that $p_1 + p_2 + \cdots + p_k = 1$
> 
> 2.  Trials are independently repeated $n$ times, with $X_i$ denoting the number of times outcome $i$ occurred, so that $X_1 + X_2 + \cdots X_k = n$
> 
> If $X_1, \ldots, X_k$ have multinomial distribution with parameters $n$ and $p_1, \ldots, p_k$, then their joint probability function is
> 
> $$
> \begin{align*}
>     f(x_1, \ldots x_k) = \frac{n!}{x_1!x_2!\cdots x_k!}p_1^{x_1}\cdots p_k^{x_k},
> \end{align*}
> $$
> where $x_1, \ldots, x_k$ satisfy $x_1 + \cdots + x_k = n, x_i \ge 0$.

The terms 

$$
\begin{align*}
    \frac{n!}{x_1!x_2!\cdots x_k!}, \quad \text{for } x_1 + \cdots + x_k = n
\end{align*}
$$
are called multinomial coefficients.

If $X_1, \ldots, X_k$ have joint Multinomial distribution with parameters $n$ and $p_1, \ldots, p_k$, then 

$$
\begin{align*}
    X_i \sim Bin(n,p_i)
\end{align*}
$$
Also 

$$
\begin{align*}
    \sum X_i \sim Bin\left ( n, \sum p_i \right )
\end{align*}
$$


## Expectation for Multivariate Distributions: Covariance and Correlation

Recall, 

$$
\begin{align*}
    E[X] = \sum xf(x) \quad E[X] = \int xf(x)dx
\end{align*}
$$


> [!info] Definition
> 
> Suppose $X$ and $Y$ are jointly distributed random variables with joint probability function $f(x,y)$. Then for a function $g: \mathbb{R}^2 \to \mathbb{R}$, 
> 
> $$
> \begin{align*}
>     E(g(X,Y)) = \sum_{(x,y)}g(x,y)f(x,y)
> \end{align*}
> $$


More generally, if $g: \mathbb{R}^n \to \mathbb{R}$, and $X_1, \ldots, X_n$ have joint p.f. $f(x_1, \ldots, x_n)$, then

$$
\begin{align*}
    E(g(X_1, \ldots, X_n)) = \sum_{(x_1, \ldots, x_n)} g(x_1, \ldots, x_n)f(x_1, \ldots, x_n)
\end{align*}
$$


Linear Properties of Expectation

$$
\begin{align*}
    E(X + Y) = \sum_{x}xf_X(x) + \sum_{y}yf_Y(y) = E(X) + E(Y)
\end{align*}
$$
and in general, 

$$
\begin{align*}
    E[a \cdot g_1(X,Y) + b \cdot g_2(X,Y)] = a \cdot E(g_1(X,Y)) + b \cdot E(g_2(X,Y))
\end{align*}
$$


Independence gives a useful - but simplistic - way of describing relationships between variables.

> [!info] Definition
> 
> If $X$ and $Y$ are jointly distributed, then $Cov(X,Y)$ denotes the covariance between $X$ and $Y$. It is defined by 
> 
> $$
> \begin{align*}
>     Cov(X,Y) = E[(X-E(X))(Y-E(Y))]
> \end{align*}
> $$
> or the shortcut, 
> 
> $$
> \begin{align*}
>     Cov(X,Y) = E(XY) - E(X)E(Y)
> \end{align*}
> $$


Properties of Covariance

-   Positive $Cov(X,Y) \implies Y$ increases as $X$ increases

-   Negative $Cov(X,Y) \implies Y$ decreases as $X$ increases

-   The larger the absolute value of $Cov(X,Y)$, the stronger the relationship is

-   $Cov(X,X) = Var(X). \quad Cov(X,X) = E[XX] - E[X]E[X] = E[X^2] - E[X]^2$

-   $Cov(X,c) = 0$ for any constant $c$.

-   $Cov(Y,X) = Cov(X,Y) = E[(Y - \mu_Y)(X - \mu_X)]$

> [!tldr] Theorem
> 
> If $X$ and $Y$ are independent, then $Cov(X,Y) = 0$.

Proof

$$
\begin{align*}
    Cov(X,Y) &= E[(X - \mu_X)(Y - \mu_Y)] = \sum_{\text{all }y}\left [ \sum_{\text{all }x}(x - \mu_X)(y-\mu_Y)f_1(x)f_2(y) \right ] \\
    &= \sum_{\text{all }y}\left [ (y - \mu_Y)f_2(y) \sum_{\text{all }x}(x-\mu_X)f_1(x) \right ]\\
    &= \sum_{\text{all }y}\left [ (y- \mu_Y) f_2(y) E(X - \mu_X) \right ] \\
    &= \sum_{\text{all }y}0 = 0 \quad \blacksquare
\end{align*}
$$


$X$ and $Y$ are independent $\implies$ $Cov(X,Y) = 0$.

It is important to know that the converse is false. If $Cov(X,Y) = 0$ then $X$ and $Y$ are not necessarily independent.

$Cov(X,Y) = 0 \iff E[XY] = E[X]E[Y]$

$X$ and $Y$ are uncorrelated if $Cov(X,Y) = 0$, but that does not mean they are independent.

Independence $\implies Cov(X,Y) = 0 \implies E[XY] = E[X]E[Y]$
Independence $\implies E[g_1(X)g_2(Y)] = E[g_1(X)]E[g_2(Y)]$

> [!info] Definition
> 
> The correlation of $X$ and $Y$ is denoted $corr(X,Y)$, and is defined by
> 
> $$
> \begin{align*}
>     \rho = \frac{Cov(X,Y)}{SD(X)SD(Y)}
> \end{align*}
> $$
> with $-1 \le \rho \le 1$.

Correlation measures the strength of the linear relationship between $X$ and $Y$.

Properties:

-   If $p \approx +1$, then $X$ and $Y$ will have an approximately positive linear relationship

-   If $p \approx -1$, then $X$ and $Y$ will have an approximately negative linear relationship

-   If $p \approx 0$, then $X$ and $Y$ are said to be uncorrelated.

We say that $X$ and $Y$ are uncorrelated if $Cov(X,Y) = 0$ (or $corr(X,Y) = 0$).

$X$ and $Y$ are independent $\implies$ $X$ and $Y$ are uncorrelated.

Once again, the converse is not true.

## Mean and Variance of a Linear Combination of Random Variables

Suppose $X_1, \ldots, X_n$ are jointly distributed random variables with joint probability function $f(x_1, \ldots, x_n)$. A linear combination of the random variables $X_1, \ldots, X_n$ is a random variable of the form 

$$
\begin{align*}
    \sum_{i=0}^n a_i X_i
\end{align*}
$$
where $a_1, \ldots, a_n \in \mathbb{R}$

> <u>Examples</u> 
> 
> $$
> \begin{align*}
>     S_n &= \sum_{i=1}^nX_i \quad a_i = 1, \quad 1 \le i \le n \\
>     \bar{X} &= \sum_{i=1}^n \frac{1}{n}X_i \quad a_i = \frac{1}{n}, \quad 1 \le i \le n
> \end{align*}
> $$


Expected Value of a Linear Combination: 

$$
\begin{align*}
    E\left(\sum_{i=1}^n a_iX_i \right ) = \sum_{i=1}^n a_i E(X_i)
\end{align*}
$$


Mean of sample mean: 

$$
\begin{align*}
    E[\bar{X}] = \sum_{i=1}^n \frac{1}{n}E[X_i] = \frac{1}{n}n \mu = \mu
\end{align*}
$$


Covariance of linear combinations:

Two useful results: 

$$
\begin{align*}
    Cov(aX + bY, cU + dV) &= acCov(X,U) + adCov(X,V) + bcCov(Y,U) + bdCov(Y,V) \\
    Cov\left (\sum_{i=1}^n a_i X_i, \sum_{j=1}^m b_j Y_j \right ) &= \sum_{i=1}^n \sum_{j=1}^m a_ib_j Cov(X_i, Y_j)
\end{align*}
$$


Variance of linear combination

When $Cov(X,Y) = 0$

$Var(X + Y) = Var(X) + Var(Y)$

$Var(X - Y) = Var(X) + Var(Y)$

When $Cov(X,Y) > 0$

$Var(X + Y) > Var(X) + Var(Y)$

$Var(X - Y) < Var(X) + Var(Y)$

In the case of two random variables $X$ and $Y$, and constants $a$ and $b$, we have:

$$
\begin{align*}
    Var(aX + bY) = a^2Var(X) + b^2Var(Y) + 2abCov(X,Y)
\end{align*}
$$
If $a = b = 1$

$$
\begin{align*}
    Var(X + Y) = Var(X) + Var(Y) + 2Cov(X,Y) 
\end{align*}
$$
If $a = 1, b = -1$ 

$$
\begin{align*}
    Var(X-Y) = Var(X) + Var(Y) - 2Cov(X,Y)
\end{align*}
$$


In general, let $X_1, X_2, \ldots, X_n$ be random variables, and write $Var(X_i) =  \sigma_i^2$, then: 

$$
\begin{align*}
    Var\left(\sum_{i=1}^na_iX_i\right) &= \sum_{i=1}^n \sum_{j=1}^n a_ia_jCov(X_i, X_j) \\
    &= \sum_{i=1}^n a_i^2 \sigma_i^2 + 2 \sum_{i=1}^n \sum_{j=i+1}^n a_ia_jCov(X_i,X_j)
\end{align*}
$$


If $X_1, X_2, \ldots, X_n$ are independent, then $Cov(X_i, X_j) = 0$ (for $i \ne j$) and so 

$$
\begin{align*}
    Var \left ( \sum_{i=1}^na_iX_i \right ) = \sum_{i=1}^n a_i^2 Var(X_i) = \sum_{i=1}^n a_i^2 \sigma_i^2
\end{align*}
$$


Variance of sample mean

In general, we have for $X_1, X_2, \ldots, X_n$ independent random variables all with variance $\sigma^2$ 

$$
\begin{align*}
    Var(\bar{X}) = \frac{\sigma^2}{n}
\end{align*}
$$
this holds for any set of independent random variables that have the same variance.

## Linear Combinations of Independent Normal Random Variables

Linear transformation of a normal random variable:

Let $X \sim \mathcal{N}(\mu, \sigma^2)$ and $Y = aX + b$ where $a$ and $b$ are constants, then 
$$
\begin{align*}
    Y \sim \mathcal{N}(a\mu + b, a^2\sigma^2)
\end{align*}
$$

The linear transformation of a normal random variable is still normal.

Linear combination of $2$ independent normal random variables:

Let $X \sim \mathcal{N}(\mu_1, \sigma_1^2)$ and $Y \sim \mathcal{N}(\mu_2, \sigma_2^2)$ independently, and let $a$ and $b$ be constants, then 
$$
\begin{align*}
    aX + bY \sim \mathcal{N}(a \mu_1 + b\mu_2, a^2\sigma_1^2 + b^2\sigma_2^2)
\end{align*}
$$

Linear combination of independent normal random variables is still normal.

Let $X_1, X_2, \ldots, X_n$ be independent $\mathcal{N}(\mu, \sigma^2)$ random variables. Then 

$$
\begin{align*}
    S_n \equiv \sum_{i=1}^n X_i \sim \mathcal{N}(n \mu, n \sigma^2)
\end{align*}
$$
and

$$
\begin{align*}
    \bar{X} \sim \mathcal{N}(\mu, \sigma^2 / n)
\end{align*}
$$


> The IQs of UWaterloo Math students are normally distributed with mean $120$ and variance $100$. The probability that the average IQ in a class of $25$ students is between $118$ and $123$ is: 
> 
> $$
> \begin{align*}
>     &X_i \sim \mathcal{N}(120,100) \implies \bar{X} \sim \mathcal{N}(120,100/25) \\
>     \implies P(118 \le \bar{X} \le 123) &= P\left ( \frac{118-120}{2} \le \frac{\bar{X} - 120}{2} \le \frac{123-120}{2} \right ) = P(-1 \le Z \le 1.5)
> \end{align*}
> $$


## Indicator Random Variables

If $X \sim Binomial(n,p)$ we can think of $X$ in the following way:

Observe the first trial, and see if it succeeds. We set $X_1$ to be $1$ if it succeeds and $0$ if it fails.

Observe the second trial, and see if it succeeds. We set $X_2$ to be $1$ if it succeeds and $0$ if it fails.

Observe the $n^{\text{th}}$ trial, and see if it succeeds. We set $X_n$ to be $1$ if it succeeds and $0$ if it fails.

Sum the successful events to find $X$ 

$$
\begin{align*}
    X = \sum_{i=1}^n I_i
\end{align*}
$$


$X$ is a linear combination of random variables.

> [!info] Definition
> 
> Let $A$ be an event which may possibly result from an experiment. We say that $\mathbf{1}_A$ is the indicator random variable of the event $A$. $\mathbf{1}_A$ is defined by: 
> 
> $$
> \begin{align*}
>     \mathbf{1}_A = \begin{cases}
>         1 \quad \text{if } A \text{ occurs} \\
>         0 \quad \text{otherwise}
>     \end{cases}
> \end{align*}
> $$


Covariance of Indicator Random Variables:

Suppose we have two events, $A$ and $B$, and we define 

$$
\begin{align*}
    \mathbf{1}_A = 1 \text{ if } A \text{ occurs, and } \mathbf{1}_A = 0 \text{ otherwise} \\
    \mathbf{1}_B = 1 \text{ if } B \text{ occurs, and } \mathbf{1}_B = 0 \text{ otherwise}
\end{align*}
$$


How do we find $Cov(\mathbf{1}_A, \mathbf{1}_B)$

For general, $X, Y$ 

$$
\begin{align*}
    Cov(X,Y) = E[XY] - E[X]E[Y]
\end{align*}
$$
so for indicator variables we have 

$$
\begin{align*}
    Cov(\mathbf{1}_A, \mathbf{1}_B) = E[\mathbf{1}_A \times \mathbf{1}_B] - E[\mathbf{1}_A]E[\mathbf{1}_B]
\end{align*}
$$
We know that $E[\mathbf{1}_A] = P(A)$ and $E[\mathbf{1}_B] = P(B)$, so we just have to find 

$$
\begin{align*}
    &E[\mathbf{1}_A \times \mathbf{1}_B] \\
    &= 1 \times P(A \cap B) + 0 \times (1 - P(A \cap B))\\
    &= P(A \cap B) 
\end{align*}
$$


If $A$ and $B$ are events, then 
$$
\begin{align*}
    Cov(\mathbf{1}_A, \mathbf{1}_B) = P(A \cap B) - P(A)P(B)
\end{align*}
$$

$\mathbf{1}_A$ and $\mathbf{1}_B$ are independent $\iff \mathbf{1}_A$ and $\mathbf{1}_B$ are uncorrelated.

# Central Limit Theorem and Moment Generating Functions

## Central Limit Theorem

If $X_1, X_2, \ldots, X_n$ are independent random variables from the same distribution, with mean $\mu$ and variance $\sigma^2$, then as $n \to \infty$, the shape of the probability histogram for the random variable $S_n = \sum_{i=1}^n X_i$ approaches the shape of a $\mathcal{N}(n\mu,n\sigma^2)$ probability density function.

The cumulative distribution function of the random variable

$$
\begin{align*}
    \frac{\sum_{i=1}^n X_i - n\mu}{\sigma \sqrt{n}} = \frac{S_n - n \mu}{\sigma \sqrt{n}}
\end{align*}
$$
approaches the $\mathcal{N}(0,1)$ cumulative distribution function. Similarly, the cumulative distribution function of 

$$
\begin{align*}
    \frac{\bar{X} - \mu}{\sigma / \sqrt{n}}
\end{align*}
$$
approaches the $\mathcal{N}(0,1)$ cumulative distribution function.

In other words, if $n$ is large: 

$$
\begin{align*}
    S_n = \sum_{i=1}^n X_i
\end{align*}
$$
has approximately a $\mathcal{N}(n\mu,n\sigma^2)$ distribution, and 

$$
\begin{align*}
    \bar{X} = \frac{1}{n} \sum_{i=1}^n X_i
\end{align*}
$$
has approximately a $\mathcal{N}(\mu, \sigma^2 / n)$ distribution.

> <u>Example</u>
> 
> Roll a $6$-sided die $1000$ times and record each result. If the die is a fair die, estimate the probability that the sum of the die rolls is less than $3400$.
> 
> Let $X_i$ be the dot for the $i-$th roll. We want the probability $P(\sum_{i=1}^{1000}X_i < 3400)$. Without CLT this is very difficult. 
> 
> Using CLT:
> 
> Seems reasonable to assume independence, each $X_i$ is a discrete $\mathcal{U}(1,6)$ random variable, and $n = 1000$ is large.
> 
> Mean and variance 
> 
> $$
> \begin{align*}
>     \mu = \frac{a + b}{2} = 3.5 &\quad \sigma^2 = \frac{(b-a+1)^2 - 1}{12} = \frac{35}{12} \\
>     E[S_n] = n \mu = 3.5n &\quad Var(S_n) = n \sigma^2 = \frac{35}{12}n
> \end{align*}
> $$
> Apply CLT (Standardization) 
> 
> $$
> \begin{align*}
>     \frac{S_n- 3.5n}{\sqrt{\frac{35}{12} n}} \to \mathcal{N}(0,1)
> \end{align*}
> $$
> Use the Z-table 
> 
> $$
> \begin{align*}
>     P(S_n < 3400) &= P\left ( \frac{S_n - 3.5n}{\sqrt{\frac{35}{12}n}} < \frac{3400-3.5n}{\sqrt{\frac{35}{12}n}}\right) \\
>     &\approx P(Z < -1.852) = 0.032
> \end{align*}
> $$


Note:

-   CLT doesn't hold if $\mu$ and/or $\sigma^2$ don't exist

-   Accuracy depends on the size of $n$ and the actual distribution of the $X_i$

-   CLT works for any distribution of $X_i$

Normal approximation to binomial

Note that $S_n = \sum_{i=1}^n X_i \sim Binomial(n,p)$ if all $X_i \sim Binomial(1,p)$ are independent.

Then if $S_n \sim Binomial(n,p)$ then for large $n$, the random variable

$$
\begin{align*}
    Z = \frac{S_n - np}{\sqrt{np(1-p)}}
\end{align*}
$$
has approximately a $\mathcal{N}(0,1)$.

Continuity Correction

We need to be careful with CLT when working with discrete random variables. For example we've computed $P(15 \le S_n \le 20)$. But we know that $X$ can't take non-integer values. Therefore, $P(14.5 \le S_n \le 20.5)$ gives us a better estimate. This is called continuity correction.

We should apply this when approximating discrete distributions using the CLT, and not continuous distributions.

-   $P(a \le X \le b) \to P(a - 0.5 \le X \le b + 0.5)$

-   $P(X \le b) \to P(X \le b + 0.5)$

-   $P(X < b) \to P(X < b - 0.5)$

-   $P(X \ge a) \to P(X \ge a - 0.5)$

-   $P(X > a) \to P(X > a + 0.5)$

-   $P(X = x) \to P(x - 0.5 \le X \le x + 0.5)$

If $X \sim Poisson(\mu)$, then the cumulative distribution function of

$$
\begin{align*}
    Z = \frac{X - \mu}{\sqrt{\mu}}
\end{align*}
$$
approaches that of a $\mathcal{N}(0,1)$ random variable as $\mu \to \infty$

## Moment Generating Functions

This is the third type of function that uniquely determines a distribution.

> [!info] Definition
> 
> The moment generating function (MGF) of a random variable $X$ is given by 
> 
> $$
> \begin{align*}
>     M_X(t) = E(e^{tX}), \quad t \in \mathbb{R}
> \end{align*}
> $$

If $X$ is discrete with probability function $f(x)$, then 

$$
\begin{align*}
    M_X(t) = \sum_xe^{tx}f(x), \quad t \in \mathbb{R}
\end{align*}
$$
If $X$ is continuous with density $f(x)$

$$
\begin{align*}
    M_X(t) = \int_{-\infty}^{\infty}e^{tx}f(x)dx, \quad t \in \mathbb{R}
\end{align*}
$$


Properties: 

$$
\begin{align*}
    M_X(t) = 1 + tE(X) + \frac{t^2E(X^2)}{2!} + \frac{t^3E(X^3)}{3!} + \ldots
\end{align*}
$$
So long as $M_X(t)$ is defined in a neighbourhood of $t = 0$ 

$$
\begin{align*}
    \dfrac{d}{dt^k}M_X(0) = E(X^k)
\end{align*}
$$


Suppose $X$ has a $Binomial(n,p)$ distribution. Then its moment generating function is 

$$
\begin{align*}
    M(t) &= \sum_{x=0}^n e^{tx}\binom{n}{x}p^x(1-p)^{n-x}\\
    &= \sum_{x=0}^{n}\binom{n}{x}(pe^t)^x(1-p)^{n-x} \\
    &= (pe^t + 1 - p)^n
\end{align*}
$$
Therefore, 

$$
\begin{align*}
    M'(t) &= npe^t(pe^t + 1 - p)^{n-1} \\
    M''(t) &= npe^t(pe^t + 1 - p)^{n-1} + n(n-1)p^2e^{2t}(pe^t + 1 - p)^{n-2}
\end{align*}
$$
so 

$$
\begin{align*}
    E(X) &= M'(0) = np \\
    E(X^2) &= M''(0) = np + n(n-1)p^2 \\
    Var(X) &= E(X^2) - E(X)^2 = np(1-p)
\end{align*}
$$


What is the Moment Generating Function for $\mathbf{I}_A$?

The distribution of $\mathbf{I}_A$ is 

$$
\begin{align*}
    P(\mathbf{I}_A = 1) &= P(A), \quad P(\mathbf{I}_A = 0) = 1 - P(A) \\
    M_{\mathbf{I}_A}(t) &= E[e^{t\mathbf{I}_A}] \\
    &= e^{t \times 0}P(\mathbf{I}_A = 0) + e^{t \times 1}P(\mathbf{I}_A = 1) \\
    &= 1 - P(A) + e^tP(A)
\end{align*}
$$


What is the Moment Generating Function for $X \sim \mathcal{U}(a,b)$?

When $t =0$, we have $M_X(t) = E[e^{tX}] = E[e^{0\times X}] = E[1] = 1$

When $t \ne 0$ 

$$
\begin{align*}
    M_X(t) &= E[e^{tX}] \\
    &= \int_a^b e^{tx}f(x)dx \\
    &= \int_a^b e^{tx}\frac{1}{b-a}dx \\
    &= \frac{1}{b-a}\int_a^b e^{tx}dx \\
    &= \frac{1}{b-a} \frac{e^{tx}}{t} \vert_a^b \\
    &= \frac{e^{bt}-e^{at}}{t(b-a)}
\end{align*}
$$


> [!tldr] Theorem (Uniqueness)
> 
> Suppose that random variables $X$ and $Y$ have MGF's $M_X(t)$ and $M_Y(t)$ respectively. If $M_X(t) = M_Y(t)$ for all $t$, then $X$ and $Y$ have the same distribution.

> [!tldr] Theorem
> <u>Theorem</u>
> 
> Suppose that $X$ and $Y$ are independent and each have moment generating functions $M_X(t)$ and $M_Y(t)$. Then the moment generating function of $X + Y$ is
> 
> $$
> \begin{align*}
>     M_{X + Y}(t) = E\left(e^{t(X + Y)}\right) = E\left(e^{tX}\right) E\left(e^{tY}\right) = M_X(t)M_Y(t)
> \end{align*}
> $$


We can use this to prove the following.

Suppose that $X \sim \mathcal{N}(\mu_1, \sigma_1^2)$ and $Y \sim \mathcal{N}(\mu_2, \sigma_2^2)$ and $X$ and $Y$ are independent.

$$
\begin{align*}
    X + Y \sim \mathcal{N}(\mu_1 + \mu_2, \sigma_1^2 + \sigma_2^2)
\end{align*}
$$


## Multivariate Moment Generating Functions

> [!info] Definition
> 
> The joint moment generating function of two random variables, $X$ and $Y$ is 
> 
> $$
> \begin{align*}
>     M(s,t) = E\left(e^{sX + tY}\right)
> \end{align*}
> $$


And so if $X$ and $Y$ are independent 

$$
\begin{align*}
    M(s,t) = E\left(e^{sX}\right)E\left(e^{tY}\right) = M_X(s)M_Y(t)
\end{align*}
$$

