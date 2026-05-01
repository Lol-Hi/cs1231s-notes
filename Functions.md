A function is a [[Relations|relation]] $f \subseteq X \times Y$ that satisfies

| Property | Symbolic form                                                                                                 | How to prove                                                                                       | Intuition (not mathematical)                       |
| -------- | ------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------- | -------------------------------------------------- |
| F1       | $\forall x \in X \:\exists y \in Y \:(x,y) \in f$                                                             | Consider some $x \in X$<br>Then we can find some expression $f(x) \in Y$ where $(x, f(x)) \in f$   | Every $x \in X$ maps to **at least one** $y \in Y$ |
| F2       | $\forall x \in X \:\forall y \in Y \:\forall y' \in Y$ $((x,y) \in f \wedge (x,y') \in f \rightarrow y = y')$ | Consider some $(x,y)$ in $f$ and assume we have another $(x,y')$  also in $f$<br>Prove that $y=y'$ | Every $x \in X$ maps to **at most one** $y \in Y$  |
We denote functions as $f: X \mapsto Y$ and use $f(x)$ to denote the **unique** $y \in Y$ such that $(x,y) \in f$: $$y = f(x) \iff (x,y) \in f$$
## Sets related to functions
For a function $f: X \mapsto Y$:
- $X$ is the known as the **domain** of the function
- $Y$ is known as the **codomain** of the function
- The **range** $\mathrm{range}(f)$ of the function is the set of all images $f(x)$ of the function: $$\mathrm{range}(f) = \{y \in Y \mid \exists x \in X \: y = f(x)\} \subseteq Y$$
## Function Properties
Given a function $f: X \mapsto Y$:

| Property             | Symbolic form                                                                                                                                                                               | How to prove                                                                                                                                                                  | Intuition (not mathematical)                            |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------- |
| Onto /<br>Surjective | $\forall y \in Y \:\exists x \in X \: y = f(x)$                                                                                                                                             | Consider some $y \in Y$<br>Then we can find some expression $g(y) \in X$ where $y = f(g(y))$                                                                                  | Every $y \in Y$ is mapped by **at least one** $x \in X$ |
| One-one / Injective  | $\forall x \in X \:\forall x' \in X$ $(f(x) = f(x') \rightarrow x = x')$<br><br><br><br>Contrapositive form: $\forall x \in X \:\forall x' \in X$ $(x \neq x' \rightarrow f(x) \neq f(x'))$ | Consider some $x$ and $x'$ in $Y$ where $f(x) = f(x')$<br>Prove that $x = x'$<br>*OR* <br>Consider some $x$ and $x'$ in $X$ where $x \neq x'$<br>Prove that $f(x) \neq f(x')$ | Every $y \in Y$ is mapped by **at most one** $x \in X$  |
A **bijective function** is a function that is **both one-one and onto**

## Function equality
*It's actually the same concept as [[Set Theory#Set relations|set equality]] but this is easier to work with*
**Theorem 2.7:** Given two functions $f: X \mapsto Y$ and $g: X \mapsto Y$ (note: both functions have **same domain** and **same codomain**):
$$f=g \iff \forall x \in X \:(f(x) = g(x))$$
## Function operations
*Same as the [[Relations#Relation operations|operations on relations]] but applied to the context of functions*
Given two functions $f: X \mapsto Y$ and $g: Y \mapsto Z$

| Operation                                                               | Set-builder notation                                    | In terms of elements                                          |
| ----------------------------------------------------------------------- | ------------------------------------------------------- | ------------------------------------------------------------- |
| Composition $g \circ f: X \mapsto Z$                                    | $g \circ f = \{(x,z) \in X \times Z \mid z = g(f(x))\}$ | **Theorem 2.8:** $\forall x \in X \:(g \circ f)(x) = g(f(x))$ |
| Inverse $f^{-1} \subseteq Y \times X$<br>*(not necessarily a function)* | $f^{-1} = \{(y, x) \in Y \times X \mid y = f(x)\}$      | $(y, x) \in f^{-1} \iff y = f(x)$                             |
## Theorems
Defining $i_X: X \mapsto X$ as the identity function defined where $\forall x \in X \:(i_X(x) = x)$,
Given any function $f: X \mapsto Y$:
- **Corollary 2.9:** $f \circ i_X = f$ and $i_Y \circ f = f$
- **Tutorial 7 Q2:** There exists $h: Y \mapsto X$ where $g \circ f = i_X$ and $f \circ g = i_Y$ 
  $\implies$ $f$ is bijective with $g = f^{-1}$
Given functions $f: X \mapsto Y$ and $g: Y \mapsto Z$
* **Theorem 2.12:** 
	* $f$ and $g$ are one-one $\implies$ $g \circ f$ is one-one
	- $f$ and $g$ are onto $\implies$ $g \circ f$ is onto
- **Tutorial 7 Q1:*
	- $g \circ f$ is one-one $\implies$ $f$ is one-one
	- $g \circ f$ is onto $\implies$ $g$ is onto
### For bijections
**Theorem 2.10:** If $f: X \mapsto Y$ is a **bijection**, then $f^{-1}$ is also a **bijection** $f^{-1}: Y \mapsto X$
- We thus have $x = f^{-1}(y) \iff y = f(x)$
- **Theorem 2.11:** then $f^{-1} \circ f = i_X$ and $f \circ f^{-1} = i_Y$

**Theorem 2.12:** Given two bijections $f: X \mapsto Y$ and $g: Y \mapsto Z$:
- $g \circ f: X \mapsto Z$ is also a bijection
- $(g \circ f)^{-1} = f^{-1} \circ g^{-1}$, which are mappings from $Z$ to $X$