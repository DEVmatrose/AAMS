# Guideline: Git Safety

> **Gültig ab:** 2026-04-30  
> **Herkunft:** `.agent.json` `file_safety`  
> **Typ:** Security Guideline / File Deletion

---

## Warum

Files outside WORKING/ should be treated with caution before deletion. Git history is the source of truth for file relevance.

---

## Rules

### Outside WORKING/

| Rule | Beschreibung |
|---|---|
| `check_git_history` | `git log --all --diff-filter=D -- <file>` examines whether a file has been committed. |
| `if_history_found` | Files with git history may be relevant. Inform user before deletion. |
| `if_no_history` | Files without git history may be safe to delete. Proceed with caution. |
| `manual_rm_rf` | Never use rm -rf with manual file lists without git verification. |

---

## Gitignore Patterns

| Pattern | Beschreibung |
|---|---|
| `WORKING/LOGS/*` | Exclude logs (except `.gitkeep`) |
| `!WORKING/LOGS/.gitkeep` | Keep .gitkeep |
| `WORKING/WORKPAPER/*.tmp` | Exclude tmp files |

---

## Regel

> **Git history is the source of truth for file relevance.**  
> **Never delete files with git history without user confirmation.**

---

> Letztes Update: 2026-04-30 — Initial creation. `.agent.json` file_safety.
