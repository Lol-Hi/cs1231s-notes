## Pigeonhole Principle
Given two [[Cardinality#Finite Sets|finite]] sets $X = \{x_1, x_2, \cdots, x_n\}$ and $Y = \{y_1, y_2, \cdots, y_n\}$:

| From Lecture 1                                                                                                        | From Lecture 3                                         |
| --------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| When $n > k$, <br>if $n$ cards are distributed among $k$ boxes,<br>then there exists a box with more than 1 card      | If $n > k$, there is no 1-1 function $f: X \mapsto Y$  |
| *(equivalent)* When $n < k$<br>if $n$ cards are distributed among $k$ boxes,<br>then there exists a box with no cards | If $n < k$, there is no onto function $f: X \mapsto Y$ |
## Counting scenarios
### Addition rule, Inclusion-Exclusion, Multiplication Rule
| Counting rule                                                                                                      | Intuition/when do you use it (not mathematical)                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Inclusion/Exclusion Principle**<br>$\vert A \cup B \vert = \vert A \vert + \vert B \vert - \vert A \cap B \vert$ | When what you are counting can be split into 2 scenarios, but you have to take note of not double counting the overlap<br><br>E.g. To count all functions which are either injective or surjective, we add the number of injective functions and number of surjective functions, minus the number of bijections |
| **Addition Rule**<br>If $A \cap B = \varnothing$, $\vert A \cup B \vert = \vert A \vert + \vert B \vert$           | When what you are counting can be split into 2 disjoint scenarios with no overlap<br><br>E.g. To count the number of countable sets, we sum the number of finite sets and the number of countably infinite sets                                                                                                 |
| **Lemma 3.9:**<br>If $B \subseteq A$, $\vert A - B \vert = \vert A \vert - \vert B \vert$                          | When what you are counting comes from a bigger set after excluding the a subset<br><br>E.g. To count the number of partial orders that are not total orders, we count the number of partial orders minus the cases where not every element is related to each other                                             |
| **Multiplication Rule**<br>$\vert A \times B \vert = \vert A \vert\vert B \vert$                                   | When what you are counting comes as a combination of two factors<br><br>E.g. When distributing 2 elements into a number boxes, we need to first put the first element in a box, and then place the second element in another box. The overall distribution is a combination of these 2 decisions.               |
From Lecture 2: To count the number of subsets of a set $A$ - $\vert\mathcal{P}(A)\vert = 2^{\vert A \vert}$
### Permutations and combinations
Let $\pi: \{1, 2, \cdots, n\} \mapsto \{1, 2, \cdots, n\}$ be a permutation (bijection)

| Name             | Formula                             | The Problem                                                                                                                                     |
| ---------------- | ----------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------- |
| $r$-Combinations | $\binom{n}{r} = \frac{n}{r!(n-r)!}$ | Number of ways to pick a subset $\{x_1, x_2, \cdots, x_r\} \subseteq S$ of size $r$ from a set $S$ of $n$ elements                              |
| Permutations     | $n! = n(n-1)\cdots1$                | Number of strings (ordered) $s_{\pi(1)}s_{\pi(2)} \cdots s_{\pi(n)}$ of length $n$ formed from elments of a set $S = \{s_1, s_2, \cdots, s_n\}$ |
| $r$-Permutations | $^nP_r = \frac{n}{(n-r)!}$          | Number of strings (ordered) $s_{\pi(1)}s_{\pi(2)} \cdots s_{\pi(r)}$ of length $r$ formed from elments of a set $S = \{s_1, s_2, \cdots, s_n\}$ |
#### Combinatorial Identities
**Tutorial 10 Q1:** $\binom{n}{r} + \binom{n}{r-1} = \binom{n+1}{r}$
**Tutorial 10 Q3:** $(x + y)^n = \sum^n_{r=0}\binom{n}{r}x^{n-r}y^r$
* **Tutorial 10 Q2:** $\binom{n}{0} + \binom{n}{1} + \cdots + \binom{n}{n} = 2^n$
**Tutorial 10 Q4:** $\binom{0}{r} + \binom{1}{r} + \binom{2}{r} + \cdots + \binom{n}{r} = \binom{n+1}{r+1}$
**Tutorial 10 Q5**: $\binom{m}{0}\binom{n}{r} + \binom{m}{1}\binom{n}{r-1} + \cdots + \binom{m}{r}\binom{n}{0} = \binom{m+n}{r}$

### Counting Relations/Functions
**Tutorial 10 Q6:**
- (i) Number of relations $R \subseteq A \times B$ = $2^{\vert A \vert \vert B \vert}$
- (ii) Number of functions $f: A \mapsto B$ = ${\vert B \vert}^{\vert A \vert}$
- (iii) Number of injective functions $f: A \mapsto B$ = $^{\vert B \vert}P_{\vert A \vert}$ when $|A| \leq |B|$
- (iv) Number of bijective functions $f: A \mapsto B$  = $n!$ where $|A| = |B| = n$