# 🇵🇱🌍 Multi-Sprachen Lern-App (Polnisch Pro)

Eine serverlose, datenschutzfreundliche **Single-File KI-Sprachlern-App** auf Basis von HTML5, CSS3 und Vanilla JavaScript. Speziell zugeschnitten auf das Lernen der **polnischen Sprache** (inkl. 7-Fälle-Detektiv, Verbaspekt-Vergleich & 3-Zeiten-Verb-Konjugator), aber ebenso flexibel nutzbar für **Englisch (UK/US), Swahili, Italienisch, Rumänisch, Spanisch und Französisch**.

---

## ✨ Hauptfunktionen

### 📖 KI-Lektionen & Interaktives Training
* **Individuelle Texte & Dialoge:** Generiert Lesetexte oder Dialoge zwischen zwei Personen auf den GER-Niveaus **A1, A2, B1 und B2** in wählbarer Länge.
* **Alltags-Szenario-Chips:** Schnellstart-Buttons für typische Situationen (z. B. *Zapiekanka & Pierogi*, *PKP-Fahrkarte*, *Apotheke*, *Basar*, *Amt/Urząd*) plus Zufallsgenerator.
* **Interaktive Übungen:**
  * Automatisch generiertes **Lückentext-Quiz** mit Sofort-Auswertung.
  * **Verständnisfragen & freie Schreibübung** mit direkter **KI-Korrektur** (Rechtschreibung, Grammatik & Verbesserungsvorschläge).
  * **Musterlösungen** inklusive deutscher Lautschrift.

### 🔄 Verb-Konjugator (Vergangenheit • Gegenwart • Zukunft)
* **Alle 6 Personen auf einen Blick:** Konjugiert Verben übersichtlich für *ja, ty, on/ona/ono, my, wy, oni/one* über **Vergangenheit, Gegenwart und Zukunft** (im Polnischen inkl. m./w.-Endungen und Aspekt-Hinweisen).
* **Doppelter Modus:** Zeigt automatisch ein zentrales Verb aus der aktuellen Lektion an und bietet zusätzlich ein **freies Suchfeld**, um jederzeit beliebige polnische oder deutsche Verben direkt nachzuschlagen.
* **Klick-Audio:** Jede einzelne konjugierte Form in der Tabelle lässt sich per Klick anhören.

### 🇵🇱 Polnisch-Spezial & Grammatik-Coach
* **7-Fälle-Detektiv (Kasus-Analyse):** Analysiert Schlüsselsätze aus dem Text, markiert die 7 polnischen Fälle farblich (*Nominativ bis Vokativ*), zeigt das polnische Fragewort (*Kogo? Czego?* etc.) und erklärt die genaue Grammatik-Regel dahinter.
* **Kasus-Endungs-Trainer:** Interaktive Übungen zum Einsetzen der richtigen Fall-Endung.
* **Verbaspekt-Vergleich:** Gegenüberstellung von **unvollendeten (*niedokonany*)** und **vollendeten (*dokonany*)** Verben samt hörbaren Beispielsätzen.
* **Grammatik-Coach:** Erklärt die passende Grammatikregel zum gewählten Niveau, warnt vor typischen Stolperfallen für Deutschsprachige und liefert 2 interaktive Umformungs-Drills.

### 🔊 Multi-Engine Audio & Aussprache
* **Einzelsatz- & Volltext-Wiedergabe:** Klicke auf einen einzelnen Satz, auf Beispielsätze oder auf die gesamte Lektion, um sie vorlesen zu lassen (inkl. Tempo- und Tonhöhen-Regler).
* **3 Audio-Stufen wählbar:**
  1. **Browser-Stimme** (kostenlos / 0 Tokens).
  2. **Google Cloud Text-to-Speech** (WaveNet & Neural2 HD-Stimmen).
  3. **ElevenLabs Multilingual v2** (natürliche HD-Stimmen, ideal auch für Polnisch und Swahili).

### ⭐ Vokabel-Merkliste, Karteikarten & Anki-Export
* Speichert ausgewählte Vokabeln inkl. deutscher Lautschrift lokal im Browser.
* **Interaktiver Karteikarten-Modus** zum Umdrehen und Anhören.
* **Anki-kompatibler CSV-Export & Import** (Tab-getrennt inkl. HTML-Formatierung und Sprach-Tags).

### 📊 Kosten-Transparenz & Verbindungs-Ampel
* **Verbindungs-Ampel:** Prüft auf Knopfdruck den Status von Gemini API, Google Cloud TTS, ElevenLabs und Browser-Audio.
* **Live-Modellauswahl & Token-Rechner:** Zeigt nach jeder Anfrage das verwendete KI-Modell, die verbrauchten Input/Output-Tokens sowie die geschätzten Kosten in US-Cent an.

