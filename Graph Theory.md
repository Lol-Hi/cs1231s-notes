## Data type: Graphs
A graph $G = (V, E)$ consists of a set $V$ of vertices and another set $E$ of edges between vertices
- For **undirected graphs**, edges $e \in E$ are represented as sets $e = \{u, v\}$ of vertices $u, v \in V$
- For **directed graphs**, edges $e \in E$ are represented as tuples $e = (u,v)$ of vertices $u,v \in V$
### Graph Relations

| Relation name                      | Mathematical definition                                                                                                                                                                                   | Intuition (not mathematical)                                                                        |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------- |
| Subgraph (partial order)           | $H = (V_H,E_H)$ is a subgraph of $G = (V_G,E_H)$ $\iff V_H \subseteq V_G \wedge E_H \subseteq E_G$                                                                                                        | $H$ is a graph formed by selecting a subset of the vertices and edges of $G$                        |
| Proper subgraph                    | $H$ is a proper subgraph of $G$ <br>$\iff H$ is a subgraph of $G \wedge H \neq G$                                                                                                                         | $H$ is a subgraph of $G$ but not equal to $G$                                                       |
| Isomorphism (equivalence relation) | $G=(V,E)$ is isomorphic to $G'=(V',E')$ $\iff \exists \text{permutation } \pi: V \mapsto V'$ $(\{u, v\} \in E \leftrightarrow \{\pi(u), \pi(v)\} \in E')$<br>If tree is rooted at $v_r$, $\pi(v_r) = v_r$ | $G$ and $G'$ "looks the same" if we ignore the vertex labels<br><br>(but don't ignore the **root**) |

### Significant subgraphs
Given a graph $G=(V,E)$

| Subgraph name                                | Mathematical definition                                                                                                                                                                                                                                                                                                                | Intuition (not mathematical)                                                 |
| -------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| Path <br>between $v_1 \in V$ and $v_p \in V$ | A subgraph of the form $P = (\{v_1, v_2, \cdots, v_p\}, \{\{v_1, v_2\}, \{v_2, v_3\}, \cdots, \{v_{p-1}, v_p\}\})$<br><br>$\mathrm{length}(P) = p-1$                                                                                                                                                                                   | Basically a sequence of edges that leads me from $v_1$ to $v_n$              |
| Cycle                                        | Undirected graphs: A subgraph of the form $C = (\{v_1, v_2, \cdots, v_c\}, \{\{v_1, v_2\}, \{v_2, v_3\}, \cdots, \{v_{c-1}, v_c\}, \{v_c, v_1\}\})$ where $c \geq 3$<br><br>Directed graphs: A subgraph of the form $C = (\{v_1, v_2, \cdots, v_c\}, \{(v_1, v_2), (v_2, v_3), \cdots, (v_{c-1}, v_c), (v_c, v_1)\})$ where $c \geq 2$ | A sequence of edges that forms a cycle back to the same node                 |
| Connected Component                          | A connected subgraph $H$ where there is no other connected subgraph $H'$ such that $H$ is a proper subgraph of $H'$:<br>1. $H$ is a connected subgraph of $G$<br>2. For any other connected subgraph $H'$ of $G$, $H$ is not the proper subgraph of $H'$                                                                               | The largest possible connected subgraph of $G$ containing these nodes/ edges |
| Spanning Tree                                | A subgraph $T=(V, E_T)$ of $G=(V,E)$ that is a tree and contains all the nodes of $G$                                                                                                                                                                                                                                                  | When you only select the edges of $G$ that forms a tree                      |
**Theorem 4.4:** Distinct nodes $u \in V$ and $v \in V$ are connected by a path 
$\iff$ $u$ and $v$ are in the same connected component in $G$
**Theorem 4.7:** $G$ is a finite connected undirected graph $\implies$ $G$ has a spanning tree
**Tutorial 10 Q7:** Given connected components $H_1=(V_1,E_1)$, $H_2=(V_2,E_2)$, ..., $H_k=(V_k,E_k)$ of a graph $G = (V,E)$, 
- $\{V_1, V_2, \cdots, V_k\}$ form a partition on $V$
- If $\forall i \in [1,k] \:(E_i \neq \varnothing)$, $\{E_1, E_2, \cdots, E_k\}$ also form a partition on $E$
## Types of graphs
**Tutorial 9 Q3:** The **complete graph** $K_n=(V,E)$ of $n$ nodes ia an undirected graph with
- an edge between every pair of nodes - $\forall u \in V \:\forall v \in V \:(\{u,v\} \in E)$
- a loop at every node - $\forall v \in V \:(\{v\} \in E)$

A **connected** graph is a trivial graph or a graph with a path between any 2 nodes 
- **Tutorial 11 Q4:** Given an undirected graph $G$, $G=(V,E)$ is connected $\implies$ $\vert E \vert \geq \vert V \vert - 1$
A **cyclic** graph is a graph that contains a loop or contains an edge 
- **Theorem 4.3:** If $G$ is undirected and has no loops, 
  $G$ is cyclic $\iff$ there are 2 distinct nodes with more than 1 path between them
- An **acyclic** graph is a graph that contains no loops and no edges
	- **Tutorial 11 Q5:** Given an undirected graph $G$, $G=(V,E)$ is acyclic $\implies$ $\vert E \vert \leq \vert V \vert - 1$
A **tree** is a graph that is **connected** and **acyclic**
* **Theorem 4.6:** $T=(V,E)$ is a tree $\iff$ removing any edge disconnects $T$ $\iff$ $|E| = |V| - 1$
* **Tutorial 11 Q6:** $T = (V, E)$ is a loopless undirected tree 
  $\iff$there is exactly 1 path between any 2 distinct nodes
#### Rooted Trees
*separated this part out bcos it's a big info dump, but will be impt for cs2040s*
A **rooted tree** $T = (V,E)$ is a tree with a distinguished node called the **root** $r$
- The **level** of a node $v$ is 0 if $v = r$, and the nubmer of edges in the path from $r$ to $v$ if $v \neq r$
- The **height** is the maximum level of any node $v \in V$
- Any node $u \in V$ that is along the path from $r$ to $v$ is the **ancestor** of $v$
  Then $v$ is also the **descendant** of $u$
	- When $\mathrm{level}(v)=\mathrm{level}(u)+1$, $u$ is the **parent** of $v$ and $v$ is the **child** of $u$
	- Nodes with children are known as **internal nodes**
	- Nodes with no children are known as **leaves**
- **Tutorial 11 Q8:** If a rooted tree has $p$ parents, and each parent has at most $b$ children, number of leaves $m = (b-1)p+1$
A **binary tree** is a rooted tree where every node has at most 2 children
- **Theorem 2.8:** A binary tree with $m$ leaves and height $h$ satisfies $m \leq 2^h$
- **Theorem 2.9:** If a binary tree has $m$ leaves, then it has $m-1$ internal nodes/parents

### Graph Operations
**Tutorial 10 Q10:** The **complement** $\overline{G} = (V,F)$ of a loopless undirected graph $G=(V,E)$ is the unique graph where any edge $\{u, v\}$ is in $F$ if and only if it is not in $E$: $$\overline{G}=(V,F) \text{ is the complement of } G=(V,E) \iff \forall u \in V \:\forall v \in V \:(u \neq v \rightarrow (\{u,v\} \in F \leftrightarrow \{u,v\} \notin E))$$
- For any graph $G$, $G$ and $\overline{G}$ cannot both be unconnected
### Relationship with relations
*refer to [[Relations#Transitive Closure]] for the definitions of $R_n$ and transitive closure $R_+$*
Consider an undirected graph $G=(V,E)$ and a relation $R \subseteq V^2$ defined as $$R = \{(u,v) \in V^2 \mid u \neq v \wedge \{u,v\} \in E\}$$
- **Theorem 4.1:** 
	- There is a path of length $n$ from $u \in V$ to $v \in V$ in $G$ $\implies$ $(u,v) \in R_n$
	- $\forall (u,v) \in R_n \:(\text{there is a path of length} \leq n \text{ from } u \text{ to } v \text{ in } G)$
- **Corollary 4.2:** $G$ is connected $\iff$ $\forall u \in V \:\forall v \in V \:(u \neq v \rightarrow (u,v) \in R_+)$
