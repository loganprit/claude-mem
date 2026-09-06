---
name: do
description: Execute an existing multi-phase implementation plan when the user explicitly asks to carry out that plan.
---

# Execute a Plan

Use the plan as the source of scope, sequencing, and verification. Before changing
code, resolve any missing prerequisite that would materially change the result.

For each phase:

1. Read the cited source and documentation needed for that phase.
2. Implement the smallest change that satisfies the phase.
3. Run its relevant checks and fix failures caused by the change.
4. Record enough evidence for the next phase or a later context to continue.

Use subagents only when independent research, implementation, or review is
substantial enough to benefit from delegation. Keep synthesis and final review
with the orchestrator.

Follow the requested delivery endpoint and existing authorization for commits,
pushes, pull requests, deployments, and other external changes. Do not require an
extra approval for steps the user already authorized.
