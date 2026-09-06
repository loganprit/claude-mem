---
name: mem-search
description: Search claude-mem's persistent history when the user asks about work from previous sessions.
---

# Memory Search

Search first, then load only the history needed to answer accurately.

## The Workflow

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

## Search Parameters

- Use `query` for concrete concepts, filenames, decisions, errors, or identifiers.
- Set `project` from the current repository when possible.
- Add date bounds or observation types only when they improve precision.

## Examples

- For “What did we decide about caching?”, search for `caching decision` in the
  current project, then load the strongest matching observations.
- For “Why did this deploy fail?”, find the deploy event and use `timeline` for
  the events immediately before and after it.

## Why This Workflow

Search results are compact indexes. Loading only the selected records preserves
context while still providing the evidence needed for an accurate answer.
