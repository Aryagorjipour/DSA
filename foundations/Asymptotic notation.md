---
title: Asymptotic notation
kind:
  - Foundation
---
## What
How time and space grow as input size `n` grows. Machine-independent. Worst case unless you say otherwise.

## Picture

![[Asymptotic notation.png]]

## Must know
- `O` = upper bound. `Ω` = lower bound. `Θ` = tight (both).
- Little-o / little-ω are *strict*: `n = o(n²)`, but `n²` is not `o(n²)`.
- Drop constants and dominated terms. `3n² + 100n + 7` is `Θ(n²)`.
- Best / average / worst are different claims. State which one.
- Time vs space are separate. An algorithm can be `O(n)` time and `O(1)` extra space.
- `n` is the input size you named. For graphs it is usually `V` and `E`, not a vague `n`.
- Worst case is the default in interviews and proofs. Average case needs a distribution. Amortized is not average — see [[Amortized analysis]].

Recognize on sight, fast to slow:

| Class | Name | Typical shape |
|---|---|---|
| `O(1)` | constant | index, hash expected, stack push |
| `O(α(n))` | inverse Ackermann | [[Union-Find]] with both optimizations |
| `O(log n)` | logarithmic | [[Binary search]], balanced tree height |
| `O(n)` | linear | single scan |
| `O(n log n)` | linearithmic | [[Merge sort]], heap sort, good comparison sorts |
| `O(n²)` | quadratic | nested loops, naive pairwise |
| `O(n³)` | cubic | [[Floyd-Warshall]], naive matrix multiply |
| `O(2ⁿ)` | exponential | subset recursion without prune |
| `O(n!)` | factorial | naive permutations |

Log base does not matter in Big-O: `log₂ n` and `ln n` differ by a constant.

How to read code:
- one loop `1..n` → `O(n)`
- nested independent loops → multiply
- input halved each step → `O(log n)`
- recursion → write a recurrence, then [[Recurrences]]

Comparison-model lower bound for sorting is `Ω(n log n)`. That does not apply in the RAM model with integer keys — see [[Comparison model vs RAM]].

## Pseudocode
Not an algorithm. After every other note, write time and space in this language.

```
COUNT(A):                     // Θ(n) time, Θ(1) extra space
    c ← 0
    for i ← 0 to A.length - 1
        c ← c + 1
    return c
```

## Related
- Next: [[Amortized analysis]], [[Recurrences]], [[Comparison model vs RAM]]
- Used by every DS and algo note
