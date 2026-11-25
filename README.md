# 🌍 Multi-Sprachen Lern-App (Polnisch Pro Edition)

Eine schlanke, serverlose **Single-File Web-App** (`index.html`) zum interaktiven Sprachenlernen mit **Google Gemini** (`gemini-3.8-flash` / `gemini-3.5-flash-lite`) sowie optionalen HD-Stimmen über **Google Cloud Text-to-Speech** und **ElevenLabs**.

Die App läuft vollständig lokal im Browser – ohne Backend, ohne Build-Prozess und ohne Abonnement. Sie ist speziell auf **Polnisch** optimiert, unterstützt aber ebenso **Britisches Englisch, US-Englisch, Swahili, Italienisch, Rumänisch, Spanisch und Französisch** auf den GER-Niveaus **A1 bis B2**.

---

## ✨ Hauptfunktionen

### 🇵🇱 Polnisch-Spezial (Pro-Features)
* **7-Fälle-Detektiv (Kasus-Trainer):** Zerlegt Schlüsselsätze aus der aktuellen Lektion, markiert Substantive und Pronomen **farblich nach ihrem Fall** (Nominativ bis Vokativ), nennt das polnische Kontroll-Fragewort (*Kogo? Czego? / Z kim? Z czym?*) und erklärt den grammatikalischen Grund.
* **Interaktiver Kasus-Endungs-Trainer:** Lückentext-Übungen speziell zum Deklinieren mit direkter Prüfung und Lösungsanzeige.
* **Verbaspekt-Vergleich (*Niedokonany vs. Dokonany*):** Gegenüberstellung unvollendeter und vollendeter Verben aus der Lektion – inklusive deutscher Bedeutung und klickbaren, hörbaren Beispielsätzen für beide Aspekte.
* **Polnische Alltags-Szenarien & Zufallsgenerator:** Schnellwahl-Chips für typische Situationen (*🥟 Zapiekanka & Pierogi*, *🚆 PKP-Fahrkarte*, *💊 Apotheke & Arzt*, *🍎 Auf dem Basar*, *🏛️ Amt / Urząd*, *🎲 Zufallsthema*).

### 📖 Lektions- & Grammatik-Engine
* **Lesetexte & Dialog-Trainer:** Frei wählbare Themen, Textlängen (kurz, mittel, lang) und Sprachniveaus (**A1, A2, B1, B2**).
* **Interaktiver Grammatik-Coach:** Passende Regel-Erklärung zum Niveau, Übersichtstabelle, **Stolperfallen-Warnung** im Vergleich zur deutschen Grammatik, hörbare Beispielsätze und ein 2-teiliger Umformungs-Drill.
* **Übungen & KI-Schreibkorrektur:**
  * Interaktives **Lückentext-Quiz**
  * **Verständnisfragen** mit eigener Texteingabe und direkter **KI-Korrektur** durch deinen polnischen/fremdsprachigen KI-Tutor
  * Musterlösungen inklusive **einfacher deutscher Lautschrift**
* **Transparenz & Kostenkontrolle:** Anzeige des genutzten KI-Modells, des genauen Token-Verbrauchs (Input/Output) und der geschätzten Kosten in US-Cent pro Abruf.

### 🔊 Audio & Vorlesefunktion (3 Stufen)
* **Satz-für-Satz-Klick:** Jeden Satz im Text oder in den Grammatik-Tabellen einzeln anklicken und anhören.
* **Stufenloses Tempo & Tonhöhe:** Regler für Sprechgeschwindigkeit (`0.5x` bis `1.3x`) und Stimmlage.
* **Flexible Audio-Quellen:**
  1. **Browser-Stimmen** (Standard, komplett kostenlos / 0 Tokens)
  2. **Google Cloud Text-to-Speech** (`Wavenet` / `Neural2` HD-Stimmen, z. B. `pl-PL-Wavenet-A/B`)
  3. **ElevenLabs** (`eleven_multilingual_v2` HD-Stimmen, inkl. Unterstützung für Sprachen wie Swahili)

### ⭐ Vokabel-Merkliste, Karteikarten & Anki-Export
* Vokabeln samt Lautschrift mit einem Klick lokal im Browser (`localStorage`) speichern.
* Integrierter **Karteikarten-Modus** zum Umdrehen und Vorlesen lassen.
* **Anki-kompatibler `.csv`-Export & Import** (tab-getrennt, nach Sprache gefiltert).

---

## 🚀 Installation & Nutzung

