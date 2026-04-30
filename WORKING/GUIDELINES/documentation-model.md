# Guideline: Documentation Model

> **Gültig ab:** 2026-04-30  
> **Herkunft:** AAMS/2.0 Contract + READ-AGENT.md  
> **Typ:** Core Konvention / Vier-Schichten-Modell

---

## Warum

Vier dokumentierte Schichten garantieren Kontinuität über Sessions hinweg. Jede Schicht hat einen spezifischen Zweck — keine Duplizierung.

---

## Die vier Schichten

| Layer | Pfad | Zweck | Temporal |
|---|---|---|---|
| **Whitepaper** | `WORKING/WHITEPAPER/` | Stabile Architektur-Wahrheit. Written once, updated on decisions only. | Long-term |
| **Workpaper** | `WORKING/WORKPAPER/` | Session-Protokoll. Created at start, closed at end. | Session-scoped |
| **Diary** | `WORKING/DIARY/` | Pointer-only temporal index. WHAT touched WHEN. | Chronological |
| **Memory** | `WORKING/MEMORY/` | Long-term context store. Cross-session knowledge. | Cross-session |

---

## Regeln

### Whitepaper

- **Stabil:** Written once. Updated only on architectural decisions.
- **Nicht löschen:** Never deleted.
- **Nicht verschieben:** Never moved.
- **Naming:** `WP-{NNN}-{TOPIC}-{description}.md`
- **Index:** `INDEX.md` listet alle Whitepapers mit Status.

### Workpaper

- **Lifecycle:** active → observe → closed
- **Active:** `WORKING/WORKPAPER/` — wird gerade abgearbeitet
- **Observe:** `WORKING/WORKPAPER/observe/` — pausiert, muss beobachtet werden
- **Closed:** `WORKING/WORKPAPER/closed/` — abgeschlossen, archiviert
- **Naming:** `{DATE}-{TOPIC}-{SUBTOPIC}-{description}.md`
- **File Protocol:** Mandatory — created/modified/moved/deleted recorded.

### Diary

- **Pointer-only:** No content — only references.
- **Format:** `YYYY-MM-DD | WP: {workpaper} | WH: {whitepaper} | {other files}`
- **Monthly:** `YYYY-MM.md`
- **Compression:** daily → weekly → monthly (429 entries/year max)

### Memory

- **Dual-layer:** audit-log (ltm-index.md) + vector store (ChromaDB)
- **Ingest:** Every closed workpaper ingested.
- **Query:** At every session start.

---

## Wissenskette

```
WP → Whitepaper → LTM
```

Whitepaper updated BEFORE LTM ingested. LTM learns from current truth, not stale WPs.

---

## Regel

> **Keine Schicht darf übersprungen werden.**  
> **Keine Duplizierung zwischen Schichten.**  
> **Jede Schicht hat einen spezifischen Zweck.**

---

## Entdeckte Gaps

### Gap 1: Keine Guidelines existierten

**Problem:** Vier Schichten definiert, aber keine Guidelines als separate docs.  
**Fix:** Diese Guideline + Naming Schema + Workpaper Lifecycle + Decision-Promotion + File Protocol + LTM Rules + Topic Registry.

---

> Letztes Update: 2026-04-30 — Initial creation. AAMS/2.0 Documentation Model.
