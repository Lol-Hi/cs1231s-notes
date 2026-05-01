## Data Type: Sets
A set is an **unordered** collection of **distinct** elements
Sets are defined by **set-builder notation**: 
$$ A = \{a \in U | P(a)\} \iff (a \in A \leftrightarrow P(a))$$
### Set relations
*Since everything in this table are definitions, the relationship between whatever is written in the table is $\iff$

| Name                           | Written Definition (in Notes)               | Symbolic definition                                                                               |
| ------------------------------ | ------------------------------------------- | ------------------------------------------------------------------------------------------------- |
| Element of $x \in A$           | $x$ is an element of $A$                    | -                                                                                                 |
| Subset $A \subseteq B$         | every element of $A$ is an element of $B$   | $\forall x \in A \:(x \in B) \iff \forall x \in U \:(x \in A \rightarrow x \in B)$                |
| Set equality $A = B$           | all elements of $A$ and $B$ are equal       | $(A \subseteq B) \wedge (B \subseteq A) \iff \forall x \in U \:(x \in A \leftrightarrow x \in B)$ |
| Set inequality $A \neq B$      | $A$ and $B$ differ by at least 1 element    | $\exists a \in A \: (a \notin B) \vee \exists b \in B (b \notin A)$                               |
| Proper subset $A \subsetneq B$ | $A$ is a subset of $B$ but not equal to $B$ | $(A \subseteq B) \wedge (A \neq B) \iff (A \subseteq B) \wedge \exists x \in B \:(x \notin A)$    |
### Set operations
Takes in sets and outputs another set

| Name                              | Set-Builder Notation                                                                 | In terms of elements                                                                                                        | Intuition (not mathmatical)                      |
| --------------------------------- | ------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| Set union $A \cup B$              | $A \cup B = \{x \in U \mid x \in A \vee x \in B\}$                                   | $x \in A \cup B \iff x \in A \vee x \in B$                                                                                  | All elements in either set                       |
| Set inteesection $A \cap B$       | $A \cap B = \{x \in U \mid x \in A \wedge x \in B\}$                                 | $x \in A \cap B \iff x \in A \wedge x \in B$                                                                                | Only elements common to both sets                |
| Set difference $A - B$            | $A - B = \{x \in U \mid x \in A \wedge x \notin B\} = A \cap \overline{B}$           | $x \in A - B \iff x \in A \wedge x \notin B$                                                                                | Elements in $A$ that are not in $B$              |
| Set complement $\overline{A}$     | $\overline{A} = \{x \in U \mid x \notin A\}$                                         | $x \in \overline{A} \iff x \notin A$                                                                                        | All elements not in $A$                          |
| Power Set $\mathcal{P}(A)$        | "The set of all subsets of $A$"<br>$\mathcal{P}(A) = \{S \in U \mid S \subseteq A\}$ | $S \in \mathcal{P}(A) \iff S \subseteq A$                                                                                   | All possible subsets of $A$                      |
| Cartesian Product<br>$A \times B$ | $A \times B = \{(a, b) \mid a \in A \wedge b \in B\}$                                | $(a, b) \in A \times B \iff a \in A \wedge b \in B$$t \in A \times B \iff \exists a \in A \: \exists b \in B \: t = (a, b)$ | All possible pairings of elements of $A$ and $B$ |
### Partitions
A **partition** of a set $\Pi \subseteq \mathcal{P}(A)$ consists of subsets of $A$ with the following properties:
1. $\forall S \in \Pi \:(S \neq \varnothing)$ - all subsets in the partition are nonempty
2. $\forall S_i \in \Pi \:\forall S_j \in \Pi \:(i \neq j \rightarrow S_i \cup S_j = \varnothing)$ - all subsets in the partition are pairwise disjoint
3. $\bigcup_{S \in \Pi} S = A$  - union of all subsets of a partition forms the original set
Must prove all 3 properties to prove that a set is a partition
## Theorems
### Relating to empty set
The **empty set** $\varnothing$ is the set containing no elements, defined by 
$$\forall x \in U \: x \notin \varnothing$$
Hence to prove that $A \neq \varnothing$, we simply have to prove that $\exists x \in U \:(x \in A)$

