---
name: smart-explore
description: Use claude-mem's structural search tools for token-efficient symbol discovery in large code files.
---

# Smart Explore

Use the structural tools when a symbol-level view is more useful than loading a
large implementation file:

- `smart_search(query, path, max_results?, file_pattern?)` finds relevant files
  and ranked symbols across a directory.
- `smart_outline(file_path)` returns a file's imports and symbol skeleton.
- `smart_unfold(file_path, symbol_name)` returns one complete symbol.

Start with `smart_search` for conceptual discovery, `smart_outline` when the file
is already known, and `smart_unfold` after identifying the implementation that
matters. Skip an intermediate step when the prior result already supplies enough
structure.

Use ordinary exact search for strings, references, or path patterns. Read small
files, configuration, prose, or complete implementations directly when that is
clearer. For cross-file behavior, inspect callers and related state rather than
assuming one unfolded symbol explains the full flow.
