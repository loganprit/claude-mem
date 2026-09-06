---
name: timeline-report
description: Generate a narrative development-history report from a named project's claude-mem timeline.
---

# Timeline Report

Build a sourced account of how a project changed over time from its claude-mem
history.

## Gather the history

Infer the project from the request or current repository. In a git worktree, use
the parent repository name rather than the worktree directory name. Ask only when
the project remains ambiguous.

Fetch the full timeline from:

```bash
curl -fsS "http://localhost:37777/api/context/inject?project=PROJECT&full=true"
```

If the worker is unavailable or the project has no observations, report that
directly. For a timeline too large for the available context, analyze explicit
time windows and reconcile their boundaries instead of silently dropping early
history.

## Write the report

Read [references/report-outline.md](references/report-outline.md) for the report
shape and evidence rules. Delegate analysis only when the history size benefits
from an independent context; keep final synthesis and source checks with the
orchestrator.

Include token economics only when the user asks for it or it materially helps the
report. In that case, read
[references/token-economics.md](references/token-economics.md) and keep measured
database facts separate from modeled estimates.

Save the report to the user's requested path, or
`./journey-into-PROJECT.md` when none is given. Report the path, date range, and
number of observations analyzed.
