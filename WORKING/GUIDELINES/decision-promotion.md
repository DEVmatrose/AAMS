# Guideline: Decision-Promotion

> **Gültig ab:** 2026-04-30  
> **Herkunft:** READ-AGENT.md §Decision-Promotion + wiki_lint.py L4b  
> **Typ:** Core Konvention / Session-Close Protocol

---

## Warum

Eine Entscheidung die nur im Workpaper lebt, existiert nicht für das System. Decisions müssen in Whitepapers leben.

---

## Decision-Promotion — Session-Close Checklist

**Erforderlich vor jedem Session-Close.**

Bevor du diese Session schließt, prüfe:

- [ ] Wurde eine Architektur-Entscheidung getroffen?
  - [ ] Ist sie in `WORKING/WHITEPAPER/INDEX.md` eingetragen?
  - [ ] Wurde das betroffene Whitepaper aktualisiert?
- [ ] Existieren offene Decisions in diesem Workpaper?
  - [ ] Sind alle offenen Decisions in einem Whitepaper gepromoted?
  - [ ] Falls nein: Workpaper schließen und erst nach Decision-Promotion wieder öffnen.

**Regel:** Keine offenen Decisions in Workpapers nach Session-Ende.

---

## [PROMOTE→WP-xxx] Tag

Eine Decision die architekturell relevant ist:

1. **Taggen:** `[PROMOTE→WP-xxx]` in Decisions section
2. **Whitepaper erstellen/aktualisieren:** Target Whitepaper
3. **INDEX.md update:** New entry in Whitepaper Index
4. **LTM ingest:** Whitepaper ingested
5. **Workpaper schließen:** Alle [PROMOTE→WP-xxx] tags gelöst

---

## wiki_lint.py L4b — Orphaned Decisions

**7 Checks + L4b Orphaned Decisions** (16 orphane Decisions detektiert)

**Check:** `python WORKING/TOOLS/wiki_lint.py` zeigt orphane Decisions.

---

## Regel

> **Kein Workpaper darf mit ungelösten [PROMOTE→WP-xxx] Tags geschlossen werden.**  
> **Die Decision muss in einem Whitepaper leben, nicht im Workpaper.**

---

> Letztes Update: 2026-04-30 — Initial creation. READ-AGENT.md Decision-Promotion.
