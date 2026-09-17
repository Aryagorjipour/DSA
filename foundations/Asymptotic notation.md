# Asymptotic notation

Kind: Foundation

## What
How time and space grow with input size `n`. Worst case by default unless you say otherwise.

## Picture

```mermaid
flowchart LR
    c["O(1)"] --> log["O(log n)"] --> lin["O(n)"] --> nlog["O(n log n)"] --> quad["O(n²)"] --> exp["O(2ⁿ)"]
```

## Must know
- O = upper bound. Ω = lower bound. Θ = tight.
- Drop constants and dominated terms. `3n² + 100n` is Θ(n²).
- Best / average / worst are different claims. Say which one.
- Classes you must recognize: O(1), O(log n), O(n), O(n log n), O(n²), O(n³), O(2ⁿ), O(n!).

## Pseudocode
Not an algorithm. When you finish any other note, write time and space in this language.

## Related
- Next: [[Amortized analysis]], [[Recurrences]]
- Used by every DS and algo note
