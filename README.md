# b&p Metalltechnik – Karriereseite

Recruiting-Landingpage / Ad-Funnel für die **b&p Metalltechnik GmbH** (Lennestadt).
Offene Stellen (m/w/d):
1. **Zerspanungsmechaniker – CNC-Fräsen** (3- & 5-Achs, Heidenhain)
2. **Zerspanungsmechaniker – Drehtechnik** (Drehen & Fräsen, Sägen/Schleifen, Siemens)
3. **Elektroniker – SPS-Steuerung**

Aufbau 1:1 an der ALWA-Karriereseite orientiert – in eigenem b&p-CI, mit den
oben genannten Positionen und angebunden an die LeadTable-Kachel von b&p.

## Inhalt

- `index.html` – die komplette Seite (self-contained, keine Build-Schritte nötig)
- `supabase-bewerbungen.sql` – legt den Storage-Bucket für den optionalen Lebenslauf-Upload an
- `.nojekyll` – sorgt dafür, dass GitHub Pages die Dateien 1:1 ausliefert
- `bilder/` – Hero-Fotos & Logo (siehe unten) – **hier bitte das Bildmaterial ablegen**
- `creatives/` – Meta-Ads: Creatives + Werbetexte (folgen in Schritt 2, siehe Ordner)

## ⚠️ Noch zu bestätigen / einzupflegen

Diese Punkte sind mit sinnvollen Platzhaltern belegt und sollten mit den echten
Daten von b&p abgeglichen werden:

1. **CI-Farben** – ✅ **direkt aus dem gelieferten Logo abgeleitet**:
   b&p-Blau (`--brand:#0066b1`), Anthrazit (`--brand-900:#20242b`, wie das
   Logo-Negativ) und ein heller Blau-Akzent (`--accent:#1498d6`). Alles liegt
   in den `:root`-Variablen ganz oben im `<style>`-Block – bei Bedarf dort
   feinjustieren. Schrift ist „Barlow / Barlow Semi Condensed“ (technisch,
   passend zur Logo-Anmutung) – falls b&p eine feste Hausschrift hat, dort
   `--f-display`/`--f-body` tauschen.
2. **Logo** – ✅ **eingebunden**. Aus den gelieferten PDFs wurden web-taugliche
   Dateien erzeugt: `bilder/bp-logo.png` (farbig, transparent – Kopfzeile) und
   `bilder/bp-logo-weiss.png` (weiß, transparent – Hero & Footer). Die
   Original-PDFs bleiben als Quelle im Ordner; die „25 Jahre“-Jubiläumsversion
   (`Logo 25.pdf`) liegt ebenfalls bei, ist aber nicht aktiv eingebunden.
3. **Benefits** – die 6 Benefit-Kacheln sind ein fachlich passender Vorschlag
   für einen Zerspanungs-/Werkzeugbau-Betrieb (siehe Kommentar im Abschnitt
   `BENEFITS`). Bitte mit den tatsächlichen Benefits von b&p ersetzen.