1. Lade die Datei `index.html` aus diesem Repository herunter (oder klone das Repository).
2. Öffne die `index.html` per Doppelklick in einem modernen Browser (Chrome, Edge, Firefox, Safari) – oder hoste sie kostenlos über **GitHub Pages**.
3. Öffne oben das Panel **🔐 API-Schlüssel & Verbindungs-Ampel**:
   * Trage deinen **Google Gemini API-Schlüssel** ein (Pflichtfeld, erhältlich im [Google AI Studio](https://google.com)).
   * *Optional:* Hinterlege einen **Google Cloud TTS-Key** oder **ElevenLabs API-Key** für noch natürlichere HD-Stimmen.
   * Klicke auf **Speichern** und prüfe den Status über **🚦 Verbindung & Ampel prüfen**.
4. Wähle Sprache, Niveau und Thema aus und klicke auf **Lektion erstellen**.

---

## 🧩 Modulare Code-Struktur (8 Blöcke)

Die `index.html` ist intern durch klare HTML-Kommentare in **8 eigenständige Module** gegliedert, sodass einzelne Funktionen gezielt gewartet oder erweitert werden können:

| Modul | Bereich | Inhalt |
| :--- | :--- | :--- |
| **Modul 1** | `HEAD & CSS` | Layout, Responsive Design, Karten-Optik & Kasus-Farbcodes |
| **Modul 2** | `HTML SETTINGS & SETUP` | API-Schlüssel-Verwaltung, Verbindungs-Ampel & Lektions-Auswahl |
| **Modul 3** | `HTML LESSON & MEMO` | Text-Box, Audio-Leiste, Grammatik-Coach, Polnisch-Spezial & Merkliste |
| **Modul 4** | `JS CONFIG & AMPEL` | Initialisierung, dynamische Szenario-Chips & API-Statusprüfung |
| **Modul 5** | `JS MODELS & AUDIO` | Modell-Abruf, Stimmen-Auswahl, Google Cloud TTS & ElevenLabs Player |
| **Modul 6** | `JS GEMINI & GENERATOR` | Token-/Kostenrechner, Gemini API-Client & Lektions-Prompt |
| **Modul 7** | `JS RENDERER` | Darstellung von Text, Grammatik, 7-Fälle-Analyse & Verbaspekten |
| **Modul 8** | `JS EXERCISES & MEMO` | Übungs-Checks, KI-Korrektur, Karteikarten & CSV-Import/Export |

---

## 🔒 Datenschutz & Sicherheit

* **100 % Client-Side:** Es gibt keinen Zwischenserver. Deine API-Schlüssel und deine Vokabel-Merkliste werden ausschließlich lokal im `localStorage` deines eigenen Browsers gespeichert.
* Direkte Kommunikation erfolgt nur zwischen deinem Browser und den offiziellen API-Endpunkten von Google (`://googleapis.com`, `://googleapis.com`) bzw. ElevenLabs (`api.elevenlabs.io`).

---

## 📝 Changelog (Versionshistorie)

### v2.2 – Polnisch Pro & Modulare Architektur
* **Neu:** **7-Fälle-Detektiv (Kasus-Trainer)** mit Farbcodes, polnischen Kontrollfragen und interaktivem Kasus-Endungs-Trainer.
* **Neu:** **Verbaspekt-Vergleich** (*Niedokonany vs. Dokonany*) mit klickbaren Beispielsätzen für beide Aspekte.
* **Neu:** **Polnische Alltags-Szenarien** (*Bar Mleczny, PKP, Apteka, Basar, Urząd*) inklusive **Zufallsthema-Generator**.
* **Neu:** Integriertes **SVG-Favicon & Smartphone-Homescreen-Icon** (Weiß-Rot mit `PL`-Badge) sowie Gliederung in **8 wartbare Code-Module**.

### v2.1 – Grammatik-Coach & Audio-Upgrade
* **Neu:** Einklappbarer **Grammatik-Coach** mit Regel-Tabelle, Stolperfallen-Box, hörbaren Beispielsätzen und Umformungs-Drill.
* **Neu:** **Verbindungs-Ampel** für Gemini API, Google Cloud TTS und ElevenLabs sowie automatische Fallbacks auf Browser-Stimmen.
* **Neu:** Token- und geschätzte US-Cent-Kostenanzeige pro Lektion und Schreibkorrektur.

### v2.0 – Multi-Sprachen & Anki-Workflow
* **Neu:** Unterstützung für 8 Sprachen (Polnisch, UK/US-Englisch, Swahili, Italienisch, Rumänisch, Spanisch, Französisch) auf Niveau A1–B2.
* **Neu:** KI-Schreibkorrektur für eigene Antworten, Karteikarten-Modus und tab-getrennter `.csv`-Import/Export für Anki.

### v1.0 – Erstveröffentlichung
* Serverlose Single-File Web-App für Polnisch-Lesetexte, Lückentext-Quiz, Vokabel-Merkliste und Browser-Sprachausgabe.

---

## 📄 Lizenz

Dieses Projekt steht zur freien persönlichen Nutzung und Weiterentwicklung zur Verfügung.
