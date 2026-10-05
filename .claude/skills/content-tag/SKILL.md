---
name: content-tag
description: LinkedIn Wochenproduktion Alperna (Aufgabe v1). Baut 4 Beiträge für Andrej und 4 für Leander als Nachbau viraler Vorlagen mit echtem Alperna-Rohstoff aus Notion, legt DOCX, Taplio-Entwürfe (nur Andrej) und Notion-Archivzeilen an und terminiert nichts. Auslösen mit /content-tag oder als Routine sonntags 18:00 Europe/Zurich. Braucht Taplio-MCP und Notion-MCP.
---

# LinkedIn Wochenproduktion Alperna, Aufgabe v1

Stand 5. Oktober 2026. Zum Einfügen als wiederkehrende Aufgabe (Vorschlag: sonntags 18:00 Europe/Zurich) oder als manueller Startbefehl "Content-Tag". Der Prompt ist absichtlich eigenständig: Bei Konflikt mit Regelwerk v3, Betriebssystem v1 oder Projektdateien gilt dieser Text.

## Parameter (hier ändern, nicht im Ablauf)

- ANZAHL_ANDREJ = 4
- ANZAHL_LEANDER = 4
- Zeitzone: Europe/Zurich
- Slots Andrej: Di 08:00, Mi 14:00, Do 08:00, Fr 14:00
- Slots Leander: Di 14:00, Mi 08:00, Do 14:00, Fr 08:00
- Zielwoche: die Woche nach dem Lauf (Datum jedes Slots ausrechnen und im Output nennen)
- Taplio-Konto = Andrej. Leander hat kein Taplio-Konto.

## Idee in einem Satz

Jeder Beitrag ist der Nachbau eines viralen Beitrags (Aufbau, Hook-Formel, Satzrhythmus, Anzahl Blöcke, Bildtyp fast eins zu eins) mit zu 100 Prozent echtem Alperna-Inhalt aus Notion. Struktur ja, fremde Sätze nie.

## Harte Regeln (gelten vor allem anderen)

1. Nie `publish_draft`. Nie `schedule_draft` ohne ausdrückliche Freigabe von Andrej im Chat, pro Beitrag. Dieser Lauf terminiert nichts.
2. Leanders Beiträge nie per `create_draft`, `update_draft` oder `schedule_draft` anlegen. Das Taplio-Konto ist Andrejs. Leanders Text ginge unter Andrejs Namen raus. Leander-Beiträge nur als Text (DOCX und Notion). Andrej plant sie manuell auf LinkedIn.
3. Kein Beitrag ohne Rohstoff. Jeder Beitrag braucht einen Eintrag im Notion-Rohstoff-Speicher. Ein Erlebnis ergibt einen Beitrag, nicht zwei. Fehlt Rohstoff für einen Slot, wird der Slot nicht beschrieben, sondern als Lücke gemeldet. Lieber 3 starke als 4 mit Lücke.
4. Nichts erfinden: keine Anekdoten, Zahlen, Namen, Zitate, Daten. Fehlt ein Detail, kommt eine Rückfrage, keine Ausschmückung.
5. Zwei Tests vor jedem Output:
   - Vorlagentest: Kann ich die Vorlage nennen (Autor, erste Zeile, Likes, Kommentare), und folgt der Beitrag ihrem Aufbau? Nein: neu bauen.
   - Substitutionstest: Könnte eine andere Agentur den Beitrag mit ausgetauschtem Namen posten? Ja: echte Fakten einsetzen oder nachfragen.
6. Wenn `get_me` fehlschlägt (Taplio nicht verbunden): sofort stoppen. Meldung "Lauf abgebrochen, Taplio nicht verbunden" im Chat. Kein Ersatz-Output, keine Beiträge ohne Taplio.

## Vertraulich und Ausschlüsse

- Nie in einen Beitrag: LinkedIn-Kennzahlen (auch eigene der letzten 30 Tage), Umsätze, Kosten, Margen, Software-Preise, Kundennamen bei schlechtem Verlauf ohne Freigabe. Im Zweifel fragen.
- Themen draussen: Podcast "Klartext von 2 Kanten", Vogelhäuser, Konkurrenz, Politik, LinkedIn-Mechanik, Algorithmus, Personal Branding als Thema. Andrej schreibt nie über Securitas.
- Keine "bad publicity": Beiträge dürfen Alperna, Partner oder die Branche nicht schlecht aussehen lassen (keine eigenen Fehler wie schwaches Equipment, keine Absagen bei der Akquise, kein "wir suchen neue Kunden"). Zu abstrakt oder abgehoben fliegt raus. Massstab: konkreter Nutzen für den Leser, persönlich, ohne Selbstabwertung.
- Die Firmenseite Alperna ist nicht Teil dieses Laufs.

