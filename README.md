# 🌍 Multi-Sprachen Lern-App (Lesetrainer & Dialog-Coach)

Eine kostenlose, eigenständige Web-App zum Sprachenlernen (Sprachniveau **A1 bis B2**), die vollständig im Browser läuft – ohne Backend, ohne Serverkosten und ohne fest hinterlegte API-Schlüssel.

## ✨ Funktionen

* **8 Sprachen zur Auswahl:** Polnisch, Britisch Englisch, US-Englisch, Swahili, Italienisch, Rumänisch, Spanisch und Französisch.
* **Flexible Texte & Dialoge:** Wahl zwischen **Lesetext** (Erzählung) und **Dialog-Trainer** (Gespräch zwischen zwei Personen) in drei Längen (**3–4**, **5–8** oder **10–15 Sätze**) auf den GER-Niveaus `A1` bis `B2`.
* **Anpassbare Vorlesefunktion (Audio):** Liest Texte in der jeweiligen Landessprache vor – mit stufenlosen Reglern für **Sprechtempo** (`0.5x`–`1.3x`) und **Tonhöhe**.
* **Grammatik-Fokus:** Passende Grammatik-Erklärung zum gewählten Sprachniveau inklusive Beispielen aus dem aktuellen Text.
* **Vokabeln & Lautschrift:** 5–6 zentrale Ausdrücke aus dem Text mit einfacher deutscher Lautschrift und Merk-Button.
* **Interaktives Lückentext-Quiz:** 4 Übungssätze direkt zum Ausfüllen mit sofortiger Richtig/Falsch-Auswertung.
* **Verständnisfragen & Lösungen:** 5 Fragen in der Fremdsprache (mit deutscher Übersetzung) sowie aufklappbare Musterantworten inklusive Lautschrift.
* **Vokabel-Merkliste mit Anki-Export:** Speichert gemerkte Wörter lokal im Browser. Exportiert gezielt die jeweils ausgewählte Sprache als Anki-kompatible Datei (z. B. `anki-polnisch.csv`) und ermöglicht den Rück-Import auf anderen Geräten (PC / iPad).

---

## 🔐 Sicherheit & API-Schlüssel

Diese App nutzt die **Google Gemini API** (kostenloser Tarif / Free Tier):
* **Kein Schlüssel im Quellcode:** Der API-Key wird niemals auf GitHub gespeichert.
* **Lokale Speicherung:** Der Schlüssel wird ausschließlich im `localStorage` des eigenen Browsers gesichert (`polnisch_app_key`) und kann jederzeit gelöscht werden.
* **Unterstützte Schlüssel-Formate:** Kompatibel mit aktuellen `AQ.`-Schlüsseln aus dem [Google AI Studio](https://google.com) sowie `AIza`-Keys.
* **Auto-Fallback:** Wechselt bei Server-Auslastung automatisch zwischen `gemini-3.5-flash-lite`, `gemini-4-hydrogen` und `gemini-3.8-flash`.

---

## 📋 Aktueller Blueprint-Prompt (für spätere KI-Erweiterungen)

Falls die App künftig um weitere Funktionen ergänzt werden soll, diesen Prompt als Arbeitsgrundlage verwenden:

> Du bist ein erfahrener Webentwickler. Wir entwickeln eine reine Client-Side Multi-Sprachen-Lern-App als einzelne `index.html`-Datei für GitHub Pages (ohne Backend, ohne Frameworks, ohne Build-Tools).
>
> Halte dich strikt an diese bereits erfolgreich getestete Architektur und alle technischen Sicherheitsregeln:
> 1. **Hosting & Code-Ausgabe:** Gesamter Code (HTML, CSS, Vanilla JS) befindet sich kompakt in einer einzigen `index.html`-Datei. Bei größeren Änderungen Code-Blöcke in handliche Teile aufteilen, damit beim Kopieren aus dem Chat nichts abgeschnitten wird und der letzte Block stets mit `</html>` endet. JavaScript-Arrays ohne eckige Klammern auslesen (z. B. mit `.at(0)`).
> 2. **API-Key-Sicherheit (`localStorage`):** Der Google Gemini API-Key steht niemals im Quellcode. Eingabe über ein Passwort-Feld in einem einklappbaren `<details>`-Panel, lokale Speicherung unter `localStorage.getItem('polnisch_app_key')` sowie Lösch-Button. Akzeptierte Key-Präfixe: `AQ.` und `AIza`.
> 3. **API-Anbindung & Auto-Fallback:** Authentifizierung ausschließlich über den HTTP-Header `'x-goog-api-key': apiKey`. Host-URL im JS aus Einzelteilen zusammensetzen: `["https://", "generativelanguage", ".", "googleapis", ".", "com"].join("")`. Automatische Ausweich-Schleife über gültige Modelle: `["gemini-3.5-flash-lite", "gemini-4-hydrogen", "gemini-3.8-flash"]`. Strukturierte Antwort via `generationConfig: { responseMimeType: "application/json" }`.
> 4. **Implementierte Lern-Funktionen:**
>    - Sprachauswahl (`Polnisch`, `Britisches Englisch`, `US-Englisch`, `Swahili`, `Italienisch`, `Rumänisch`, `Spanisch`, `Französisch`) inklusive Sprachcode für TTS.
>    - Auswahl GER-Niveau (`A1`–`B2`), Textlänge (`3–4`, `5–8`, `10–15` Sätze), Textart (`Lesetext` oder `Dialog-Trainer`) und Themen-Eingabe mit Schnellwahl-Chips.
>    - Audio-Vorlesen (`window.speechSynthesis`) mit Reglern für Tempo und Tonhöhe.
>    - Aufklappbare deutsche Übersetzung, Grammatik-Fokus-Box, 5–6 Vokabeln mit Lautschrift, interaktives Lückentext-Quiz (4 Lücken mit Auswertung), 5 Verständnisfragen und aufklappbare Lösungen mit Lautschrift.
>    - Lokale Vokabel-Merkliste (`localStorage` unter `lang_memo`) mit sprachspezifischem Anki-Tab-CSV-Export (`anki-<sprache>.csv` mit `#separator:tab`, `#html:true`, `#tags column:3`) und CSV-Import.
