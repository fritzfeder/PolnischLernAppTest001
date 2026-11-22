# 🇵🇱 Polnisch Lern-App (Lesetrainer)

Eine schlanke, kostenlose Web-App zum Polnischlernen (Sprachniveau **A1 bis B2**), die vollständig im Browser läuft – ohne Backend, ohne Serverkosten und ohne fest hinterlegte API-Schlüssel.

## ✨ Funktionen

* **Individuelle Texte & Dialoge:** Generiert zu jedem beliebigen Thema einen natürlichen polnischen Text (5–8 Sätze) passend zum gewählten GER-Sprachniveau (`A1`, `A2`, `B1`, `B2`).
* **Vorlesefunktion (Audio):** Liest den polnischen Text über die eingebaute Sprachausgabe des Browsers (`pl-PL`) vor.
* **Deutsche Übersetzung:** Aufklappbar zur direkten Selbstkontrolle.
* **Wichtige Redewendungen & Vokabeln:** 5–6 zentrale Begriffe aus dem Text inklusive einfacher deutscher Lautschrift.
* **Verständnisfragen & Lösungen:** 5 Fragen auf Polnisch (mit deutscher Übersetzung) sowie aufklappbare Musterantworten mit Lautschrift.

---

## 🔐 Sicherheit & API-Schlüssel

Diese App nutzt die **Google Gemini API** (kostenloser Tarif / Free Tier):
* **Kein Schlüssel im Quellcode:** Der API-Key wird niemals auf GitHub gespeichert.
* **Lokale Speicherung:** In der HTML-Version (`index.html`) wird der Schlüssel ausschließlich im `localStorage` des eigenen Browsers gesichert und kann dort jederzeit wieder gelöscht werden.
* **Unterstützte Schlüssel-Formate:** Kompatibel mit den aktuellen `AQ.`-Schlüsseln aus dem [Google AI Studio](https://google.com) sowie älteren `AIza`-Keys.
* **Auto-Fallback:** Wechselt bei Server-Auslastung automatisch zwischen den Modellen `gemini-3.5-flash-lite`, `gemini-4-hydrogen` und `gemini-3.8-flash`.

---

## 📂 Enthaltene Versionen

1. **`index.html` (Hauptversion für GitHub Pages):** Reine HTML/CSS/JavaScript-Datei. Lädt sofort, speichert den API-Key lokal im Browser und bietet eine polnische Vorlesefunktion.
2. **`app.py` (Optionale Stlite-Version):** Python/Streamlit-Variante für den Betrieb in Stlite (WebAssembly im Browser).

---

## 📋 Blueprint-Prompt (für spätere KI-Erweiterungen)

Falls die App künftig um neue Funktionen erweitert werden soll, diesen Prompt als Arbeitsgrundlage verwenden:

> Du bist ein erfahrener Webentwickler. Wir entwickeln eine reine Client-Side Polnisch-Lern-App als einzelne `index.html`-Datei für GitHub Pages (ohne Backend, ohne Frameworks, ohne Build-Tools).
>
> Halte dich strikt an diese bereits erfolgreich getestete Architektur und alle technischen Sicherheitsregeln:
> 1. **Hosting & Code-Ausgabe:** Gesamter Code (HTML, CSS, Vanilla JS) befindet sich kompakt in einer einzigen `index.html`-Datei. Code-Blöcke müssen kompakt gehalten werden, damit sie beim Kopieren nicht abgeschnitten werden und stets mit `</html>` enden. JavaScript-Arrays ohne eckige Klammern auslesen (z. B. mit `.at(0)`).
> 2. **API-Key-Sicherheit (`localStorage`):** Der Google Gemini API-Key steht niemals im Quellcode. Eingabe über ein Passwort-Feld in einem einklappbaren `<details>`-Panel, lokale Speicherung unter `localStorage.getItem('polnisch_app_key')` sowie Lösch-Button. Akzeptierte Key-Präfixe: `AQ.` und `AIza`.
> 3. **API-Anbindung & Auto-Fallback:** Authentifizierung ausschließlich über den HTTP-Header `'x-goog-api-key': apiKey`. Host-URL im JS aus Einzelteilen zusammensetzen: `["https://", "generativelanguage", ".", "googleapis", ".", "com"].join("")`. Automatische Ausweich-Schleife über gültige Modelle: `["gemini-3.5-flash-lite", "gemini-4-hydrogen", "gemini-3.8-flash"]`. Strukturierte Antwort via `generationConfig: { responseMimeType: "application/json" }`.
> 4. **Aktuelle Lern-Funktionen:** Auswahl GER-Niveau (`A1`–`B2`), Themen-Eingabe mit Schnellwahl-Chips, polnischer Text (5–8 Sätze), Audio-Vorlesen (`pl-PL`), aufklappbare deutsche Übersetzung, 5–6 Vokabeln mit Lautschrift, 5 Verständnisfragen (Polnisch + Deutsch) und aufklappbare Lösungen mit Lautschrift.
