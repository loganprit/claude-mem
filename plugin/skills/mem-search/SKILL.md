---
name: mem-search
description: Search claude-mem's persistent history when the user asks about work from previous sessions.
---

# Memory Search

Search first, then load only the history needed to answer accurately.

Use `search` with a focused query and project filter to find candidate
observations, sessions, or prompts. Narrow by date or observation type when that
improves relevance.

After reviewing the results:

- Answer from the index when its metadata is sufficient.
- Use `get_observations` for the selected IDs when full facts or narratives are
  needed. Batch multiple IDs in one request.
- Use `timeline` when surrounding chronology or cause and effect matters. It can
  center on an observation ID or find an anchor from a query.

Do not fetch full records merely because they were returned by search. If the
project is unclear and cannot be inferred from the working directory or request,
ask for it.
