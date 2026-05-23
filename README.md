# IRON.LOG — Hypertrophy Tracker PWA

Krafttraining-, Ernährungs- & Gewichts-Tracker für 4er Upper/Lower Split mit Hypertrophie-Fokus.

## ⚡ Schnellstart auf Android

### Option A: Lokal ohne Server (einfach)
1. `index.html` auf dein Android-Handy kopieren (z.B. via USB, Email, Cloud)
2. Mit **Chrome** öffnen
3. Menü (⋮) → **"Zum Startbildschirm hinzufügen"**
4. Fertig — App-Icon liegt am Homescreen

**Hinweis:** Ohne HTTPS-Hosting funktioniert die volle PWA-Installation (mit Splash-Screen) eingeschränkt. Die App selbst läuft aber komplett offline mit localStorage.

### Option B: Mit Hosting (volles PWA-Erlebnis)
1. Beide Dateien (`index.html` + `manifest.json`) auf einen statischen Host laden:
   - **GitHub Pages** (kostenlos): Repo erstellen → Files hochladen → Pages aktivieren
   - **Netlify Drop** (kostenlos): `netlify.com/drop` → Ordner reinziehen
   - **Cloudflare Pages** (kostenlos)
2. URL am Handy in Chrome öffnen
3. "App installieren"-Prompt erscheint automatisch → bestätigen
4. App startet im Standalone-Modus (ohne Browser-UI)

## 📋 Trainingsplan (4er Upper/Lower)

| Tag | Workout | Fokus |
|-----|---------|-------|
| Mo  | Upper A | Push (Bank, Klimmzug, Shoulder Press) |
| Di  | Lower A | Quads (Kniebeugen, RDL, Beinpresse) |
| Do  | Upper B | Pull (Schrägbank, Rudern, Lat-Pulldown) |
| Fr  | Lower B | Posterior (Kreuzheben, Hip Thrust, BSS) |

Jedes Workout: 6 Übungen, 45–60 Min, RPE 7–9, 10–20 Sätze/Muskel/Woche.

## 🍽 Ernährungsziele

- **3300 kcal/Tag** (Trainingstag) / **3000 kcal** (Ruhetag)
- **170g Protein** (2.0 g/kg)
- **80g Fett** (0.95 g/kg)
- **475g Kohlenhydrate**
- 5 Mahlzeiten/Tag (inkl. Pre-Workout)
- 7-Tage-Beispielplan in der App

## ⚖ Wiegung & Anpassung

- **1× pro Woche**, gleicher Tag/Zeit (empfohlen: Samstag morgens nüchtern)
- Ziel: **+200–350g/Woche** (Hardgainer-konservativ, minimiert Fettzunahme)
- **Anpassungs-Regel:**
  - 2 Wochen kein Anstieg → **+150 kcal/Tag** (über zusätzliche KH/Fett)
  - Zunahme >500g/Woche → 200 kcal reduzieren
  - Bauchumfang zusätzlich messen (alle 2 Wochen)

## 🔄 Progressive Overload

**Double Progression:**
1. Hit obere Wiederholungszahl im Zielbereich bei allen Sätzen (z.B. 8 von 6–8)
2. Beim nächsten Mal: **+2.5kg** (Compound) bzw. **+1–2.5kg** (Isolation)
3. Reps fallen wieder in untere Range → wiederholen

## 🔁 Deload

Alle **6–8 Wochen** eine Deload-Woche:
- Sätze auf 60% reduzieren (z.B. 4×8 → 2×8)
- Gewicht auf ~80% behalten
- Keine Sätze bis zum Versagen

## 📊 Features der App

