*I am aware that this is probably not in the scope of the test, but it is still important to get the foundations right*
*Also important to see the parts about proofs and how to interpret statements*
*And make sure you are familiar with the operators and don't use them on the wrong data types*
## Data type: Boolean Expressions
A statement/proposition $P$ is a sentence that is either $\text{true}$ or $\text{false}$: $p \in \{\text{T}, \text{F}\}$
* If it is just $p$ or $q$ it is called a **statement variable**
* If it is constructed from statement variables using boolean operators , it is called a **compound statement**
### Boolean operators
Takes in a boolean and outputs a boolean
**Negation:** $\sim p$  is $\begin{cases} \text{true} & \text{if } p \text{ is false} \\ \text{false} & \text{otherwise}\end{cases}$
**Conjunction:** $p \wedge q$  is $\begin{cases} \text{true} & \text{if } p \text{ is true and } q \text{ is true}  \\ \text{false} & \text{otherwise}\end{cases}$
**Disjunction:** $p \vee q$  is $\begin{cases} \text{true} & \text{if } p \text{ is true or } q \text{ is true or both}  \\ \text{false} & \text{otherwise}\end{cases}$
**Conditional:** $p \rightarrow q \equiv \sim p \vee q$  which is $\begin{cases} \text{true} & \text{if } q \text{ is false or both } p \text{ and } q \text{ are true}  \\ \text{false} & \text{if } p \text{ is false but } q \text{ is true}\end{cases}$
**Biconditional:** $p \leftrightarrow q \equiv (p \rightarrow q) \wedge (q \rightarrow p)$ which is $\begin{cases} \text{true} & \text{if } p \text{ and } q \text{ are both true or both false} \\ \text{false} & \text{otherwise}\end{cases}$
### Relations for boolean statements
**Logical Equivalence:** Two Boolean expressions P and Q with the same statement variables are **logically equivalent** if and only if they have the same truth values for all choices of truth values for the variables
$$P \equiv Q \iff \forall b_1, b_2, \cdots, b_k \in \{\text{T},\text{F}\} \:(P(b_1, b_2, \cdots, b_k) \leftrightarrow Q(b_1, b_2, \cdots, b_k))$$
## Logical Quantifiers
**Universal statements:** $\forall x \in D \: P(x)$ is $\begin{cases} \text{true} & \text{if } Q(x) \text{ is true for every } x \text{ in } D \\ \text{false} & \text{if } Q(x) \text{ is false for any one } x \text{ in } D\end{cases}$
**Existential statements:** $\exists x \in D \: P(x)$ is $\begin{cases} \text{true} & \text{if } Q(x) \text{ is true for any one } x \text{ in } D \\ \text{false} & \text{if } Q(x) \text{ is false for every } x \text{ in } D\end{cases}$
## Theorems
#### Logical Equivalences (Properties of boolean operators)

