# Guideline: Workpaper Lifecycle

> **Gültig ab:** 2026-04-30  
> **Herkunft:** WP-005-workpaper-lifecycle-states.md  
> **Typ:** Core Konvention / Session Lifecycle

---

## Warum

Workpapers haben drei Zustände — nicht zwei. Pausierte Workpapers verunreinigen den aktiven Flow.

---

## Die drei Zustände

| Zustand | Ordner | Bedeutung |
|---|---|---|
| **active** | `WORKING/WORKPAPER/` | Wird gerade abgearbeitet. Mehrere parallel erlaubt. |
| **observe** | `WORKING/WORKPAPER/observe/` | Muss beobachtet/beaufsichtigt werden. Wartet auf Input. |
| **closed** | `WORKING/WORKPAPER/closed/` | Abgeschlossen. Archiviert. |

---

## Kriterien

### → observe

Ein Workpaper geht nach `observe/` wenn:

- Nicht abgeschlossen
- Wartet auf externe Input/Entscheidungen
- Muss auf dem Schirm bleiben (beobachtet werden)
- Benötigt mehr Sessions als geplant
- Aktive Abarbeitung momentan nicht möglich aber relevant

### → closed

Ein Workpaper geht nach `closed/` wenn:

- Abgeschlossen
- Alle Decisions promoted oder verworfen
- File Protocol vollständig
- Ingest in Memory erfolgt
- Diary entry erstellt

---

## Migration

| Workpaper | Datum | Grund | Status |
|---|---|---|---|
| `2026-04-15-social-outreach.md` | 2026-04-15 | Pausiert — waiting | → observe/ |
| `2026-04-15-mempalace-analyse.md` | 2026-04-15 | Pausiert — waiting | → observe/ |
| `2026-04-02-wording-faktencheck.md` | 2026-04-02 | Pausiert — waiting | → observe/ |
| `2026-03-27-versioning-system.md` | 2026-03-27 | Abgeschlossen | → closed/ |
| `2026-03-31-field-report-analyse.md` | 2026-03-31 | Abgeschlossen | → closed/ |
| `2026-04-24-three-tests.md` | 2026-04-24 | Abgeschlossen | → closed/ |

---

## Active Workpapers

| Workpaper | Datum | Status |
|---|---|---|
| `2026-04-17-RES-WIKI-karpathy-llm-wiki-vergleich.md` | 2026-04-17 | active |
| `2026-04-29-projekt-analyse.md` | 2026-04-29 | active |

---

## Regel

> **Active Ordner signalisiert "was wird gerade gemacht".**  
> **Pausierte Workpapers gehören nach observe/ — nicht in active.**  
> **Closed Workpapers gehören nach closed/ — nicht in active.**

---

> Letztes Update: 2026-04-30 — Initial creation. WP-005 Workpaper Lifecycle.
