
> This is not “every named variant that ever existed.” 
> It is the complete working set people actually learn and use in 2026, ordered so each layer only needs what came before. 
> Sources aligned: current interview/CP roadmaps, GFG topic map, cp-algorithms, CLRS, and advanced-DS course lists (suffix structures, persistent/succinct trees, vEB, link-cut).

##### Scale
- **0 = analysis primitives.**
- **1–40 = interview core.**
- **41–75 = hard interviews + CP mid.**
- **76–100 = CP expert / databases / research structures.**

---

## 0. Foundations ([[foundations/Index|do this first]])

**Must know before item 1:**

- What a problem, an ADT, a data structure, and an algorithm each are
- Time vs space; input size n
- Asymptotic notation: Big-O (upper), Big-Ω (lower), Big-Θ (tight)
- Best / average / worst case
- Amortized analysis (aggregate, accounting, potential) — needed for dynamic arrays, splay, union-find, Fibonacci heaps
- Recurrences + Master theorem + recursion trees
- Divide and conquer vocabulary: split, conquer, combine
- Loop invariants
- Proof habits: induction, contradiction, exchange argument
- Bits: AND/OR/XOR, shifts, set/clear/test, popcount
- Comparison model vs integer/RAM model (why counting sort can beat n log n)

Common classes you must recognize on sight:  
*O(1)*, *O(log n)*, *O(n)*, *O(n log n)*, *O(n²)*, *O(n³)*, *O(2ⁿ)*, *O(n!)*.

If this layer is weak, later items become memorization.

---

## I. Linear memory and primitive access