---

## 🚀 Installation & Nutzung

Da die App komplett ohne Build-Tools oder Backend auskommt, gibt es zwei einfache Wege zur Nutzung:

1. **Lokal im Browser:**
   * Lade die Datei `index.html` herunter und öffne sie per Doppelklick in einem modernen Browser (Chrome, Edge, Safari, Firefox).
2. **Eigene Web-App über GitHub Pages:**
   * Aktiviere in den Repository-Einstellungen unter **Settings → Pages** den Branch `main` (`/root`).
   * Öffne den erzeugten `github.io`-Link auf dem PC oder Smartphone (über *„Zum Startbildschirm hinzufügen“* erscheint die App inkl. weiß-rotem **PL**-Icon).

### Benötigte API-Schlüssel
* **Pflicht:** Ein **Google Gemini API-Schlüssel** (erhältlich über [Google AI Studio](https://google.com)).
* **Optional:** Eigener **Google Cloud TTS Key** und/oder **ElevenLabs API Key** für HD-Stimmen.

---

## 🔒 Datenschutz & Sicherheit

* **100 % Client-Side:** Es gibt keinen eigenen Server, keine Datenbank und kein Tracking.
* **Lokale Speicherung:** Alle eingegebenen API-Schlüssel und gemerkten Vokabeln werden ausschließlich im `localStorage` deines eigenen Browsers gespeichert und verlassen dein Gerät nur direkt an die jeweiligen offiziellen API-Schnittstellen.

### 🔍 Code-Transparenz & Sicherheits-Check (Selbst prüfen)

Da die gesamte App aus einer einzigen, unverschlüsselten HTML-Datei (`index.html`) besteht, lässt sich der Umgang mit den eigenen API-Schlüsseln jederzeit direkt im Quelltext überprüfen:

1. **Lokale Speicherung (`localStorage`):**
   * Suche im Code nach `localStorage.setItem` und `localStorage.getItem` (in **Modul 5** und **Modul 6**).
   * Dort wird ersichtlich, dass die Schlüssel (`polnisch_app_key`, `google_tts_key`, `elevenlabs_app_key`) ausschließlich im lokalen Speicher des eigenen Browsers abgelegt und über **Löschen** (`localStorage.removeItem`) wieder restlos entfernt werden.
2. **Direkte API-Kommunikation (`fetch`):**
   * Suche im Code nach `fetch(` (in **Modul 5, 6 und 7**).
   * Sämtliche Netzwerkanfragen gehen direkt vom Browser an die offiziellen Hersteller-Endpunkte:
     * `https://googleapis.com` (Google Gemini)
     * `https://googleapis.com` (Google Cloud Text-to-Speech)
     * `https://elevenlabs.io` (ElevenLabs TTS)
   * Es existieren keinerlei Drittanbieter-Server, Analytics-Skripte oder externe Bibliotheken.

---

## 🧩 Code-Architektur (12-Module-Blueprint)

Die App ist in **12 klar getrennte HTML/CSS/JS-Module** unterteilt, um Wartung und KI-gestützte Erweiterungen ohne Token-Limits zu ermöglichen:

1. **Modul 1:** HTML-Grundgerüst & CSS-Design (inkl. Kasus-Farbschema).
2. **Modul 2:** Einstellungs-UI (API-Key, Modellwahl, Sprache, Stimme, Tempo & Modus).
3. **Modul 3:** Lese-, Audio-, Vokabel-, KI-Korrektur- & Lückentext-UI.
4. **Modul 4:** Grammatik-Drill, Karteikarten & CSV-Import/-Export-UI.
5. **Modul 5:** Polnisch-Kasus-Referenz & Deklinations-Nachschlagewerk (HTML).
6. **Modul 6:** JavaScript-Basisdaten, Kasus-Tabellen & Sprachumschaltung.
7. **Modul 7:** JavaScript-Audio-Engine (Web Speech API) & interaktive Wort-Klicks.
8. **Modul 8:** JavaScript-Deklinations-Suche & Gemini-API-Client mit Kostenrechner.
9. **Modul 9:** JavaScript-Prompt-Builder (inkl. Kasus-Markierungen) & Text-Renderer.
10. **Modul 10:** JavaScript-Lückentext-Generator & Satz-Drill-Builder.
11. **Modul 11:** JavaScript-Übungs-Checks, KI-Korrektur, Karteikarten & CSV-Sync.
12. **Modul 12 (12A + 12B):** Aufklappbarer Offline-Trainer für Zahlen, Uhrzeiten, Daten & Preise.

---

## 📄 Lizenz

Dieses Projekt steht zur freien persönlichen Nutzung, Anpassung und Weiterentwicklung zur Verfügung.
