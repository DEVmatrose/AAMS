# Workpaper — Wording & Faktencheck: AAMS Value Proposition

- **Datum:** 2026-04-02
- **Typ:** Wording-Review / Faktencheck / Narrative Korrektur
- **Ziel:** Die zentrale AAMS-Argumentation ehrlich und differenziert formulieren

---

## Session-Ziel

Das bisherige AAMS-Narrativ hat eine schiefe Achse:

> **ALT (falsch/irreführend):** „KI-Agenten vergessen alles. AAMS gibt ihnen Gedächtnis."

Das ist faktisch nicht korrekt und wird zunehmend falscher. Claude Code hat bereits Session-Summaries, Cursor hat Composer-History, Google Gemini baut massiv an Kontext-Persistenz. Alle großen Player investieren hier. Das „Vergessen"-Argument wird uns als uninformiert dastehen lassen.

---

## Die echte Value Proposition (3 Argumente)

### Argument 1: Portabilität — Das Projekt-Gedächtnis gehört dem Projekt, nicht dem Tool

Jeder Coding-Agent baut sein eigenes Gedächtnis — aber **in seinem Ökosystem, in seinem Format, an seinem Ort**. Wechselst du von Cursor zu Claude Code, startest du bei null. Wechselt ein Teammitglied das Tool, ist der Kontext weg.

AAMS legt das Wissen **ins Repository** — in Git, in lesbaren Dateien, unter Versionskontrolle. Es gehört dem Projekt, nicht dem Tool.

> **Kernaussage:** „Dein Projekt-Wissen lebt im Repo — nicht in der Cloud eines Anbieters."

### Argument 2: Kleinste portable Einheit für agentisches Arbeiten

Eine einzige JSON-Datei reicht, um jedes Repo zu einem strukturierten Agenten-Workspace zu machen. Kein Framework, keine Runtime, keine Abhängigkeit. Du nimmst dein Paket und gehst damit zu jedem Agenten — Copilot, Claude Code, Cursor, oder was nächstes Jahr aktuell ist.

> **Kernaussage:** „Die kleinste Einheit, um überall agentisch arbeiten zu können."

### Argument 3: Projekt-Lebenszyklus über die Zeit

AAMS dokumentiert nicht nur die aktuelle Session — sondern die gesamte Geschichte eines Projekts: Warum wurde etwas entschieden (Diary), wie sieht die Architektur aus (Whitepaper), was wurde gelernt (Memory). Das ist mehr als Session-Memory — das ist **institutionelles Wissen**.

> **Kernaussage:** „Nicht nur merken, was gestern war — sondern die ganze Geschichte des Projekts mitführen."

---

## Was NICHT mehr gesagt werden darf

| Alte Formulierung | Problem | Ersatz |
|---|---|---|
| „KI-Agenten vergessen alles" | Falsch — viele haben bereits Session-Persistenz | „Jeder Agent merkt sich Dinge anders, an anderem Ort, in anderem Format" |
| „Jede Session startet bei null" | Übertrieben — Claude Code, Copilot etc. haben Kontextmechanismen | „Wechselst du das Tool oder das Team, startest du bei null" |
| „Kontextverlust ist unvermeidlich" | Zu pauschal | „Kontextverlust beim Tool-Wechsel und über lange Zeiträume ist unvermeidlich — ohne projekteigene Struktur" |
| Aufzählung von Produktnamen als „das Problem" | Positioniert uns gegen Produkte, die unsere Nutzer verwenden | Produktnamen nur neutral nennen: „funktioniert mit..." |
| „AAMS gibt Agenten Gedächtnis" | Reduces AAMS auf Memory-Feature | „AAMS macht jedes Repo zu einem portablen Agenten-Workspace" |

---

## Betroffene Dokumente — Audit

### 1. `docs/outreach/aams-onepager-akademisch.md`
- **Problem:** Erster Absatz „vergessen alles", Produktnamen als Problem, Bullet-Liste „Wiederholte Fehler"
- **Fix:** Problem umformulieren auf Portabilität + Lebenszyklus

### 2. `docs/outreach/email-vorlage-hochschule.md`
- **Problem:** Variante A: „verlieren zwischen Sessions den Kontext. Jede neue Sitzung startet bei null"
- **Problem:** Variante B: „leiden unter systematischem Problem: Session-übergreifender Kontextverlust"
- **Problem:** Beide: Produktnamen in der Problemstellung
- **Fix:** Argument auf Portabilität + Tool-Unabhängigkeit umstellen, Produktnamen nur bei „funktioniert mit"

### 3. `docs/kurskonzept-ki-campus-2026.md`
- **Problem:** Abschnitt 2 nennt Produktnamen, impliziert schlechtes Gedächtnis
- **Fix:** Lehrkurs — hier ist die Produktnennung weniger kritisch, aber Argument trotzdem schärfen

### 4. `WORKING/WHITEPAPER/WP-001-aams-overview.md` (Abschnitt 2)
- **Problem:** „Context lost. Session N+1 weiß nicht was Session N entschieden hat"
- **Fix:** Differenzieren — einzelne Tools arbeiten daran, aber: kein Standard, nicht portabel, nicht auditierbar

### 5. `README.md`
- **Problem:** „Your AI agent remembers everything" — ok als Claim, aber „across tools" ist der Schlüssel
- **Fix:** Prüfen, ob der Tool-Portabilitäts-Aspekt stark genug betont wird

---

## File Protocol

| Aktion | Datei |
|--------|-------|
| CREATED | `WORKING/WORKPAPER/2026-04-02-wording-faktencheck.md` |
| MODIFIED | `docs/outreach/aams-onepager-akademisch.md` |
| MODIFIED | `docs/outreach/email-vorlage-hochschule.md` |
| MODIFIED | `docs/kurskonzept-ki-campus-2026.md` |
| TO REVIEW | `WORKING/WHITEPAPER/WP-001-aams-overview.md` |
| TO REVIEW | `README.md` |

---

## Next Steps

- [ ] Outreach-Dokumente (E-Mails, 1-Pager) sofort fixen — die gehen bald raus
- [ ] KI-Campus-Konzept anpassen
- [ ] WP-001 und README separat reviewen (größerer Eingriff, eigene Session)