| Label         | Written form (in notes)                | Symbolic form                                 |
| ------------- | -------------------------------------- | --------------------------------------------- |
| Corollary 2.2 | The empty set is a subset of every set | $\forall S \in U \:(\varnothing \subseteq S)$ |
| Corollary 2.3 | There is a unique empty set            | -                                             |

### Set operation identities
| Name of law     | Notation (Intersection)                                | Notation (Union)                                       |
| --------------- | ------------------------------------------------------ | ------------------------------------------------------ |
| Commutativity   | $A \cap B = B \cap A$                                  | $A \cup B = B \cup A$                                  |
| Associativity   | $(A \cap B) \cap C = A \cap (B \cap C)$                | $(A \cup B) \cup C = A \cup (B \cup C)$                |
| Distributivity  | $A \cap (B \cup C) = (A \cup B) \cap (B \cup C)$       | $A \cup (B \cap C) = (A \cap B) \cup (B \cap C)$       |
| Absorption      | $A \cap (A \cup B) = A$                                | $A \cup (A \cap B) = A$                                |
| De-Morgan's Law | $\overline{A \cap B} = \overline{A} \cup \overline{B}$ | $\overline{A \cup B} = \overline{A} \cap \overline{B}$ |
| Idempotence     | $A \cap A = A$                                         | $A \cup A = A$                                         |
| Identity        | $A \cap U = A$ and $A \cap \varnothing = \varnothing$  | $A \cup U = U$ and $A \cap \varnothing = A$            |
| Negation        | $A \cap \overline{A} \equiv \varnothing$               | $A \cup \overline{A} = U$                              |
|                 |                                                        |                                                        |
More negation laws: $\overline{\overline{A}} = A$ and $\overline{U} = \varnothing$ and $\overline{\varnothing} = U$
### Subset relation rules
From lecture notes: $A \cap B \subseteq A$ (and by extension also $A \cap B \subseteq B$)
From Tutorial 3 Q5:
Implications
- (iii) $A \subseteq B \implies A \cap C \subseteq B \cap C$
- (vi) $B = (A \cap \overline{B}) \cup (B \cup \overline{A}) \implies A = \varnothing$
Biconditionals
- (iv) $B \subseteq A \iff A \subseteq B = B$
- (v) $C \subseteq A \iff (A \cap B) \cup C = A \cap (B \cup C)$
From Tutorial 3 Q8: $\mathcal{P}(A) \cup \mathcal{P}(B) \subseteq \mathcal{P}(A \cup B)$

## Relations, Functions and Graphs
A **[[Relations|relation]]** $R$ is a set of tuples $(a_1, a_2, \cdots, a_n) \in R$ satisfying a certain predicate $P(a_1, a_2, \cdots, a_n)$: 
$$(a_1, a_2, \cdots, a_n) \in R \iff P(a_1, a_2, \cdots, a_n)$$
thus it is the subset of a cartesian product $$R = \{(a_1, a_2, \cdots, a_n) \in A_1 \times A_2 \times \cdots \times A_n \mid P(a_1, a_2, \cdots, a_n)\} \subseteq A_1 \times A_2 \times \cdots \times A_n$$
A **[[Functions|function]]** $f: X \mapsto Y$ is a relation, and thus is also a set of tuples and a subset of a cartesian product$$f = \{(x, y) \in X \times Y \mid y = f(x)\}\subseteq X \times Y$$
An **[[Graph Theory|undirected graph]]** $G = (V, E)$ consists of 2 sets: 
* A set of vertices $v \in V$
* A set of undirected edges $e\in E$, where $\exists u \in V \:\exists v \in V \:(e = \{u, v\})$
Meanwhile, a **[[Graph Theory|directed graph]]** $G = (V, D)$ also consists of two sets:
- A set of vertices $v \in V$
- A set of directed edges $d \in D$ where $\exists u \in V \:\exists v \in V (d = (u, v))$, hence $D \subseteq V \times V$ is a relation