- ✅ Trainings-Tracking pro Satz (Gewicht + Wdh)
- ✅ Letzte Leistung als Referenz sichtbar
- ✅ Pausen-Timer mit visuellem Balken + Beep + Vibration
- ✅ Notizen pro Übung (erscheinen nächste Woche automatisch)
- ✅ Training abbrechen oder abschließen
- ✅ Einstellungen (Ton an/aus, Lautstärke)
- ✅ Wöchentliches Gewichts-Logging mit Verlaufs-Diagramm
- ✅ Kalorien-/Makro-Tracking mit 45+ Lebensmitteln
- ✅ **Profil + automatische Kalorien/Makros** (Mifflin-St Jeor, frei konfigurierbar in ⚙)
- ✅ **Mahlzeiten-Gruppen** (z.B. „Frühstück" als Bündel speichern & per Tap hinzufügen)
- ✅ **Mehrere Trainingspläne** + Import/Export + Wechsel (siehe PLAN-FORMAT.md)
- ✅ **Barcode-Scanner** (Open Food Facts Datenbank)
- ✅ Volumen-Progression pro Woche (Balkendiagramm)
- ✅ e1RM-Verlauf pro Übung (Epley-Formel)
- ✅ Persönliche Bestleistungen automatisch
- ✅ Daten-Export/Import als JSON
- ✅ Offline-fähig (Service Worker)
- ✅ localStorage-Persistenz

## 👤 Profil & Pläne (ab dieser Version)

- **Profil** unter ⚙ Einstellungen: Name, Geschlecht, Alter, Größe, Gewicht, Aktivität, Ziel → Kalorien & Makros werden automatisch berechnet. Damit ist die App für jede Person nutzbar.
- **Trainingspläne**: Unter ⚙ → „Pläne verwalten" kannst du Pläne importieren, exportieren und zwischen ihnen wechseln. Den Standard-Plan kann man nicht löschen.
- **KI-generierte Pläne**: Mit `PLAN-FORMAT.md` lässt du dir von jeder KI einen Plan im passenden Format erstellen und importierst ihn.
- Deine Trainings-Historie bleibt bei allen Änderungen erhalten.

## 📷 Barcode-Scanner

- Nutzt die kostenlose, offene **Open Food Facts**-Datenbank (gute DE/AT-Abdeckung)
- **WICHTIG:** Funktioniert nur über **HTTPS-Hosting** (Netlify/GitHub Pages) — Android blockiert den Kamerazugriff aus lokal geöffneten Dateien
- Gescannte Produkte werden lokal gespeichert und sind später auch über die Suche (📷-Symbol) auffindbar
- Produkt nicht gefunden? → manuelle Eingabe wird angeboten, danach dauerhaft gespeichert
- Falsch gescannte Produkte: in der Suchliste über das ×-Symbol löschbar
- **Hinweis:** Open Food Facts ist community-gepflegt — nicht jedes Produkt ist drin oder hat vollständige Nährwerte. Im Zweifel Werte gegenprüfen.

## 💾 Backup

**Wichtig:** Nutze regelmäßig den **Export-Button** (Progress → Daten → Export).
Die JSON-Datei enthält alle deine Daten. Bei Browser-Cache-Reset wären die sonst weg.

## 🎯 Erwartete Fortschritte (37J, Mid-Advanced)

- **Muskelaufbau:** 1.5–3 kg fettfreie Masse in 6 Monaten (realistisch für deinen Trainingsstand)
- **Kraft:** +10–20% bei Compound-Lifts in 12 Wochen
- **Bauchumfang:** sollte nicht mehr als 2–3 cm zunehmen (sonst Kalorien anpassen)

## ⚠️ Hinweise & Unsicherheiten

- **Kalorienberechnung** basiert auf Mifflin-St Jeor + Aktivitätsfaktor 1.6. Individueller Stoffwechsel kann ±200 kcal abweichen → nach 2 Wochen Praxis anpassen
- **Lebensmittel-DB** sind Standardwerte, einzelne Marken können abweichen
- **Diese App ersetzt keinen Trainer oder Ernährungsberater.** Bei Unsicherheit zur Form ein Video machen oder einen Coach konsultieren
- Vor Trainingsbeginn 5–10 Min Aufwärmen (Cardio + dynamic stretches + Aufwärmsätze)

Viel Erfolg beim Aufbauen 💪
