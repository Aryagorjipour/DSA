# DSA

Obsidian vault for notes. Code lives in a separate repo: [dsa-go](https://github.com/Aryagorjipour/dsa-go).

Open this folder as a vault in Obsidian. Write notes. Link them. That is the whole system.

## Folders

| Folder | What belongs here |
|---|---|
| `foundations/` | Analysis tools. Not a DS and not an algorithm. Big-O, amortized analysis, recurrences, bits. |
| `ds/` | Data structures. How data is stored. Array, heap, graph, segment tree. |
| `algo/` | Named algorithms. Binary search, Dijkstra, KMP, Kruskal. |
| `paradigm/` | Design methods that produce many algorithms. Divide and conquer, greedy, DP, backtracking. |
| `pattern/` | Reusable problem moves. Two pointers, sliding window, prefix sums, monotonic stack. |
| `problem/` | One note per problem you actually solve. Link back to the DS / algo / pattern you used. |
| `attachments/` | Images only. Drop the file, embed it with `![[filename]]`. |

The map of the whole list is [[Dependency-ordered map of DSA]].

## How to write a note

Keep every topic note to five sections. Nothing else is required.

```md
# Array

Kind: DS

## What
One sentence. What it stores and what it makes cheap.

## Picture
![[array.png]]

## Must know
- Invariant
- Operations and real complexities
- When it loses to the next structure

## Pseudocode
(the operations, not a novel)

## Related
- Built from: [[...]]
- Used by: [[...]]
- Go: `ds/array` in dsa-go
```

If a section has nothing yet, leave it empty. Do not invent filler.

## How notes relate

Use `[[Note name]]`. That is the contract.

- A DS note links to the algorithms that run on it.
- An algo note links to the DS it needs and the paradigm it belongs to.
- A pattern note links to the DS it usually sits on (most patterns sit on [[Array]] or [[String]]).
- A problem note links to whatever you used, and one line on why.

Obsidian will create the file when you click a link that does not exist yet. Put the new file in the right folder.

## Naming

- File name = title. `Binary search.md`, not `07-binary-search.md`.
- One topic per file.
- Kind line at the top: `DS` | `Algo` | `Paradigm` | `Pattern` | `Problem` | `Foundation`.

## What this vault is not

No templates. No Dataview. No graph setup. No daily notes. No tags required.

Backlinks in the sidebar are enough to see what points here.

## Study loop

1. Read the topic on the map.
2. Write the note (picture + must know + pseudocode).
3. Implement it in [dsa-go](https://github.com/Aryagorjipour/dsa-go).
4. Solve one problem. Put that write-up in `problem/`.
5. Link the three together.

## Open in Obsidian

1. Clone this repo.
2. Obsidian → Open folder as vault → this folder.
3. Settings are already in `.obsidian/` (attachments go to `attachments/`, graph plugin off, templates off).
