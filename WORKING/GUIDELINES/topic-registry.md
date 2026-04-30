# Guideline: Topic Registry

> **Gültig ab:** 2026-04-30  
> **Herkunft:** `.agent.json` `topic_registry` + READ-AGENT.md §Topic Registry  
> **Typ:** Core Konvention / Topic Tags

---

## Warum

TOPIC-Tags enable RFL pattern-matching. Ohne TOPIC-Tags keine konsistente cross-session Navigation.

---

## Topic Registry

| TOPIC | Meaning |
|---|---|
| `ARCH` | Architecture & system design |
| `SPEC` | Specification/Contract work |
| `LTM` | Long-term memory |
| `SEC` | Security & governance |
| `BOOT` | Bootstrap & onboarding |
| `FLD` | Field tests & reports |
| `RES` | Research & related work |
| `MKT` | Marketing & communication |
| `ISS` | Issue processing |
| `GOV` | Governance & process |
| `EDU` | Education & courses |

---

## Regeln

1. **max 4 letters**
2. **UPPERCASE**
3. **unique**
4. **extensible** — new tags may be added

---

## Maschinenlesbar

`.agent.json` `topic_registry`:

```json
"topic_registry": {
  "tags": ["ARCH", "SPEC", "LTM", "SEC", "BOOT", "FLD", "RES", "MKT", "ISS", "GOV", "EDU"],
  "extensible": true
}
```

Dies ermöglicht RFL-Pattern-Matching ohne manuelle Registry-Pflege.

---

## Regel

> **TOPIC enables RFL pattern-matching — priorität.**  
> **Tags sind ein Ordnungsschlüssel, nicht eine Beschreibung.**

---

> Letztes Update: 2026-04-30 — Initial creation. `.agent.json` topic_registry.
