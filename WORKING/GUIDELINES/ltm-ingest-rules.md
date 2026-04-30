# Guideline: LTM Ingest Rules

> **Gültig ab:** 2026-04-30  
> **Herkunft:** READ-AGENT.md §LTM Commands + `.agent.json` `ltm_triggers`  
> **Typ:** Core Konvention / Memory Management

---

## Warum

Ohne mandatory triggers, LTM gets forgotten. LTM ist querybar cross-session knowledge.

---

## Dual-Layer Architecture

| Komponente | Pfad | Zweck |
|---|---|---|
| Audit-Log | `WORKING/MEMORY/ltm-index.md` | Menschenlesbar. Was wurde wann ingested. Immer im Git. |
| Vektorspeicher | `WORKING/AGENT-MEMORY/` | Querybar. Semantische Suche. ChromaDB. |

**Warum beides:** Audit-Log ist die Wahrheit die Menschen lesen können. Vektorspeicher ist die Wahrheit die Agenten effizient abfragen können.

---

## LTM Triggers

| Trigger | Action |
|---|---|
| Context limit reached | Ingest current state → query in new session |
| Before new workpaper | Query LTM for topic context first |
| Before new whitepaper | Query LTM for existing architecture notes |
| Folder or file structure changed | Re-ingest affected documentation |
| Workpaper updated | Log change in workpaper file protocol |
| Workpaper closed | Ingest → move to `closed/` |
| Whitepaper updated | Re-ingest whitepaper into LTM |

---

## LTM Commands

### Track A — Markdown-only (default, zero dependencies)

No Python, no ChromaDB needed. Works on any fresh repo.

- **Query:** Read `WORKING/MEMORY/ltm-index.md` directly — scan for session topic
- **Ingest:** Append new entry to `WORKING/MEMORY/ltm-index.md` at session end

### Track B — Vector store (ChromaDB, requires Python)

**Query (Sessionstart):**
```powershell
.venv\Scripts\python.exe WORKING\AGENT-MEMORY\query.py "<Session-Thema>"
```

**Ingest (Sessionende):**
```powershell
.venv\Scripts\python.exe WORKING\AGENT-MEMORY\ingest.py
```

> ⚠️ **NICHT `wsl python3`, `python`, oder System-Python verwenden.**  
> **Nur das `.venv` im Workspace-Root enthält `chromadb`.**

---

## LTM Thresholds

| Einträge | Zustand | Was der Agent tut |
|---|---|---|
| < 90 | Normal | Audit-Log vollständig laden |
| ≥ 90 | **Warnung** | Agent meldet: Vektorspeicher fehlt, Kontext wird bald blind |
| ≥ 100 | **Blind** | Agent lädt nur die letzten 20 Einträge — ohne Vektorspeicher gibt es keine andere Option |

---

## Regel

> **Knowledge chain: WP → Whitepaper → LTM — never skip or reorder.**  
> **Whitepaper updated BEFORE LTM ingested.**  
> **Every closed workpaper ingested.**

---

> Letztes Update: 2026-04-30 — Initial creation. READ-AGENT.md LTM Commands.
