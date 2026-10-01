---
id: 2
title: "Daily sales report command: gaps found in review and fixed"
status: actioned
type: internal
skill: []
proposes_skill: []
target_file: [".claude/commands/29cm.md"]
siblings_checked: "checked - instance-specific, no propagation"
area: "29cm daily report command, steps 1-5"
date: 2026-10-01
session_context: "User asked for a review of the command, then for fixes"
parked_until:
resolved: 2026-10-01
resolution: "Edited .claude/commands/29cm.md: added previous-day collection, pagination beyond 100 rows, header check before column indexes, mismatch stop rule, duplicate-post check, and backfill detection from channel history. Not applied: UI coordinates, CSS class selector and hardcoded product names (see body)."
reference:
---

**Issue:** The command had no previous-day collection although the report compares to it, fetched only page 1 of 100 rows, had no duplicate-post check or backfill detection, and no rule for an unreconciled check.

**Suggested improvement:** Applied as listed in resolution. Still open as residual risks: hardcoded click coordinates, a build-hashed CSS class for the scroll container, hardcoded column indexes and a hardcoded product-name list. These need a live browser session to replace safely.

**Principle:** A report that compares to a baseline must collect the baseline in the same procedure; a repeatable job needs an idempotency check before it posts.
