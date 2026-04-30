# Guideline: Wiki Lint Health Checks

> **Gültig ab:** 2026-04-30  
> **Herkunft:** `WORKING/TOOLS/wiki_lint.py`  
> **Typ:** Tool Guideline / Health Monitor

---

## Warum

Kein Mechanismus erkennt verwaiste Whitepapers, stale LTM-Referenzen oder widersprüchliche Decisions.

---

## 7 Checks + L4b Orphaned Decisions

**Check:** `python WORKING/TOOLS/wiki_lint.py`

| Check | Level | Beschreibung |
|---|---|---|
| L1 | Index-Konsistenz | INDEX.md matches actual Whitepapers |
| L2 | Stale WPs | Whitepapers not updated in long time |
| L3 | Naming-Schema | Filenames follow naming convention |
| L4 | Decision-Promotion | Decisions promoted to Whitepapers |
| L4b | Orphaned Decisions | Decisions not promoted (16 orphane) |
| L5 | Cross-Refs | Cross-references consistent |
| L6 | LTM-Nummerierung | LTM entries sequential |
| L7 | Pending-Decisions | Pending Decisions tracked |

---

## Erstlauf

0 Errors, 12 Warnings, 2 Infos, 16 Orphaned Decisions (L4b)

---

## Regel

> **wiki_lint.py optionaler Schritt 7 in session-end.**  
> **Orphaned Decisions müssen in Whitepapers leben.**

---

> Letztes Update: 2026-04-30 — Initial creation. wiki_lint.py Health Checks.
