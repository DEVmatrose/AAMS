# Guideline: Diary Format

> **Gültig ab:** 2026-04-30  
> **Herkunft:** READ-AGENT.md §Diary Layer + `.agent.json` `diary_path`  
> **Typ:** Maintenance Guideline / Temporal Index

---

## Warum

Diary is a **pointer-only temporal index** — records WHAT was touched WHEN, without duplicating content.

---

## Format

```
YYYY-MM-DD | WP: {workpaper-filename} | WH: {whitepaper if updated} | {other files}
```

**Beispiel:** `2026-04-30 | WP: 2026-04-30-ARCH-WPSTRUCT-workpaper-observe-folder.md (CLOSED) | WP: WP-005-workpaper-lifecycle-states.md | .agent.json, INDEX.md`

---

## Hierarchical Compression

1. **Daily entries** — one line per session, pointer only
2. **Weekly rollup** — which documents/TOPICs were active this week
3. **Monthly summary** — focus themes, activity volume

**429 entries/year max** (365 days + rollups)

---

## File Structure

**Monthly files:** `WORKING/DIARY/YYYY-MM.md`

**Bootstrap:** Creates `WORKING/DIARY/` folder. First file created lazily on first entry.

---

## Rules

1. **No content duplication** — if it's in a Workpaper or Whitepaper, don't repeat it
2. **Every chain link must add unique value** — Diary's value is the time axis
3. **Follow the pointer for details** — Diary answers "when", Workpaper answers "what" and "how"

---

## Regel

> **Diary is pointer-only temporal index.**  
> **No content — only references.**

---

> Letztes Update: 2026-04-30 — Initial creation. READ-AGENT.md Diary Layer.
