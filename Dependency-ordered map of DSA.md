# Dependency-ordered map of DSA

Full working set, ordered so each layer only needs what came before.

Scale: **0 = analysis. 1–40 = interview core. 41–75 = hard interviews + CP mid. 76–100 = CP / indexes / research structures.**

Code for implementations: [dsa-go](https://github.com/Aryagorjipour/dsa-go).

## 0. Foundations

Must know before item 1.

- [[Asymptotic notation]] — O, Ω, Θ. Best / average / worst.
- [[Amortized analysis]] — aggregate, accounting, potential. Needed for [[Dynamic array]], [[Splay tree]], [[Union-Find]], [[Fibonacci heap]].
- [[Recurrences]] — Master theorem, recursion trees.
- [[Divide and conquer]] vocabulary: split, conquer, combine.
- [[Loop invariants]]
- [[Bits]] — AND / OR / XOR, shifts, set / clear / test, popcount.
- Proof habits: induction, contradiction, exchange argument.
- [[Comparison model vs RAM]] — why [[Counting sort]] can beat n log n.

Common classes: `O(1)`, `O(log n)`, `O(n)`, `O(n log n)`, `O(n²)`, `O(2ⁿ)`, `O(n!)`.

## I. Linear memory

Requires: foundations.

1. [[Array]] → DS
2. [[Dynamic array]] → DS
3. [[Matrix]] → DS
4. [[String]] → DS
5. [[Bitset]] → DS

Must know: contiguous layout, index arithmetic O(1), grow-by-2 and amortized append, row-major vs column-major.

## II. Search, scan, sort

Requires: arrays + Big-O + [[Divide and conquer]].

6. [[Linear search]] → Algo
7. [[Binary search]] → Algo
8. [[Binary search on answer]] → Algo
9. [[Ternary search]] → Algo
10. [[Two pointers]] → Pattern
11. [[Sliding window]] → Pattern
12. [[Prefix sums]] → Pattern
13. [[Difference array]] → Pattern
14. [[Kadane]] → Algo
15. [[Merge intervals]] → Pattern
16. [[Bubble sort]] → Algo
17. [[Selection sort]] → Algo
18. [[Insertion sort]] → Algo
19. [[Merge sort]] → Algo
20. [[Quicksort]] → Algo
21. [[Counting sort]] → Algo
22. [[Radix sort]] → Algo
23. [[Bucket sort]] → Algo
24. [[Quickselect]] → Algo

Must know: binary search is a decision on a monotonic predicate. Comparison-sort lower bound Ω(n log n). Stable vs not.

## III. Pointer machines and LIFO / FIFO

Requires: arrays.

25. [[Singly linked list]] → DS
26. [[Doubly linked list]] → DS
27. [[Circular linked list]] → DS
28. [[XOR linked list]] → DS
29. [[Stack]] → DS
30. [[Queue]] → DS
31. [[Deque]] → DS
32. [[Circular buffer]] → DS
33. [[Monotonic stack]] → Pattern
34. [[Monotonic queue]] → Pattern
35. [[Fast slow pointers]] → Pattern

Must know: insert/delete O(1) once you hold the node. Access O(n). Stack = DFS / undo. Queue = BFS.

## IV. Hashing

Requires: arrays + amortized analysis.

36. [[Direct-address table]] → DS
37. [[Hash table]] → DS
38. [[Hash set]] → DS
39. Chaining → DS detail on [[Hash table]]
40. Open addressing → DS detail on [[Hash table]]
41. [[Rabin-Karp]] / rolling hash → Algo
42. [[Bloom filter]] → DS
43. [[Cuckoo hashing]] → DS
44. [[Perfect hashing]] → DS

Must know: average O(1) vs worst O(n). Load factor.

## V. Recursion and exhaustive search

Requires: [[Stack]] + recurrences.

45. [[Recursion]] → Paradigm
46. [[Divide and conquer]] → Paradigm
47. [[Backtracking]] → Paradigm
48. [[Branch and bound]] → Paradigm
49. [[Meet in the middle]] → Pattern
50. [[Bitmask enumeration]] → Pattern

## VI. Trees and heaps

Requires: recursion + arrays or nodes.

51. [[Rooted tree]] → DS
52. [[Binary tree]] → DS
53. [[Tree traversals]] → Algo
54. [[Binary Search Tree]] → DS
55. [[AVL tree]] → DS
56. [[Red-Black tree]] → DS
57. [[Splay tree]] → DS
58. [[B-tree]] / [[B+ tree]] → DS
59. [[Binary heap]] → DS
60. [[Heap sort]] → Algo
61. [[Priority queue]] → DS
62. d-ary heap → DS detail on [[Binary heap]]
63. [[Trie]] → DS
64. [[Compressed trie]] → DS

## VII. Graphs — core

Requires: queues, stacks, recursion, sets.

65. [[Graph]] representations → DS
66. [[DFS]] → Algo
67. [[BFS]] → Algo
68. [[0-1 BFS]] → Algo
69. [[Cycle detection]] → Algo
70. [[Connected components]] → Algo
71. [[Topological sort]] → Algo
72. Bipartite check → Algo on [[Graph]]
73. [[Bridges and articulation points]] → Algo
74. [[Strongly connected components]] → Algo
75. [[Union-Find]] → DS

## VIII. Graphs — weights

Requires: heaps + DSU + core graph.

76. [[Dijkstra]] → Algo
77. [[Bellman-Ford]] → Algo
78. SPFA → optional note under [[Bellman-Ford]]
79. [[Floyd-Warshall]] → Algo
80. [[Kruskal]] → Algo
81. [[Prim]] → Algo
82. [[Binary lifting]] / [[LCA]] → Algo
83. [[Euler tour of a tree]] → Pattern
84. Tree diameter / rerooting → Algo on [[Rooted tree]]

## IX. Greedy and DP

Requires: recursion, sorting, sometimes topo order.

85. [[Greedy]] → Paradigm
86. Activity selection → Algo under [[Greedy]]
87. Huffman coding → Algo under [[Greedy]]
88. Fractional knapsack → Algo under [[Greedy]]
89. [[Dynamic programming]] → Paradigm
90. Classic 1D DP → under [[Dynamic programming]]
91. Knapsack family → under [[Dynamic programming]]
92. LIS → under [[Dynamic programming]]
93. LCS / edit distance → under [[Dynamic programming]]
94. Grid DP → under [[Dynamic programming]]
95. Interval DP → under [[Dynamic programming]]
96. DP on trees → under [[Dynamic programming]]
97. Bitmask DP → under [[Dynamic programming]]
98. Digit DP → under [[Dynamic programming]]
99. DP optimizations (D&C DP, Knuth, CHT) → under [[Dynamic programming]]
100. Matrix exponentiation → Algo under [[Dynamic programming]]

Interview-solid cutoff for most engineers is here.

## X. Strings beyond hashing

101. [[KMP]] → Algo
102. [[Z-algorithm]] → Algo
103. [[Manacher]] → Algo
104. [[Aho-Corasick]] → Algo
105. [[Suffix array]] → DS
106. [[Suffix tree]] → DS
107. [[Suffix automaton]] → DS
108. [[FM-index]] → DS

## XI. Range queries

109. [[Sparse table]] → DS
110. [[Sqrt decomposition]] → Pattern
111. [[Fenwick tree]] → DS
112. [[Segment tree]] → DS
113. Lazy propagation → on [[Segment tree]]
114. [[Persistent segment tree]] → DS
115. 2D Fenwick / 2D segment tree → on those notes
116. Li Chao tree → DS
117. RMQ ↔ LCA → on [[Sparse table]] and [[LCA]]
118. [[Treap]] → DS
119. Order-statistic tree → DS
120. [[Wavelet tree]] → DS

## XII. Tree decompositions

121. [[Heavy-Light Decomposition]] → Pattern
122. [[Centroid decomposition]] → Pattern
123. [[Euler-tour tree]] → DS
124. [[Link-cut tree]] → DS

## XIII. Flows

125. Ford-Fulkerson / [[Edmonds-Karp]] → Algo
126. [[Dinic]] → Algo
127. Push-relabel → Algo
128. Min-cut → on max-flow notes
129. [[Bipartite matching]] → Algo
130. Min-cost max-flow → Algo
131. Hungarian → Algo
132. 2-SAT → Algo
133. Euler path → Algo
134. Hamiltonian / TSP DP → Algo
135. Planar graphs → specialist

## XIV. Geometry, algebra, numbers

136. Orientation / cross product → Algo
137. [[Convex hull]] → Algo
138. [[Sweep line]] → Algo
139. Rotating calipers → Algo
140. Half-plane intersection → Algo
141. [[Sieve of Eratosthenes]] → Algo
142. GCD / [[Extended Euclid]] → Algo
143. Modular inverse / CRT → Algo
144. [[Binary exponentiation]] → Algo
145. Primality + factorization → Algo
146. Discrete log → Algo
147. [[FFT]] → Algo
148. Gaussian elimination → Algo

## XV. Randomized, streaming, hardness

149. [[Randomized algorithms]] → Paradigm
150. [[Skip list]] → DS
151. Reservoir sampling → Algo
152. [[Online algorithms]] → Paradigm
153. Streaming sketches → DS
154. NP-completeness → Theory
155. [[Approximation algorithms]] → Paradigm
156. Parallel / work-span → Paradigm

## XVI. Modern / specialist structures

157. [[Fibonacci heap]] → DS
158. Binomial heap → DS
159. [[van Emde Boas tree]] → DS
160. x-fast / y-fast trie → DS
161. Fusion tree → DS
162. Scapegoat tree → DS
163. Cartesian tree → DS
164. [[Interval tree]] → DS
165. Range tree → DS
166. [[KD-tree]] → DS
167. Quadtree / R-tree → DS
168. Persistent DS (general) → DS
169. Confluent persistence → DS
170. Succinct / rank-select → DS
171. [[LSM-tree]] → DS
172. Learned indexes → DS
173. Rope / piece table → DS
174. Leftist / skew heap → DS
175. Soft heap → DS
176. Tango tree → DS
177. Cuckoo filter → DS
178. Count-Min sketch → DS
179. Persistent / rollback DSU → on [[Union-Find]]
180. Dynamic connectivity → DS

## How to use the map

- Interviews: foundations through section IX.
- CP: add X–XIII and the number-theory slice of XIV.
- Storage / search work: [[B+ tree]], [[LSM-tree]], [[Bloom filter]], [[Suffix array]], [[FM-index]].

Implement the representative of a layer. Know when the siblings win. Do not collect rare trees.
