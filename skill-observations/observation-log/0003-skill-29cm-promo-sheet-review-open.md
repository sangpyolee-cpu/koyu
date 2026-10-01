---
id: 3
title: "Promo sheet skill: formula and robustness issues awaiting owner decision"
status: open
type: internal
skill: ["anthropic-skills:29cm-promo-sheet"]
proposes_skill: []
target_file: []
siblings_checked: "checked - instance-specific, no propagation"
area: "sheet block formulas, XML fill script, browser copy-paste"
date: 2026-10-01
session_context: "User asked for a review of the skill; it lives outside the repo as a synced skill"
parked_until:
resolved:
resolution:
reference:
---

**Issue:** Formula questions needing the owner's answer: sign of the free-shipping column versus the cost total, mixed profit bases (price vs coupon price), why the platform coupon is excluded from cost, and an unexplained fixed commission cell. Robustness: the XML fill snippet has undefined variables and per-version style indexes; block creation relies on internal page element ids; the "same item" rule has no definition; a one-off judgement sits in the rules.

**Suggested improvement:** Get answers on the formulas, move the fill code to a script that detects style indexes and validates output, test whether the connected Sheets tools can copy blocks, add an item keyword table.

**Principle:** Automation that depends on a vendor's internal page structure needs a supported-API path or a fallback.
