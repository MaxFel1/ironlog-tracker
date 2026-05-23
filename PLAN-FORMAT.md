# IRON.LOG — Trainingsplan-Format (für KI-Generierung)

Mit dieser Spezifikation kann **jede KI** (Claude, ChatGPT, Gemini …) dir einen
Trainingsplan im richtigen Format erzeugen. Du speicherst die Antwort als `.json`-Datei
und importierst sie in IRON.LOG über **Einstellungen ⚙ → Pläne verwalten → Plan importieren**.

---

## Das JSON-Format

```json
{
  "type": "ironlog-plan",
  "schemaVersion": 2,
  "name": "Mein Plan-Name",
  "days": [
    {
      "code": "UA",
      "name": "Upper A — Push",
      "weekday": "Mo",
      "exercises": [
        {
          "name": "Bankdrücken Langhantel",
          "sets": 4,
          "reps": "6-8",
          "rpe": "8",
          "rest": 180,
          "cues": "Schulterblätter zusammen, Brust raus",
          "alt": "Schrägbankdrücken"
        }
      ]
    }
  ]
}
```

## Feld-Erklärung

**Oberste Ebene:**
- `type` — muss exakt `"ironlog-plan"` sein (Pflicht, sonst wird die Datei nicht erkannt)
- `schemaVersion` — immer `2`
- `name` — Name des Plans (frei wählbar)
- `days` — Liste der Trainingstage (mindestens 1)

**Pro Tag (`days`):**
- `code` — Kurzkürzel, max. 6 Zeichen (z.B. `"UA"`, `"PUSH"`, `"P1"`) — wird in den Tab-Buttons angezeigt
- `name` — voller Name des Tages
- `weekday` — optionaler Wochentag-Hinweis, max. 4 Zeichen (z.B. `"Mo"`) — darf leer sein
- `exercises` — Liste der Übungen (mindestens 1)

**Pro Übung (`exercises`):**
- `name` — Übungsname (**Pflicht**)
- `sets` — Anzahl Sätze (Zahl, z.B. `4`)
- `reps` — Wiederholungen als Text (z.B. `"6-8"`, `"10"`, `"45-60s"`, `"8-10/Seite"`)
- `rpe` — Ziel-RPE als Text (z.B. `"8"`, `"7-9"`)
- `rest` — Pausenzeit in **Sekunden** (Zahl, z.B. `120`)
- `cues` — kurzer Technik-Hinweis (optional)
- `alt` — Alternativübung (optional)

> Hinweis: Übungs-IDs werden beim Import automatisch erzeugt – du musst keine angeben.

---

## Fertiger Prompt für eine KI

Kopiere den folgenden Text in eine beliebige KI und passe den ersten Absatz an deine
Wünsche an:

```
Erstelle mir einen Trainingsplan mit folgenden Vorgaben:
- Ziel: [z.B. Muskelaufbau / Kraft / Abnehmen]
- Trainingstage pro Woche: [z.B. 4]
- Split: [z.B. Upper/Lower, Push/Pull/Legs, Ganzkörper]
- Equipment: [z.B. komplettes Gym / Home-Gym / nur Kurzhanteln]
- Dauer pro Einheit: [z.B. 60 Min]
- Erfahrungslevel: [Anfänger / Fortgeschritten]
- Besonderheiten: [z.B. Schulterprobleme, Fokus auf Rücken …]

Gib mir das Ergebnis AUSSCHLIESSLICH als gültiges JSON im folgenden Format aus
(keine Erklärung, kein Markdown, nur das JSON):

{
  "type": "ironlog-plan",
  "schemaVersion": 2,
  "name": "...",
  "days": [
    {
      "code": "...",
      "name": "...",
      "weekday": "...",
      "exercises": [
        { "name": "...", "sets": 4, "reps": "6-8", "rpe": "8", "rest": 180, "cues": "...", "alt": "..." }
      ]
    }
  ]
}

Regeln:
- "type" muss exakt "ironlog-plan" sein
- "rest" ist in Sekunden als Zahl
- "reps" und "rpe" sind Strings
- Pro Tag 4-7 Übungen, sinnvolle Pausen (Compound 150-240s, Isolation 60-90s)
- Gib nur das JSON aus, sonst nichts
```

---

## So importierst du den Plan

1. KI-Antwort kopieren und als Datei speichern, z.B. `mein-plan.json`
   (am Handy: in einer Notiz-/Dateien-App als `.json` speichern)
2. In IRON.LOG: **⚙ Einstellungen → Pläne verwalten → Plan importieren (JSON)**
3. Datei auswählen → Plan wird importiert und automatisch aktiviert
4. Unter **Training** taucht der neue Plan mit seinen Tagen auf

Deine Trainings-Historie bleibt dabei immer erhalten. Du kannst beliebig viele Pläne
speichern und zwischen ihnen wechseln. Den Standard-Plan kannst du nicht löschen
(als Sicherheitsnetz), alle importierten schon.
