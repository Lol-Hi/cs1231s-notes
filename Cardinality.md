*Please do note that this set of notes has quite loose usage of the mathematical notation so I would advise against actually writing out the mathematical notation like this in your answers*
Two sets $X$ and $Y$ have the same cardinality iff there is a bijection between them: $$X \text{ and } Y \text{ have same cardinality} \iff \exists f: X \mapsto Y \:(f \text{ is bijective}) $$
**Tutorial 7 Q6 / Test 2 Q4:** Same cardinality is an equivalence relation
## Countable Sets
A set  is countable iff it is finite or it has the same cardinality as $\mathbb{N}$: $$X \text{ is countable} \iff X \text{ is finite} \vee \exists f: \mathbb{N} \mapsto X \:(f \text{ is bijective})$$**Tutorial 7 Q9:**  $X$ is countably iff it is empty, or there is an onto function from $\mathbb{N}$ to $X$ $$X \text{ is countable} \iff X = \varnothing \vee \exists f: \mathbb{N} \mapsto X \:(f \text{ is onto})$$*Intuition (not mathematical): I can store all of $x_i\in X$ in an array `X = [x1, x2, ...]` (either finite or infinite)*
#### "How do I make a countable set?" theorems
* **Theorem 3.5:** Every subset of a countable set is countable: $X \text{ is countable} \implies \forall Y \subseteq X \:(Y \text{ is countable})$
- **Tutorial 8 Q1:** $X$ and $Y$ are countable $\implies$ $X \cup Y$ are countable
- **Tutorial 8 Q2**: 
	- $\forall n\in\mathbb{N}\: (X_1, X_2, \cdots, X_n \text{ are countable} \implies \bigcup^n_{i=1}X_i \text{ is countable})$
	-  $\forall i\in\mathbb{N} \:(X_i \text{ is countable})$ $\implies$ $\bigcup^\infty_{i=0}X_i$ is countable 
- **Tutorial 8 Q6:** $X$ is finite $\iff$ $\mathcal{P}(X)$ is countable
### Finite Sets
A set is finite iff it is empty or it has the same cardinality as $\{1, 2, \cdots, n\}$ for some $n\in\mathbb{Z}^+$ $$X \text{ is finite} \iff X = \varnothing \vee \exists n\in\mathbb{Z}^+\:\exists\ f:\{1,2,\cdots,n\} \mapsto X \:(f \text{ is bijective})$$
*Intuition (not mathematical): I can store all of $x_i\in X$ in a finite array `X = [x1, x2, ..., xn]`*

### "How do I make a finite set?" theorems
**Lemma 3.9:** $X$ and $Y$ are finite $\implies$ $X \cup Y$ is finite
**Theorem 3.10**: $\forall n\in(\mathbb{Z}^+-\{1\}) \:(X_1, X_2, \cdots, X_n \text{ are countable} \implies \bigcup^n_{i=1}X_n \text{ is countable})$

More theorems in [[Permutations and Combinations]]
### Countably infinite sets
A set is countably infinite iff it has a same cardinality as $\mathbb{N}$: $$X \text{ is countably infinite} \iff \exists f: \mathbb{N} \mapsto X \:(f \text{ is bijective})$$
**Examples**
- **Theorem 3.2:** $\mathbb{Z}$ has the same cardinality as $\mathbb{N}$ *(and is thus countably infinite)*
- **Theorem 3.3:** $\mathbb{N}\times\mathbb{N}$ is countable *(it's also infinite)*
- **Theorem 3.4:** Set of all binary strings, $\{0,1\}^*$ is countable *(and also infinite)*

#### "How do I make a countably infinite set?" theorems
* **Theorem 3.6:** Every infinite set has a countably infinite subset: $X \text{ is infinite} \implies \exists Y \subseteq X \:(Y \text{ is countably infinite})$

## Uncountable Sets
A set is uncountable iff it is not finite and it does not have the same cardinality as $\mathbb{N}$: $$X \text{ is uncountable} \iff \sim(X \text{ is finite}) \wedge \forall f: \mathbb{N} \mapsto X \:\sim(f \text{ is bijective})$$
#### "How do I make an uncountable set?" theorems
* **Theorem 3.7**: A countably infinite set has uncountably infinite subsets: $X \text{ is countably infinite} \implies \mathcal{P}(X) \text{ is uncountable}$
* **Tutorial 8 Q5(i):** $\exists Y \subseteq X \:(Y \text{ is uncountable}) \implies X \text{ is uncountable}$
* **Tutorial 8 Q5(ii):** $X$ is uncountable and $Y$ is countable $\implies$ $X-Y$ is uncountable
* **Tutorial 8 Q8:** $A$ is infinite, $B$ is finite and $B \subseteq A$ 
  $\implies$ Set of all countable $X$ such that $B \subseteq X \subseteq A$ is uncountable
* **Corollary 3.8:** The set of all subsets of binary strings $\mathcal{P}(\{0,1\}^*)$ is uncountable