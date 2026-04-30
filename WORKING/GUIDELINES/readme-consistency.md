# Guideline: README Consistency

> **Gültig ab:** 2026-04-30  
> **Herkunft:** WP-006-readme-consistency.md  
> **Typ:** Maintenance Guideline / External Consistency

---

## Warum

READMEs sind die externe Wahrnehmung. Veraltete READMEs = falsches Image.

---

## Reality Check — Divergenzen

| # | README sagt | Realität | Severity |
|---|---|---|---|
| 1 | Footer: **AAMS/1.0** | **AAMS/2.0** | 🔴 |
| 2 | Whitepapers: **4** | **6** | 🟡 |
| 3 | Contract Reference: `reference/SPEC.md` | `CONTRACT.md` | 🔴 |
| 4 | Closed workpapers: **~40** | **50** | 🟡 |
| 5 | Keine `observe/` mention | `observe/` exists | 🔴 |
| 6 | Lifecycle: active → closed | **active → observe → closed** | 🔴 |
| 7 | Health-Score: **10/10** | **7/10** | 🟡 |
| 8 | LTM: **116+** | **129** | 🟡 |
| 9 | Manifest-Prinzip (D9) nicht | **AAMS describes, not prescribes** | 🔴 |
| 10 | `topic_registry` nicht | **maschinenlesbar** | 🟡 |
| 11 | `.aams-version` nicht | **exists** | 🟡 |

---

## Fixes Applied

| README | Fixes |
|---|---|
| README.md | AAMS/2.0 + Manifest-Prinzip + observe/ + topic_registry + Current Status + CONTRACT.md reference |
| README.en.md | same fixes |
| README.zh.md | "规范" → Manifest + same fixes |

---

## Regel

> **READMEs müssen mit Reality Check konsistent sein.**  
> **Health-Score reflects actual consistency.**

---

> Letztes Update: 2026-04-30 — Initial creation. WP-006 README Consistency.