**Requires:** [[#0. Foundations (do this first)|Foundations]].


1.  [[Array]] (static) #DS
2.  Dynamic array / resizable array #DS
3.  Matrix / 2D array #DS
4.  String (char sequence) #DS
5.  Bitset / bit array #DS


Must know: contiguous layout, index arithmetic `O(1)`, cache locality, resize strategy (usually ×2) and why append is amortized `O(1)`, row-major vs column-major, in-place vs extra space.

---

## II. Search, scan, and sort on sequences

**Requires:** arrays/strings + Big-O + divide and conquer.

6.  Linear search #Algo
7.  Binary search (on a sorted range) #Algo
8.  Binary search on answer / parametric #Algo
9.  Ternary search (unimodal) #Algo
10. Two pointers #Pattern
11. Sliding window (fixed + variable) #Pattern
12. Prefix sums #Pattern
13. Difference array #Pattern
14. Kadane (max subarray) #Algo
15. Merge intervals #Pattern
16. Bubble sort #Algo
17. Selection sort #Algo
18. Insertion sort #Algo
19. Merge sort     #Algo
20. Quicksort (incl. randomized) #Algo
21. Counting sort #Algo
22. Radix sort #Algo
23. Bucket sort #Algo
24. Quickselect / order statistics #Algo


Must know: binary search is a *decision* on a monotonic predicate, not “find in array.” Lower bound for comparison sorting is `Ω(n log n)`. When non-comparison sorts are legal (small integer keys). Stable vs unstable. In-place vs not.

---

## III. Pointer machines and LIFO/FIFO

**Requires:** arrays + Big-O. Recursion later uses the call stack as item 8.


25. Singly linked list #DS
26. Doubly linked list #DS
27. Circular linked list #DS
28. XOR linked list (space trick) #DS
29. Stack #DS
30. Queue #DS
31. Deque #DS
32. Circular buffer / ring buffer #DS
33. Monotonic stack #Pattern
34. Monotonic queue #Pattern
35. Fast/slow pointers (tortoise-hare) #Pattern

Must know: insert/delete `O(1)` *once you hold the node*; access is `O(n)`. Sentinel nodes. Stack = DFS / undo / parse. Queue = BFS / scheduling. Monotonic stack solves next-greater / histogram in `O(n)`.

---

## IV. Hashing

**Requires:** arrays + amortized analysis.

36. Direct-address table #DS
37. Hash table / hash map #DS
38. Hash set #DS
39. Collision handling: chaining #DS-detail
40. Collision handling: open addressing #DS-detail
41. Rolling / string hash (polynomial) #Algo
42. Bloom filter #DS
43. Cuckoo hashing #DS
44. Perfect hashing #DS

Must know: average `O(1)` vs worst `O(n)`. Load factor. Why hash + sort/two-sum is the default interview move. Rolling hash collision risk. Bloom: false positives, no false negatives. Cuckoo/perfect appear in systems and theory, not routine interviews.

---

## V. Recursion and exhaustive search

**Requires:** stack + recurrences.

45. Recursion (as a technique) #Pattern
46. Divide and conquer (as a paradigm) #Paradigm
47. Backtracking #Paradigm
48. Branch and bound #Paradigm
49. Meet in the middle #Pattern
50. Bitmask enumeration / submasks #Pattern

Must know: base case, state, call-tree size, tail vs non-tail. Backtracking template: choose → explore → unchoose. When `2ⁿ` or `n!` is acceptable. Meet-in-the-middle turns `2ⁿ` into `2ⁿ/²`.

---

## VI. Trees and heaps

**Requires:** recursion + arrays or nodes.

51. Rooted tree / N-ary tree #DS
52. Binary tree #DS
53. Tree traversals (pre/in/post/level) #Algo
54. Binary Search Tree #DS
55. AVL tree #DS
56. Red-Black tree #DS
57. Splay tree #DS
58. B-tree / B+ tree #DS
59. Binary heap #DS
60. Heap sort #Algo
61. Priority queue (ADT over a heap) #DS
62. d-ary heap / pairing ideas #DS
63. Trie / prefix tree #DS
64. Compressed trie / radix / Patricia #DS

Must know: height vs size. BST invariant. Why unbalanced BST degrades to a list. AVL = height-balanced; RB = color-balanced (what `std::map` / TreeMap use). B+ tree = databases and filesystems. Heap = `O(1)` peek, `O(log n)` push/pop, *not* a search tree. Trie = prefix / autocomplete.

---

## VII. Graphs — core

**Requires:** queues, stacks, recursion, hash/sets. DSU can be learned just before MST.

65. Graph representations (list / matrix) #DS
66. DFS #Algo
67. BFS #Algo
68. 0-1 BFS #Algo
69. Cycle detection (directed + undirected) #Algo
70. Connected components #Algo
71. Topological sort (DFS + Kahn)  #Algo
72. Bipartite check / 2-coloring #Algo
73. Bridges and articulation points #Algo
74. Strongly connected components #Algo
75. Union-Find / Disjoint Set Union #DS

Must know: adj list is the default. BFS = unweighted shortest path. DFS = structure (cycle, topo, SCC). DSU: path compression + union by rank → almost `O(1)` amortized (inverse Ackermann). Kosaraju and Tarjan for SCC.

---

## VIII. Graphs — weights, trees on graphs

**Requires:** heaps + DSU + core graph.

 
76. Dijkstra #Algo
77. Bellman-Ford   #Algo
78. SPFA (know it; treat as optional) #Algo
79. Floyd-Warshall #Algo
80. Kruskal MST #Algo
81. Prim MST #Algo
82. Binary lifting / LCA #Algo
83. Euler tour of a tree #Pattern
84. Tree diameter / rerooting DP #Algo
 

Must know: Dijkstra needs non-negative weights. Bellman-Ford handles negatives and detects negative cycles. Floyd is `O(n³)` all-pairs. Kruskal = sort + DSU. Prim = grow + heap. LCA via binary lifting is the workhorse for tree queries.

---

## IX. Greedy and Dynamic Programming

**Requires:** recursion, sorting, DAGs/topo for some DP.

85. Greedy (as a paradigm) #Paradigm
86. Activity selection / interval greedy  # Algo
87. Huffman coding #Algo
88. Fractional knapsack #Algo
89. DP: memoization + tabulation #Paradigm
90. Classic 1D DP (climb, coin, house) #Algo
91. Knapsack family (0/1, unbounded) #Algo
92. LIS / patience sorting #Algo
93. LCS / edit distance / string DP #Algo
94. Grid / path DP #Algo
95. Interval DP #Algo
96. DP on trees #Algo
97. Bitmask DP #Algo
98. Digit DP #Algo
99. DP optimizations (D&C DP, Knuth, CHT)  #Algo
100. Matrix exponentiation on recurrences  #Algo
 

That’s 100 numbered items if you stop at interview+standard CP. You asked for *all the way to current complex practice*, so the list continues. Treat 85–100 as the last “must” layer for most engineers. Everything below is specialist.

Must know: greedy needs a proof (exchange or stay-ahead). DP is recursion + cache: define *state*, *transition*, *base*, *order*. If you cannot name the state, you do not have a DP.

---

## X. Strings beyond hashing

**Requires:** arrays, KMP-style prefix thinking, sometimes trees.

 
101. KMP / prefix function #Algo
102. Z-algorithm #Algo
103. Manacher (longest palindrome) #Algo
104. Aho-Corasick  #Algo
105. Suffix array + LCP #DS
106. Suffix tree (Ukkonen) #DS
107. Suffix automaton #DS
108. Burrows-Wheeler + FM-index  #DS
 

Must know: KMP/Z are linear pattern matchers. Suffix array is the practical full-text index; suffix tree is more powerful and heavier. Suffix automaton is the CP favorite for “all distinct substrings.” FM-index is how real compressors/search engines index text.

---

## XI. Range queries and “contest trees”

**Requires:** trees, prefix sums, recursion, sometimes persistence.

 
109. Sparse table (static idempotent RQ)  # DS
110. Sqrt decomposition #Pattern
111. Fenwick tree / BIT #DS
112. Segment tree #DS
113. Segment tree + lazy propagation #DS
114. Persistent segment tree #DS
115. 2D Fenwick / 2D segment tree #DS
116. Li Chao tree #DS
117. Sparse table on trees / RMQ ↔ LCA #DS
118. Treap / implicit treap      #DS
119. Policy-based / order-statistic tree #DS
120. Wavelet tree #DS

Must know: sparse table = static min/max/gcd in `O(1)` after `O(n log n)` preprocess. Fenwick = prefix sums + point update, small and fast. Segment tree = general range query + update. Persistence = keep old versions (k-th in range). Wavelet tree = rank/select on sequences; used in compact indexes.

---

## XII. Heavy tree decompositions and dynamic trees

**Requires:** segment trees + LCA + DFS order.

 
121. Heavy-Light Decomposition #Algo
122. Centroid decomposition #Algo
123. Euler-tour tree #DS
124. Link-cut tree #DS
 

Must know: HLD reduces path queries on trees to `O(log² n)` segment-tree queries. Link-cut maintains a forest under link/cut. This is the start of *dynamic* graph DS.

---

## XIII. Flows, matchings, hard graphs

**Requires:** BFS/DFS + residual thinking.

 
125. Ford-Fulkerson / Edmonds-Karp #Algo
126. Dinic #Algo
127. Push-relabel #Algo
128. Min-cut (max-flow min-cut) #Algo
129. Bipartite matching (Kuhn / Hopcroft) #Algo
130. Min-cost max-flow #Algo
131. Hungarian assignment #Algo
132. 2-SAT #Algo
133. Euler path / circuit (Hierholzer) #Algo
134. Hamiltonian ideas / TSP exact DP #Algo
135. Planar graphs / faces (specialist) #Algo
 

Must know: flow is the algorithm behind matching, circulation, and many “assignment with capacity” problems. Dinic is the default practical max-flow. 2-SAT = implication graph + SCC.

---

## XIV. Geometry, algebra, numbers

**Requires:** sorting, stacks (hull), modular arithmetic, sometimes FFT.

 
136. Orientation / cross product #Algo
137. Convex hull (Graham / Andrew / Jarvis) #Algo
138. Sweep line (intersections, closest) #Algo
139. Rotating calipers #Algo
140. Line intersection / half-plane #Algo
141. Sieve of Eratosthenes + linear sieve #Algo
142. GCD / extended Euclid #Algo
143. Modular inverse / CRT #Algo
144. Fast pow / binary exponentiation #Algo
145. Primality + factorization #Algo
146. Discrete log / primitive root #Algo
147. FFT / NTT #Algo
148. Gaussian elimination #Algo
 

Must know: geometry lives on orientation tests and sweep. Number theory in DSA is “arithmetic that must be fast and exact under overflow/mod.” FFT is how you multiply big polynomials in `O(n log n)`.

---

## XV. Randomized, online, parallel, hardness

**Requires:** probability + all core paradigms.

 
149. Randomized algorithms (as a class) #Paradigm
150. Skip list #DS
151. Reservoir sampling #Algo
152. Online algorithms / competitive ratio #Paradigm
153. Streaming / sketching (HyperLogLog, Count-Min) #DS
154. NP-completeness (P vs NP, reductions) #Theory
155. Approximation algorithms #Paradigm
156. Parallel / PRAM / work-span (CLRS 27) #Paradigm
 

Must know: skip list ≈ probabilistic balanced tree (Redis uses this idea). Streaming sketches are how you count distinct / frequencies when the data does not fit. NP-completeness tells you when to stop looking for an exact poly-time algorithm.

---

## XVI. Advanced / modern structures (current ceiling)

These are what “100” means if you keep going: research courses, databases, compact indexes, theoretically optimal dictionaries. Not interview default. Used in production systems or CP at the top end.

 
157. Fibonacci heap #DS
158. Binomial heap  #DS
159. van Emde Boas tree #DS
160. x-fast / y-fast trie #DS
161. Fusion tree #DS
162. Scapegoat tree #DS
163. Cartesian tree #DS
164. Interval tree  #DS
165. Range tree / fractional cascading #DS
166. KD-tree #DS
167. Quadtree / Octree / R-tree #DS
168. Persistent DS (fat node / path copy) #DS
169. Confluent / functional persistence #DS
170. Succinct / compact DS (rank/select) #DS
171. LSM-tree #DS
172. Learned indexes #DS
173. Rope / piece table / gap buffer #DS
174. Leftist / skew heap #DS
175. Soft heap #DS
176. Tango tree / dynamic optimality #DS
177. Cuckoo filter / quotient filter #DS
178. Count-Min / Count sketch #DS
179. Persistent union-find / rollback DSU #DS
180. Dynamic connectivity (Holm et al.) #DS

Must know at this layer: you are no longer picking “a tree.” You are picking a *model* comparison, RAM, I/O, succinct) and a *workload* (point vs range, static vs dynamic, in-memory vs disk). LSM-tree = write-heavy storage (LevelDB, RocksDB). B+ tree = read-heavy disk indexes. vEB / x-fast = integer keys on a universe `U` in `O(log log U)`. Succinct = near-information-theoretic space. Persistence = time travel.

---

## How to use this without drowning

**If the goal is interviews (most engineers):**  
0 → 84, plus 85–98 well. Tries, DSU, Dijkstra, heap, segment-tree *awareness*. Stop before suffix automata and link-cut.

**If the goal is CP:**  
Add 101–122, 125–133, 141–147, rollback DSU, HLD.

**If the goal is databases / search / infra:**  
B+ tree, LSM, skip list, bloom, hash variants, suffix array / FM-index, succinct rank-select.

**Hard trade-off, named:**  
Coverage vs depth. Implementing 180 structures is wasted motion. Implementing each *layer’s representative* and knowing *when the others win* is the actual skill.

**Smallest working version of “learn DSA”:**
1. Foundations until you can state complexity without guessing.
2. Array + hash + two pointers + binary search + stack.
3. Recursion → tree DFS → heap → graph BFS/DFS.
4. Dijkstra + DSU + DP on 20 classic states.
5. Only then Fenwick/segment/trie/strings.

**What “must know” means per item, always:**
- Invariant
- Operations and their real complexities (worst vs amortized)
- When it beats the previous structure
- One failure mode (unbalanced BST, hash pile-up, Dijkstra + negatives, greedy without proof)

I can turn this into a one-page dependency graph, or a “minimum implement list” of ~25 structures you should actually code from scratch. Say which.