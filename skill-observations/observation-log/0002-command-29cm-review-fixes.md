---
id: 2
title: "/29cm command: argument substitution broke TOP5, plus missing steps"
status: actioned
type: internal
skill: []
proposes_skill: []
target_file: [".claude/commands/29cm.md"]
siblings_checked: "none — target is a single command file, no family"
area: "steps 1, 2, 3 and 5"
date: 2026-10-01
session_context: "Reviewing and fixing the /29cm daily sales report command"
parked_until:
resolved: 2026-10-01
resolution: "Replaced the '$1' backreference with a callback and added a note banning dollar-digit; added previous-day stats collection, page>1 handling, header check, reconcile-failure stop, duplicate-post check, and backfill basis via channel history."
reference:
---

**Issue:** (1) The regex replacement `'$1'` was substituted with command
arguments at invocation, collapsing TOP5 into one item. (2) size=100 with no
pagination. (3) The "전일 대비" figures had no collection step. (4) No
duplicate-post check, no defined basis for "미보고" dates, no action when
reconciliation fails.

**Suggested improvement:** Applied in this session (see resolution). Still
open as fragility only: hardcoded UI coordinates and the `.css-1oz11rq` class.

**Principle:** Every number in a report template needs a named collection
step. Otherwise the agent estimates it.
