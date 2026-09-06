---
name: make-plan
description: Create an evidence-backed phased implementation plan for work complex enough to span multiple execution contexts.
---

# Make a Plan

Create a plan another agent can execute without guessing about scope, APIs, or
completion.

Inspect the relevant code, tests, documentation, and existing patterns before
planning. Verify unfamiliar APIs against source or authoritative documentation.
Use subagents only when independent fact gathering is substantial enough to save
time or context; require concrete sources and re-check consequential claims.

Each phase should state:

- the outcome and files or subsystem involved;
- the source or existing pattern to follow when one matters;
- dependencies on earlier phases;
- observable verification and completion criteria.

Keep phases self-contained when they may run in separate contexts. Include API
details and anti-pattern warnings only when the evidence makes them relevant.
End with the checks that establish the whole plan is complete.
