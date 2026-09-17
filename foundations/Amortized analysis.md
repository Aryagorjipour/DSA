---
title: Amortized analysis
kind:
  - Foundation
---
## What
Cost of an operation averaged over a *sequence* of operations on the same structure. Not average-case. No probability required.

A single call can be expensive. The sequence is still cheap.

## Picture

![[Amortized analysis.png]]

## Must know
- Worst-case per call can lie. Dynamic-array append is `O(n)` when it resizes and `O(1)` amortized.
- Three methods, same answer if you do them right:
  1. **Aggregate.** Total cost of `n` ops is `T(n)`, amortized cost is `T(n)/n`.
  2. **Accounting.** Overcharge cheap ops, bank the extra, spend the credit on expensive ops. Credit never goes negative.
  3. **Potential.** Φ maps state → number ≥ 0. Amortized cost of op `i` is `ĉᵢ = cᵢ + Φᵢ − Φᵢ₋₁`. Sum of `ĉ` telescopes to real cost plus net potential.
- Amortized `O(1)` does not mean every call is `O(1)`. Real-time / hard latency still cares about the spike.
- Different from average-case: average-case assumes a distribution over inputs. Amortized assumes a sequence of ops, adversarial is allowed.

Worked example — [[Dynamic array]] grow-by-2, start empty, `n` appends:

- Copies happen at sizes 1, 2, 4, …, `2^k` with `2^k < n`.
- Total copies `< n`. Total append work `Θ(n)`. Amortized append `Θ(1)`.
- Accounting: charge 3 tokens per append (1 to store, 2 in the bank). A resize of `k` elements is prepaid.
- Potential: `Φ = 2n − cap` works after the first resize. Empty start needs a small adjustment; the aggregate proof is enough.

Where it shows up later:
- [[Dynamic array]] append
- [[Splay tree]] (potential on rank)
- [[Union-Find]] with rank + path compression → amortized `O(α(n))`
- [[Fibonacci heap]] decrease-key
- Table doubling / hash rehash

## Pseudocode

```
APPEND(A, x):                          // amortized Θ(1)
    if A.length = A.capacity
        B ← new array of size 2 * A.capacity
        copy A into B
        A ← B
    A[A.length] ← x
    A.length ← A.length + 1
```

Aggregate: `n` calls copy `1+2+4+…+n` < `2n` cells. Total `Θ(n)`.

## Related
- Needs: [[Asymptotic notation]]
- Next: [[Recurrences]]
- Used by: [[Dynamic array]], [[Hash table]], [[Splay tree]], [[Union-Find]], [[Fibonacci heap]]
