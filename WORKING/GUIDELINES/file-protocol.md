# Guideline: File Protocol

> **Gültig ab:** 2026-04-30  
> **Herkunft:** READ-AGENT.md §File Protocol + `.agent.json`  
> **Typ:** Core Konvention / Session-Audit

---

## Warum

Ohne File Protocol weiß ein neuer Agent nicht was in der letzten Session passiert ist. File Protocol ist der Kern des Workpapers.

---

## File Protocol — Mandatory Section

Jedes Workpaper muss eine File Protocol section haben:

| Aktion | Datei | Zeit |
|---|---|---|
| CREATE | `{path}` | {date} |
| UPDATE | `{path}` | {date} |
| MOVE | `{from} → {to}` | {date} |
| DELETE | `{path}` | {date} |

---

## Track Rules

| Track | Type | Description |
|---|---|---|
| `track_created` | boolean | Record every newly created file (path, purpose, status) |
| `track_modified` | boolean | Record every modified file (what, why) |
| `track_moved` | boolean | Record every moved file (from, to, why) |
| `track_deleted` | boolean | Record every deleted file (why, verified?) |

---

## File Safety

**Outside WORKING/:**

- `check_git_history`: `git log --all --diff-filter=D -- <file>` examines whether a file has been committed.
- `if_history_found`: Files with git history may be relevant. Inform user before deletion.
- `if_no_history`: Files without git history may be safe to delete. Proceed with caution.
- `manual_rm_rf`: Never use rm -rf with manual file lists without git verification.

---

## Secrets Policy

**Never in Workpapers:**

- passwords
- tokens
- API keys
- credentials

**Use:** `.env` or external secret manager only.

---

## Regel

> **File Protocol ist mandatory — nicht optional.**  
> **Ohne File Protocol: Workpaper nicht schließen.**  
> **Never put secrets in workpapers.**

---

> Letztes Update: 2026-04-30 — Initial creation. READ-AGENT.md File Protocol.
