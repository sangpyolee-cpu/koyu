---
id: 1
title: "Review findings must be verified against the live file, not the injected prompt text"
status: open
type: open-source
skill: []
proposes_skill: []
target_file: []
siblings_checked: "no family registry exists; generic review practice, checked - no propagation"
area: "reviewing an existing skill or command"
date: 2026-10-01
session_context: "Reviewing a Slack report command; the invoked text differed from the repo file"
parked_until:
resolved:
resolution:
reference:
---

**Issue:** A review reported a bug ("literal replacement string in a regex") read from the prompt text injected when the command was invoked. The checked-in file held the correct replacement; the injected copy differed. The finding was wrong and was only caught when the file was opened to edit it.

**Suggested improvement:** Before reporting any defect in a skill or command, locate the file on disk and confirm the finding there. Label findings from injected text only as "unverified".

**Principle:** The text a harness injects is a copy of the artefact, not the artefact. Verify against the source of truth before reporting a defect, and say which one was read.
