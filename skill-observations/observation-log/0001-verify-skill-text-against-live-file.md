---
id: 1
title: "Review a command from its source file, not from the expanded prompt"
status: open
type: open-source
skill: [task-observer]
proposes_skill: []
target_file: []
siblings_checked: "none — no skill-families registry exists in this workspace"
area: "skill/command review procedure"
date: 2026-10-01
session_context: "Reviewing the /29cm slash command at the user's request (koyu repo)"
parked_until:
resolved:
resolution:
reference:
---

**Issue:** While reviewing the /29cm command I read the text injected into the
prompt and found the JS replacement `'검사'`. Grepping the source file showed
`'$1'` instead, which looked like a false finding. The real cause: Claude Code
substitutes positional arguments (`$0`, `$1`, …) into command files at
invocation, so the args "스킬 검사" rewrote a regex backreference in code. The
expanded prompt and the source differ, and neither alone explains the defect.

**Suggested improvement:** When reviewing a slash command or skill, diff the
expanded prompt against the source file on disk. Any difference is itself a
finding (argument substitution, templating). Add a lint check: no `$<digit>`
in command files that contain code.

**Principle:** A templated artefact has two versions, source and rendered.
Review both and treat the difference between them as evidence.