| Name of law     | Notation (Conjunction)                                    | Notation (Disjunction)                                      |
| --------------- | --------------------------------------------------------- | ----------------------------------------------------------- |
| Commutativity   | $p \wedge q \equiv q \wedge p$                            | $p \vee q \equiv q \vee p$                                  |
| Associativity   | $(p \wedge q) \wedge r \equiv p \wedge (q \wedge r)$      | $(p \vee q) \vee r \equiv p \vee (q \vee r)$                |
| Distributivity  | $p \wedge (q \vee r) \equiv (p \vee q) \wedge (p \vee r)$ | $p \vee (q \wedge r) \equiv (p \wedge q) \vee (p \wedge r)$ |
| Absorption      | $p \wedge (p \vee q) \equiv p$                            | $p \vee (p \wedge q)$                                       |
| De-Morgan's Law | $\sim(p \wedge q) \equiv (\sim p) \vee (\sim q)$          | $\sim(p \vee q) \equiv (\sim p) \wedge (\sim q)$            |
| Idempotence     | $p \wedge p \equiv p$                                     | $p \vee p \equiv p$                                         |
| Identity        | $p \wedge t \equiv p$ and $p \wedge c \equiv c$           | $p \vee t \equiv t$ and $p \vee c \equiv p$                 |
| Negation        | $p \wedge (\sim p) \equiv c$                              | $p \vee (\sim p)\equiv t$                                   |
More negation laws: $\sim(\sim p) \equiv p$ and $\sim t \equiv c$ and $\sim c = t$
Contrapositive law (in lecture): $p \rightarrow q \equiv (\sim q) \rightarrow (\sim p)$
From Tutorial 1 Q4i: $p \vee (q \rightarrow r) \equiv (p \vee q) \rightarrow (p \vee r)$ 
#### Theorems Involving quantified statements
Negation of quantifiers: $\sim \forall x \in D \: P(x) \equiv \exists x \in D \:(\sim P(x))$ and $\sim\exists x \in D \: P(x) \equiv \forall x \in D \:(\sim P(x))$
From Tutorial 2 Q1: $(\forall x \in D \: P(x)) \wedge (\forall x \in D \: Q(x)) \iff \forall x \in D \: (P(x) \wedge Q(x))$
Theorem 2.1 in lectures: $\forall x \in A \:P(x) \iff \forall x \in U \:(x \in A \rightarrow P(x))$
## Using and Proving Statements
*Note: Explaining my own terminology*
* *"Using statements" is when we already know that this statement is true (either it is some definition/theorem from the notes/tutorial, or it's something we have proven in a previous part of the question) and we use it in our proofs to prove an unknown statement*
* *"Proving statements" is when we don't know if this statement is true yet, and we prove that it is true based on stuff we already know. It is thus important not to look like you are assuming that what you are trying to prove is true*

| Statement type                                   | How to prove                                                                                                                                                            | How to use (statement is already true)                                                                                                                          |
| ------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Negation: $\sim p$                               | Simply prove that $p$ is true                                                                                                                                           | Then $p \equiv \sim(\sim p)$ is true                                                                                                                            |
| Conjunction: $p \wedge q$                        | Prove that **both** $p$ and $q$ are true                                                                                                                                | Then $p$ is true, and $q$ is also true<br>(break down to individual statements)                                                                                 |
| Disjunction: $p \vee q$                          | Prove that either $p$ or $q$ is true<br>Usually division by cases, e.g.:<br>- Case 1: ... thus $p$ is true<br>- Case 2: ... thus $q$ is true<br>Thus $p \vee q$ is true | Then either $p$ or $q$ is true<br>We usually divide into cases:<br>- Case $p$ is true: ... (other implications)<br>- Case $q$ is true: ... (other implications) |
| Implication: $p \rightarrow q$                   | Assume $p$ is true<br>Prove $q$ is true                                                                                                                                 | **MP:** If we know $p$ is true, <br>then $q$ is true                                                                                                            |
| Biconditional: $p \leftrightarrow q$             | Either<br>1. Prove both $p \rightarrow q$ and $q \rightarrow p$<br>2. Use biconditionals at every step of the proof                                                     | Can Modus Ponens from either side                                                                                                                               |
| Universal statement<br>$\forall x \in D \: P(x)$ | Consider any $a \in D$<br>Prove that $P(a)$ is true                                                                                                                     | **UI:** Consider any $a \in D$, then $P(a)$ is true                                                                                                             |
| Existential statement $\exists x \in D \: P(x)$  | Find some example $e \in D$ where $P(e)$ is true                                                                                                                        | Then there is some $a \in D$ where $P(a)$ is true                                                                                                               |
### Contrapositive proofs
When you can't prove that a statement is true, you prove that it cannot be false!
Even though it's generally the form of $((\sim p) \rightarrow q \wedge (\sim q)) \rightarrow p$ , I generally see 2 ways to go about doing this:

| $\sim p$ leads to contradicting results                                                                                                                                                               | $\sim p$ leads to something that contradicts a truth                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1. Assume $\sim p$ is true<br>2. $\sim p$ results in $q$<br>3. $\sim p$ also results in $\sim q$<br>4. Hence $q$ and $\sim q$ is a contradiction<br>5. Hence $\sim p$ must be false<br>=> $p$ is true | This is often used when proving implications $q \rightarrow p$:<br>1. Assume $\sim(q \rightarrow p) \equiv q \wedge (\sim p)$<br>2. $\sim p$ leads to $\sim q$<br>3. Hence $q \wedge \sim q$, which is a contradiction<br>4. Hence $\sim(q \rightarrow p)$ has to be false<br>=> $q \rightarrow p$ is true |
### Mathematical Induction
Look for how **a smaller solution leads to a bigger solution** - $P(k) \rightarrow P(k+1)$
Then apply wishful thinking and recursion concepts

|                          | 1PI                                                               | 2PI                                                                                                       |
| ------------------------ | ----------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **Base Case(s)**         | **Prove** claim $P(n)$ is true for $n = b$                        | **Prove** claim $P(n)$ is true for $b \leq n \leq b+c$                                                    |
| **Inductive Hypothesis** | Assume the claim $P(n)$ is true for some $n = k$ where $k \geq b$ | Assume the claim $P(n)$ is true for all $b \leq n \leq k$, for some $k \geq b+c$                          |
| **Inductive Step**       | **Prove** that claim $P(n)$is true for $n = k + 1$                | **Prove** the claim $P(n)$ is true for $n = k+1$                                                          |
| Conclusion               | By 1PI, claim $P(n)$ is true for all $n \geq b$                   | By 2PI, claim $P(n)$ is true for all $n \geq b$                                                           |
| *Remarks*                  |                                                                   | *$c$ is the # of base cases<br>= # of previous claims $n \leq k$ needed to prove claim when $n = k + 1$*  |

## English Stuffs
*For you to understand the question*
**Tautology:** always true regardless of the truth values of statement variables $P\equiv\text{T}$
**Contradiction:** always false regardless of truth values of statement variables $P \equiv F$
Given a conditional statement $p \rightarrow q$:
* The **converse** is denoted as $q \rightarrow p$
* The **inverse** is denoted as $(\sim p) \rightarrow (\sim q)$
- The **contrapositive** is denoted as $(\sim q) \rightarrow (\sim p)$
- $p$ is a **sufficient condition** for $q$: if $p$ is true then we know that $q$ is true
- $q$ is a **necessary condition** for $p$: only if $q$ is true then $p$ can be true