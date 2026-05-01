Given 2 sets $A$ and $B$, we define a binary relation $R \subseteq A \times B$ as a binary relation over $A$ and $B$
For some $a \in A$ and some $b \in B$, we have $$(a, b) \in R \equiv aRb$$
## Relation operations
Takes in relations and outputs another relation
Given two relations $R \subseteq A \times B$ and $S \subseteq B \times C$, we have

| Operator name                                   | Set-builder notation                                                             | In terms of elements                                                                                                                      | Intuition (not mathematical)                               |
| ----------------------------------------------- | -------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------- |
| Composition<br>$S \circ R \subseteq A \times C$ | $S \circ R = \{(a, c) \in A \times C \mid \exists b \in B \: (aRb \wedge bSc)\}$ | $a(S \circ R)c \iff \exists b \in B \: (aRb \wedge bSc)$<br>$(a, c) \in S \circ R \iff \exists b \in B \: (a,b) \in R \wedge (b,c) \in S$ | $a \in A$ is related to $c \in C$ by some mutual $b \in B$ |
| Inverse $R^{-1} \subseteq B \times A$           | $R^{-1} = \{(b, a) \in B \times A \mid xRy\}$                                    | $bR^{-1}a \iff aRb$<br>$(b, a) \in R^{-1} \iff (a, b) \in R$                                                                              | Just swap the brackets                                     |
*(refer back to [[Set Theory#Set operations]] for other operations between relations*
**Theorem 2.4:** $(S \circ R)^{-1} = R^{-1} \circ S^{-1} \subseteq C \times A$
**Tutorial 4 Q8:** $T \circ (S \circ R) = (T \circ S) \circ R$ - relation composition is associative
## Properties of relations
Given a relation $R \subseteq A^2$ over some set $A$ 
*(make sure that **both** $R$ and $A$ are defined)

| Property                                               | Symbolic form                                                                                                                                                                                                                                                                                                                                                                       | How to prove                                                                  | Intuition (not mathematical)                                                    |
| ------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------- | ------------------------------------------------------------------------------- |
| **Reflexivity**<br>$aRa$ for all $a \in A$             | $\forall a \in A \:aRa$<br>$\forall a \in A \:(a, a) \in A$                                                                                                                                                                                                                                                                                                                         | Prove $(a,a)$ is in $R$ for **every element** $a$ in $A$                      | Every element is related to itself                                              |
| **Symmetry**<br>$(b, a) \in R$ whenever $(a, b) \in R$ | $\forall a \in A \:\forall b \in A \:(aRb \rightarrow bRa)$<br>$\forall a \in A \:\forall b \in A \:((a,b) \in R \rightarrow (b,a) \in R)$                                                                                                                                                                                                                                          | Consider some $(a,b)$ in $R$<br>Prove that $(b,a)$ is also in $R$             | If 2 elements are related, the relation goes both ways                          |
| **Antisymmetry**<br>$a=b$ whenever $aRb$ and $bRa$     | $\forall a \in A \:\forall b \in A \:(aRb \wedge bRa \rightarrow a = b)$<br>$\forall a \in A \:\forall b \in A$ $((a,b) \in R \wedge (b,a) \in R \rightarrow a = b)$<br>Contrapositive:<br>$\forall a \in A \:\forall b \in A \:(a \neq b \rightarrow \sim(aRb) \vee \sim(bRa))$<br>$\forall a \in A \:\forall b \in A$ $(a \neq b \rightarrow (a,b) \notin R \vee (b,a) \notin R)$ | Consider some $(a,b)$ in $R$ where $(b,a)$ is also in $R$<br>Prove $a=b$      | 2 different can only be related in one way (either $aRb$ or $bRa$ but not both) |
| **Transitivity**<br>$aRc$ whenever $aRb$ and $bRc$     | $\forall a \in A \:\forall b \in A \:\forall c \in A$ $(aRb \wedge bRc \rightarrow aRc)$<br>$\forall a \in A \:\forall b \in A \:\forall c \in A$$((a,b) \in R \wedge (b,c) \in R \rightarrow (a,c) \in R)$                                                                                                                                                                         | Consider some $(a,b)$ and $(b,c)$ in $R$<br>Prove that $(a,c)$ is also in $R$ | If 2 elements are related by a mutual then they are also related to each other  |
**Theorem 2.5:** $R$ is transitive $\iff R \circ R \subseteq R$
**Tutorial 5 Q2:** Given some $S \subseteq A \times B$, $S^{-1} \circ S \subseteq A^2$ is a **symmetric** relation
### Equivalence Relations
An equivalence relation is one that is **reflexive**, **symmetric** and **transitive**
- Reflexive: $\forall a \in A \:a \equiv a$
- Symmetric: $\forall a \in A \:\forall b \in A \:(a \equiv b \rightarrow b \in a)$
- Transitive: $\forall a \in A \:\forall b \in A \:\forall c \in A \:(a \equiv b \wedge b \equiv c \rightarrow a \equiv c)$
We can define an **equivalence class** as the set of all elements related under the equivalence relation:
$$[b]_\equiv = \{a \in A \mid a \equiv b\} \quad\text{or}\quad a \in [b]_\equiv \iff a \equiv b$$
**Theorem 2.6:** The set of all equivalence classes form a **partition** of the set $A$
$$\Pi = \{[b]_\equiv \in \mathcal{P}(A) \mid b \in A\}$$
**Tutorial 5 Q8:** $\forall a \in A \:\forall b \in A \:(a \equiv b \iff [a]_\equiv = [b]_\equiv)$
### Partial Order
A partial order is one that is **reflexive**, **antisymmetric** and **transitive**
- Reflexive: $\forall a \in A \: a \preccurlyeq a$
- Antisymmetric: $\forall a \in A \:\forall b \in A \:(a \preccurlyeq b \wedge b \preccurlyeq a \rightarrow a = b)$
- Transitive: $\forall a \in A \:\forall b \in A \:\forall c \in A \:(a \preccurlyeq b \wedge b \preccurlyeq c \rightarrow a \preccurlyeq c)$
A total order is a partial order where every element in $A$ is related to each other
- $\forall a \in A \:\forall b \in A \:(a \preccurlyeq b \wedge b \preccurlyeq a)$

## Relation to Graphs
We can represent any binary relation $R \subseteq A^2$ as some [[Graph Theory|directed graph]] $G = (A, R)$ where
- each element in $A$ is a node in the graph
- any $(a,b) \in R$ is a edge in the graph, where an edge $(a,a)$ is called a loop

Meanwhile any **symmetric** binary relation $S \subseteq A^2$ can be represented as an [[Graph Theory|undirected graph]] $G = (A, E)$ where
- each element in $A$ is a node in the graph
- any $(a, b) \in S$ can be represented by an undirected edge $\{a,b\} \in E$

#### Transitive Closure 
*bcos it's used in the graphs topic*
Given a binary relation $R \subseteq A^2$, if we define $R_n = \begin{cases} R & \text{if } n = 1 \\ R \circ R_{n-1} & \text{if } n \geq 2 \end{cases}$
the **transitive closure** is defined as $R_+ = \bigcup^\infty_{n=1} R_n$