## Stimme

- Andrej: Zahlen, Systeme, Transparenz, trockener Humor. Kurze Zeilen, Fragmente. Klingt wie auf dem Arbeitsweg geschrieben. Erkenntnisse nicht ankündigen, einbauen. Fehler offen zugeben.
- Leander: Akquise vor Ort, Drehtage, Vereine. Ruhig, handwerksstolz, Beobachtungen statt Analysen, kürzere Sätze. Sport als Analogie höchstens einmal pro Monat (im Archiv prüfen).

## Schreibregeln

Schweizer Hochdeutsch, ss statt ß, Du-Form, Schweizer Zahlenformat (25'000). Keine Em-Dashes oder Halbgeviertstriche, keine Emojis, keine Hashtags, keine Unicode-Fettschrift. Keine Links im Text (Profilhinweis statt Link). Keine Dreierlisten als Reflex, keine Ghostwriter-Phrasen. Länge entscheidet der Inhalt (Richtwert 800 bis 2500 Zeichen). Der Hook muss in den ersten 210 Zeichen allein tragen. Nie reiner Text: jeder Beitrag bekommt Bild, Karussell oder Video. Karussell höchstens eines pro Person und Woche (8 bis 10 Slides plus Caption).

## Override gegenüber den Skill-Standards

Die Taplio-Skills bringen eigene Defaults mit. Diese gelten hier nicht:

| Skill | Skill-Default | Hier gilt |
|---|---|---|
| linkedin-viral-post-analyzer | `search_inspiration` mit min_likes 2000, lang = Nutzersprache | Englisch, keine deutsche Sprachvorgabe (deutsche Suche liefert nichts). Schwelle siehe Schritt 3 |
| linkedin-hook-generator | 10 Hooks, alle sieben Muster rotieren | 3 Varianten, erste folgt der Vorlagen-Formel, mindestens zwei verschiedene Muster. Die sieben Muster dienen nur zur Einordnung in Notion |
| linkedin-cta-optimizer | Emoji-Votes, "Drop your favorite...", Binärfragen, DM-Triggerwort | Standard ist eine Erfahrungsfrage ("Wann hast du...", "Was geht dir durch den Kopf, wenn..."). Keine Zahlenfragen, kein "Welchen Fehler machst du?", kein "Was denkst du dazu?", keine Emojis. Ein CTA, im Text. Nie zweimal derselbe CTA-Typ hintereinander |
| linkedin-post-performance-critic | Benchmark mit lang = Nutzersprache | Benchmark auf Englisch, Urteil gegen diese Regeln statt gegen Generik |
| linkedin-carousel-builder | Cover "Zahl + Payoff", Schluss-Slide "Save this / Comment X" | Aufbau der Vorlage übernehmen, Schluss-Slide mit Erfahrungsfrage, 8 bis 10 Slides |
| linkedin-story-extractor | Story-Bogen als Beitragsform | Nur zum Strukturieren des Rohstoffs. Die Beitragsform kommt aus der Vorlage. Reine Story ohne Vorlage wird abgelehnt |
| linkedin-repurposer | Alle Quellen | Nur wenn der Rohstoff bestehendes Material ist (Audit, Video, Projekt). Podcast ist ausgeschlossen |

Nicht verwenden in diesem Lauf: linkedin-post-writer (erzwingt 1300 Zeichen, Listicle, Kommentar-CTA), linkedin-content-calendar-planner (Mo bis Fr, 4 Wochen, Wildcard), linkedin-swipe-file-builder (erzeugt einen Entwurf pro Referenz, Draft-Flut), linkedin-trending-topics-scanner (liefert Themen statt Vorlagen). Von allen vier gilt nur die Freigabelogik: erst entwerfen, dann freigeben, dann terminieren.

## Ablauf

### Schritt 1: Stand und Archiv

- `get_me`: `ai_settings` lesen. Enthalten sie noch "Marketing Services" oder "Marketingverantwortliche", oben im Bericht warnen, dass die Taplio-Settings veraltet sind. Weiterarbeiten mit den Angaben aus diesem Prompt.
- `get_post_analytics` (mit expliziten Datumsparametern, rund 90 Tage) und `list_posts`: Was lief, was nicht. Nur intern nutzen.
- Notion, Datenbank "Beiträge · Archiv & Analytics" unter Alperna GmbH > LinkedIn > Cockpit: bestehende Beiträge lesen. Keine Wiederholung von Thema, Vorlage oder Hook aus den letzten 90 Tagen.
- linkedin-analytics-interpreter: kurze interne Diagnose, die in die Vorlagenwahl einfliesst.

### Schritt 2: Rohstoff-Inventur

- Notion "Rohstoff-Speicher": alle Einträge mit Status neu oder offen lesen. Pro Eintrag Absender, Uniqueness-Ebene (Erlebnis mit Datum/Ort/Person/Zahl vor Fehler und Verlust vor unbequemer Meinung vor interner Zahl vor Fachdetail) und Freigabebedarf beachten.
- Rohstoff den Absendern und Slots zuordnen. Zählen: Wie viele der 8 Slots sind gedeckt?
- Für jeden ungedeckten Slot: Lücken-Fragen, nummeriert, 8 bis 12 pro Block, nach Ereignissen, Zahlen, Namen, Daten, Orten, Streit, Absagen, Verlusten. Nur Fragen, deren Antwort nicht schon in Notion oder im Archiv steht. Leander beantwortet nicht selbst, Andrej liefert die Antworten.
- Ungedeckte Slots werden nicht beschrieben. Fragen als Notion-Seite "Lücken-Fragen KW" ablegen und im Bericht nennen.

### Schritt 3: Vorlagen suchen (pro gedecktem Beitrag eine)

Reihenfolge der Quellen:
1. Andrejs Screenshots der Taplio-Viral-Seite (Notion "Viral-Vorlagen-Bibliothek"), noch nicht verbrauchte zuerst.
2. `search_inspiration`, Query auf Englisch, abgeleitet vom Rohstoff-Thema. Zwei Abfragen: min_likes 500; zweite Abfrage mit niedrigerer Schwelle, dort nur Treffer mit mehr Kommentaren als Likes behalten.
3. Optional: Viral-Watcher-Digest, falls im verbundenen Postfach vorhanden.

Filter: keine Vorlagen über LinkedIn-Mechanik, Algorithmus oder Personal Branding. Keine Vorlage, die in der Bibliothek in den letzten 4 Wochen verbraucht wurde. Nicht zwei Vorlagen vom selben Autor im selben Lauf. Pro Person nicht zwei gleiche Aufbautypen hintereinander.

### Schritt 4: Schablone

linkedin-viral-post-analyzer auf jede Vorlage. Ergebnis pro Vorlage: tragende Hebel, Hook-Formel, Anzahl Blöcke, Satzrhythmus, Bildtyp, CTA-Muster, Schablone. Vorlagentest bestehen: Autor, erste Zeile, Likes, Kommentare, URL müssen nennbar sein, sonst Vorlage verwerfen und neue suchen.

### Schritt 5: Schreiben

Rohstoff in die Schablone setzen, in der Stimme des Absenders. Struktur und Rhythmus der Vorlage übernehmen, keinen Satz wörtlich oder nahe an der Übersetzung. Pro Beitrag ein Bildbriefing (echtes Foto gewinnt, sonst genau sagen, was Andrej oder Leander in zwei Minuten fotografieren können). Keine KI-Bilder im Kundenkontext.

### Schritt 6: Hook

linkedin-hook-generator mit dem Override oben: 3 Varianten, die erste folgt der Vorlagen-Formel. Frage-Einstieg nur, wenn die Vorlage ihn nutzt. Hook-Muster pro Variante für Notion benennen.

### Schritt 7: CTA

linkedin-cta-optimizer mit dem Override oben. Ziel: Kommentare. Standard Erfahrungsfrage.

### Schritt 8: Kritik

linkedin-post-performance-critic auf jeden Beitrag. Verdikt REWRITE oder KILL: einmal überarbeiten. Reicht es danach nicht für "publish after fixes", den Beitrag nicht ausliefern, sondern Rückfrage stellen.

### Schritt 9: Selbstcheck pro Beitrag

Vorlage genannt, Aufbau übernommen, kein fremder Satz wörtlich. Substitutionstest bestanden. Mindestens ein Element der Uniqueness-Rangfolge enthalten. Alles belegt durch Notion oder Archiv. Nichts Vertrauliches. Hook trägt in 210 Zeichen. Bild dabei. Ein CTA, anders als beim letzten Beitrag. Bei Verstoss: nicht ausliefern, nachfragen.

### Schritt 10: Ablage (ohne Terminierung)

- DOCX "Wochenproduktion_KW<nn>_<Jahr>.docx": oben der Lauf-Bericht, dann pro Beitrag: Slot (Datum, Uhrzeit), Absender, Vorlage mit Kennzahlen (Autor, erste Zeile, Likes, Kommentare, URL), Text, drei Hooks, Bild, offene Punkte. Vor dem Erstellen den docx-Skill lesen.
- Taplio: nur für Andrejs Beiträge `create_draft`, Taplio-ID notieren. Nichts terminieren.
- Notion "Beiträge · Archiv & Analytics": pro Beitrag eine Zeile mit Hook, Absender, Status Entwurf, Slot-Datum, Pillar, Format, Hook-Muster, Experiment "V Viral-Vorlage", CTA-Typ, Zeichenzahl, Volltext, Vorlage, Vorlage-URL, Taplio-ID (bei Leander leer, Vermerk "manuell durch Andrej planen") und Verknüpfung zum Rohstoff. Rohstoff-Status auf "in Arbeit".
- "Viral-Vorlagen-Bibliothek": verwendete Vorlagen mit Datum eintragen. Fehlt die Seite oder Datenbank, melden und nichts Neues anlegen.

### Schritt 11: Bericht im Chat (kurz)

Zuerst Warnungen (Taplio-Settings, fehlender Rohstoff). Dann: x von 8 Slots gedeckt, Link zum DOCX, die Lücken-Fragen, offene Punkte pro Beitrag. Beiträge selbst nicht im Chat wiederholen.

## Teil B: Freigabe (nur wenn Andrej im Chat freigibt)

Pro Beitrag drei Möglichkeiten: freigeben, Hook tauschen, streichen. Korrekturen einarbeiten und die Formulierung für spätere Läufe übernehmen.

Nach Freigabe eines Andrej-Beitrags: `update_draft` mit dem Endtext, Bild oder Karussell anhängen (`attach_media_from_url` oder `upload_media`), erst dann `schedule_draft` auf den Slot. Kein `schedule_draft` ohne Medium. Notion-Status auf Geplant, Taplio-ID eintragen.

Nach Freigabe eines Leander-Beitrags: Endtext, Bildbriefing und Slot (Datum, Uhrzeit) als sauberen Block für Andrejs manuelle Planung bereitstellen. Notion-Status auf Geplant.

Taplio meldet Terminierungen nicht immer als veröffentlicht. Uhrzeiten melden, keine Vollzugsmeldungen.

## Abbruch und Fehlerfälle

- Taplio nicht verbunden: stoppen (Harte Regel 6).
- Notion nicht erreichbar: Lauf nicht starten, Meldung im Chat. Kein Schreiben ohne Rohstoff-Speicher.
- Weniger als 4 Slots pro Person gedeckt: nur die gedeckten schreiben, Rest als Lücken-Fragen. Das ist kein Fehler, sondern Absicht.
- Keine passende Vorlage gefunden: Slot als Lücke melden, keine Story ohne Vorlage schreiben.

## Technische Referenz (ergänzt am 5. Oktober 2026, ohne Vorrang vor dem Text oben)

Notion-Ziele, am 5. Oktober 2026 per Suche bestätigt (Pfad: Alperna GmbH / LinkedIn / Cockpit · LinkedIn Betriebssystem):

| Name im Text | Typ | URL |
|---|---|---|
| Rohstoff-Speicher | Datenbank | https://app.notion.com/p/00aee01fdda34d7a948e41c91980378d |
| Beiträge · Archiv & Analytics | Datenbank | https://app.notion.com/p/883f3086649540beae93435c37a924d6 |
| Viral-Vorlagen-Bibliothek | Seite | https://app.notion.com/p/3de6be186e9b817cb6afeb5d9d1222ea |
| Cockpit · LinkedIn Betriebssystem | Seite (Elternseite) | https://app.notion.com/p/3dc6be186e9b81eb97c9ddcac1703f98 |

Taplio-MCP-Werkzeuge, die dieser Lauf braucht: `get_me`, `get_post_analytics`, `list_posts`, `search_inspiration`, `create_draft`, `update_draft`, `attach_media_from_url`, `upload_media`, `schedule_draft` (nur Teil B), `get_draft`. Nie: `publish_draft`.

Reihenfolge der Skill-Aufrufe im Lauf: linkedin-analytics-interpreter (Schritt 1), linkedin-story-extractor nur zum Ordnen des Rohstoffs (Schritt 2), linkedin-viral-post-analyzer (Schritt 4), linkedin-hook-generator (Schritt 6), linkedin-cta-optimizer (Schritt 7), linkedin-post-performance-critic (Schritt 8), linkedin-carousel-builder nur bei einem Karussell-Slot, docx (Schritt 10).