4. **Vorfilter-Fragen** – ✅ eingebaut (siehe Abschnitt „Screening"): Position,
   Ausbildung, Deutsch (B2), Entfernung (Umkreis), Führerschein, CAD/CAM.
   **Bitte 1× bestätigen, welche davon hart aussteuern sollen.** Aktuell hart
   (kein Lead): keine abgeschlossene Ausbildung, Deutsch unter B2.
   Nur erfasst (kein Auto-Ausschluss): Entfernung, Führerschein, CAD/CAM –
   damit gute Leute nicht versehentlich rausfliegen (die 20-km-Filterung
   übernimmt zusätzlich das Meta-Targeting). Zum Verschärfen einfach den
   jeweiligen Antwort-Wert in `SCREEN_OUT` (in `index.html`) ergänzen.
5. **Kontaktdaten & Rechts-Links** – ✅ vom Kunden bestätigt: Telefon
   `02721 603140`, `info@bp-metall.de`, Impressum/Datenschutz auf
   `https://www.bp-metall.de/impressum/` bzw. `/datenschutz/`.

## Bilder (Hero-Fotos & Logo)

Die Fotos gehören in den Ordner **`bilder/`**. Der Hero lädt automatisch das
passende Bild – fehlt es, bleibt ein Farbverlauf stehen (kein kaputtes Bild).
Erwartete Dateinamen:

- `bilder/hero.jpg` – Hero-Bild (allgemein)

Logo (bereits eingebunden, ersetzt den Text-Schriftzug automatisch):

- `bilder/bp-logo.png` – farbiges Logo (Kopfzeile) ✅
- `bilder/bp-logo-weiss.png` – weißes Logo (Hero & Footer, dunkler Hintergrund) ✅
- Quelle: `bilder/BP_4_farbig_CMYK.pdf`, `BP_2_farbig_Weiss auf Schwarz.pdf`, `Logo 25.pdf`

Hero-Fotos: Querformat, mind. ~1600 px breit. Motiv rechts platzieren –
links liegt die Textfläche.

## Screening / Vorfilterung

Das Bewerbungsformular ist ein 7-Schritt-Funnel zur Vorfilterung – ausgelegt
auf **Bewerberqualität statt reiner Masse** (jede Auswahlfrage springt per
Ein-Klick weiter, dauert real ~1 Minute):

1. **Position** – CNC-Fräsen / Drehtechnik / Elektroniker SPS.
2. **Ausbildung** – passend / anderer Bereich / keine. **Keine Ausbildung →
   Aussteuerung** (kein Lead an LeadTable).
3. **Deutsch** – fließend / B2 / unter B2. **Unter B2 → Aussteuerung.**
4. **Entfernung (Umkreis)** – bis 20 km / 20–40 km / >40 km umzugsbereit / >40 km
   (nur erfasst, keine Aussteuerung).
5. **Führerschein** – Ja / Nein (nur erfasst).
6. **CAD/CAM** – sicher / Grundkenntnisse / noch keine (nur erfasst; ONE CNC
   wird angelernt).
7. **Kontaktdaten** + optionaler Lebenslauf-Upload.

Die Steuerung der Aussteuerung liegt in `index.html` in der Liste `SCREEN_OUT`
(einfach den exakten Antwort-Wert ergänzen, um ein Kriterium hart zu machen).

Screen-out und Erfolg gelten nur für den aktuellen Besuch – ein Seiten-Neuladen
startet frisch (kein dauerhaftes Sperren per localStorage).

## Live schalten (GitHub Pages)

1. Repo-Settings → **Pages** → Source: **Deploy from a branch**, Branch: `main` / `/root`
   (oder den gewünschten Branch).
2. Nach ein paar Minuten ist die Seite unter `https://<user>.github.io/<repo>/`
   erreichbar (bzw. unter der hinterlegten Custom-Domain, z. B. `bp-metall.de/karriere`).

## Bewerbungen (LeadTable)

Jede abgeschlossene Bewerbung wird per Webhook an LeadTable gesendet
(Felder u. a. `vorname`, `nachname`, `name`, `email`, `telefon`, `stelle`,
`ausbildung`, `deutsch`, `entfernung`, `fuehrerschein`, `cadcam`,
`lebenslauf`, `quelle`, `seite`).
Der Webhook ist in `index.html` in der Variable `WEBHOOK_URL` hinterlegt:

```
https://api-v2.lead-table.com/api/webhook/generic/…
```

Portal-Kachel (Leads einsehen):
`https://portal.lead-table.com/customer/6a9fbc8bd7eae5fa903160b4/table/6a9fbca556885b968028a7a2/leads`

## Lebenslauf-Upload (optional)

Der optionale Datei-Upload nutzt Supabase Storage (Bucket `bewerbungen`).
Er ist **standardmäßig deaktiviert** – die Bewerbung wird trotzdem gesendet
(Feld `lebenslauf` = „nicht hochgeladen“).

Zum Aktivieren:
1. Ein Supabase-Projekt anlegen, `supabase-bewerbungen.sql` einmalig im
   SQL-Editor ausführen.
2. In `index.html` `SUPABASE_URL` und `SUPABASE_KEY` (Publishable/anon Key) eintragen.

Danach landet im LeadTable-Feld `lebenslauf` ein direkt öffenbarer Link.
