---
id: 3
title: "29cm-promo-sheet: formula questions and fragile browser automation"
status: open
type: internal
skill: ["anthropic-skills:29cm-promo-sheet"]
proposes_skill: []
target_file: []
siblings_checked: "none — no skill-families registry exists in this workspace"
area: "(A) save snippet, (B) formulas and paste method"
date: 2026-10-01
session_context: "Read-only review of the 29cm-promo-sheet skill at the user's request"
parked_until: 
resolved:
resolution:
reference:
---

**Issue:** The review found items that need the owner's confirmation: G column
sign (`-IF`) added into D; T 이익 uses M while U divides by N; D excludes H with
no reason given; `$J$1315` with its sheet unspecified. Also fragile: an inline
XML-replace snippet with undefined variables and per-version style indices;
B depends on the Google Sheets DOM id `t-name-box`; "같은 품목" is undefined;
a one-off 209,000 decision is mixed into the rules; 10원 vs 1,000원 unit rules
are not explained; pricing benchmarks carry no date.

**Suggested improvement:** Get answers on the 4 formula questions, then move
the save snippet into a script with auto-detected indices and post-save
checks, test the Sheets API copyPaste as the primary path, add a
product-keyword mapping table, and move pricing benchmarks to a dated
reference file. The skill is account-synced (outside this repo), so changes
must be staged and installed by the user.

**Principle:** Inline code snippets in a skill rot. Ship them as scripts that
detect their own parameters and verify their output.
