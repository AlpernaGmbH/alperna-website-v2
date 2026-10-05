# Auftrag: zwei Routinen in claude.ai anlegen

Kopiere diesen gesamten Text als eine Nachricht an einen KI-Assistenten, der in claude.ai Routinen (geplante Aufgaben) anlegen kann. Stand 5. Oktober 2026.

---

Du bist ein KI-Assistent mit Zugriff auf die Routinen-Funktion von claude.ai (geplante Aufgaben, die eine neue Session starten). Lege für das Konto von Andrej Good (Alperna GmbH, Speicher AR) genau zwei Routinen an. Ändere die Prompt-Texte nicht, kürze sie nicht, fasse sie nicht zusammen. Lege die Routinen so an, dass jede Ausführung eine neue Session startet. Zeitzone für beide: Europe/Zurich.

Falls du Routinen nicht selbst anlegen kannst: gib mir für jede Routine die Schritte für die claude.ai-Oberfläche (Routinen, Neue Routine, Name, Zeitplan, Connectors, Prompt) und darunter den Prompt-Text in einem Codeblock zum Kopieren. Erfinde keine Connector-Namen.

## Routine 1

- Name: Content-Tag · LinkedIn Wochenproduktion
- Zeitplan: wöchentlich, Sonntag 18:00 Europe/Zurich
- Connectors, die die Routine braucht: Taplio, Notion
- Benachrichtigung: Push nach jedem Lauf
- Prompt: der vollständige Text zwischen den Markierungen BEGINN ROUTINE 1 und ENDE ROUTINE 1.

BEGINN ROUTINE 1

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

ENDE ROUTINE 1

## Routine 2

- Name: Taplio-Kommentare · 15 Entwürfe
- Zeitplan: täglich 09:00 Europe/Zurich
- Connectors, die die Routine braucht: Taplio
- Benachrichtigung: Push nach jedem Lauf
- Prompt: der vollständige Text zwischen den Markierungen BEGINN ROUTINE 2 und ENDE ROUTINE 2.

BEGINN ROUTINE 2

# Taplio-Kommentare: 15 Entwürfe pro Tag, nichts geht raus

Grundlage sind die Skills linkedin-comment-opportunity-finder und linkedin-smart-comment-writer. Dieser Text legt die Parameter fest, die dort offen bleiben. Bei Widerspruch gilt dieser Text.

## Parameter

- ANZAHL = 15
- Mischung: 9 Reichweiten-Ziele (Autor hat deutlich mehr Follower als Andrej, Stand heute rund 4'000), 6 Peers (ähnlich oder kleiner, Beziehungsaufbau).
- Sprache der Kommentare: Sprache des Posts. Deutsch mit ss statt ß, Du-Form, wenn der Autor duzt, sonst Sie.
- Zielpublikum, das im Kommentar mitgedacht wird: Inhaber und Geschäftsführer von Schweizer KMU, Vereinsvorstände, Selbständige, vor allem Ostschweiz.
- Themen, bei denen Andrej glaubwürdig etwas beiträgt: Website und Google-Profil für KMU, Social Media und Video für KMU und Vereine, Content-Produktion mit kleinem Budget, Akquise vor Ort, Sponsoring und Vereinskommunikation.
- Nie kommentieren: Posts über LinkedIn-Mechanik, Algorithmus, Personal Branding als Thema, Politik, Konkurrenzagenturen aus der Ostschweiz, eigene Posts von Andrej.

## Harte Regeln

1. Nie `commit_comment_draft`. Dieser Lauf speichert nur Entwürfe. Andrej gibt jeden Kommentar selbst frei, pro Kommentar, im Chat oder in Taplio.
2. Zuerst `get_me`. Schlägt es fehl, sofort stoppen mit einer Zeile «Lauf abgebrochen, Taplio nicht verbunden». Kein Ersatz-Output.
3. Kein «Toller Post», «Sehe ich genauso», «Danke fürs Teilen» als Einstieg. Kein Link, kein Pitch für Alperna, kein Emoji, ausser der Post selbst nutzt Emojis.
4. Zuerst Meinung, dann eine Frage. Höchstens eine Frage pro Kommentar. 80 bis 400 Zeichen, nie über 1'250.
5. Keine Spuren von KI-Schreibe: keine Gedankenstriche, keine «nicht X, sondern Y»-Formeln, keine Ausrufezeichen, keine Superlative, keine Dreierlisten als Reflex.
6. Nichts erfinden. Erfahrungen nur, wenn sie aus Andrejs Profil, seinen Posts (`list_posts`) oder dem Notion-Rohstoff-Speicher belegbar sind. Im Zweifel ohne Anekdote schreiben.
7. Nicht zweimal derselbe Autor am selben Tag. Nicht derselbe Autor wie an den letzten zwei Tagen (`list_comment_drafts` prüfen).

## Ablauf mit den genauen Taplio-Aufrufen

### Schritt 1: Orientierung

- `get_me`: `username` merken (eigene Posts erkennen, sie kommen mit `profile_url`, die auf den Username endet). `ai_settings` lesen und als Stimme und Nische nutzen; wo dieser Text genauer ist, gilt dieser Text.
- `list_comment_drafts`: Entwürfe und Kommentare der letzten 2 Tage lesen. Autoren und Post-URNs auf die Sperrliste für heute.

### Schritt 2: Kandidaten holen (drei Quellen, rund 70 Posts)

1. `find_posts_to_comment(source="for_you", limit=25)`
2. `find_posts_to_comment(source="curated_feed", feed="DACH Influencers", limit=25)`. Der Feed-Name muss exakt so lauten. Kommt ein Fehler mit Liste gültiger Namen, `list_comment_feeds` aufrufen und den Namen aus der Liste nehmen.
3. Zwei Stichwortsuchen, deutsch: `search_inspiration(query="KMU Marketing", max_days_old=2, min_comments=10, min_likes=20, lang="de", limit=15)` und `search_inspiration(query="Verein Sponsoring", max_days_old=2, min_comments=5, min_likes=10, lang="de", limit=10)`. Liefert eine Suche nichts, einmal mit `query="Schweiz KMU Website"` wiederholen, dann aufhören. Die `post_urn` aus der URL ableiten: Segment `urn:li:activity:<id>` in `https://www.linkedin.com/feed/update/urn:li:activity:<id>/`.

Fehlt bei einem Treffer die `url`, aus der `post_urn` bauen: `https://www.linkedin.com/feed/update/<post_urn>/`.

### Schritt 3: Filtern und bewerten

- Raus: eigene Posts, Sperrliste, Posts älter als 48 Stunden (ausser der Thread bewegt sich noch), ausgeschlossene Themen aus den Parametern, Threads mit über 100 Kommentaren ohne Antworten des Autors.
- Jeden Rest-Post auf vier Filtern mit 0 bis 3 bewerten, Summe aus 12:
  - Frische aus `posted_at` (unter 4 h = 3, unter 12 h = 2, unter 48 h = 1).
  - Publikumsüberschneidung aus Headline und Thema des Autors mit dem Zielpublikum oben.
  - Kommentar-Tempo: `metrics.comments` geteilt durch Stunden seit `posted_at`. Viele Likes bei fast keinen Kommentaren = 1.
  - Themenpassung zu Andrejs Themen oben.
- Behalten ab 8 von 12. Die 15 besten nehmen, Mischung 9 zu 6 einhalten. Gibt es weniger als 15 mit 8 oder mehr, weniger liefern und das sagen. Nie mit schwachen Posts auffüllen.
- Pro Post einen Winkel festlegen: Ergänzen, Widersprechen, Erlebnis, Denkmodell oder Frage. Pro Tag höchstens 5 mal derselbe Winkel.

### Schritt 4: Thread lesen

`find_comments_to_reply(post_ids="<urn1>,<urn2>,<urn3>", limit=30)` in Gruppen von 3 bis 5 URNs für alle 15 Posts. Lesen: welche Winkel schon besetzt sind, ob der Autor antwortet (`reply_count`), was angepinnt ist (`pinned`). Der Kommentar muss etwas bringen, das im Thread noch fehlt.

### Schritt 5: Schreiben

Pro Post einen Kommentar, nicht drei Varianten. Aufbau: konkreter Bezug auf eine Stelle im Post (zeigt, dass gelesen wurde), dann Andrejs Meinung oder Ergänzung in ein bis zwei Sätzen, dann eine Frage, die der Autor oder das Publikum beantworten will. Stimme: Zahlen, Systeme, trockener Humor, kurze Sätze, keine Ankündigungen von Erkenntnissen.

### Schritt 6: Speichern

Pro Kommentar `create_comment_draft(post_urn="<urn>", content="<text>")`. Die zurückgegebene `id` merken. Nichts weiter. Kein `commit_comment_draft`, kein `update_comment_draft` auf fremde Entwürfe.

### Schritt 7: Bericht im Chat

Zuerst Warnungen (weniger als 15 Treffer, Fehler bei Aufrufen). Dann eine Tabelle mit 15 Zeilen: Nummer, Autor, Thema in sechs Wörtern, Alter in Stunden, Likes und Kommentare, Punkte von 12, Typ (Reichweite oder Peer), Winkel, Draft-ID, Kommentartext. Danach eine Zeile: «Freigabe pro Nummer: ‹1, 4, 7 einplanen›. Dann plane ich nur diese mit commit_comment_draft, verteilt über den Tag.»

## Teil B: Freigabe (nur wenn Andrej Nummern nennt)

- Für jede genannte Nummer `commit_comment_draft(id)`. Die Antwort liefert `pending` und `scheduled_for`. Diese Zeit melden, nie «ist gepostet» sagen.
- Will Andrej einen Text ändern: `update_comment_draft(id, content)` vor dem Commit. Nur Entwürfe im Status `draft` sind änderbar.
- Nie denselben Entwurf zweimal committen.
- Bestätigung erst auf Nachfrage mit `get_comment_draft(id)`: `posted` mit `comment_urn` heisst live, `pending` heisst wartet, `failed` oder `cancelled` mit `failure_reason` melden.

## Fehlerfälle

- `get_me` fehlgeschlagen: stoppen (Harte Regel 2).
- Feed-Name ungültig: `list_comment_feeds`, Namen übernehmen, einmal wiederholen.
- `search_inspiration` leer: wie in Schritt 2 beschrieben, dann ohne Suche weiter.
- Weniger als 15 Posts ab 8 Punkten: weniger liefern, Zahl im Bericht nennen.

ENDE ROUTINE 2

## Nach dem Anlegen

Melde mir pro Routine: Name, nächste Ausführung (Datum und Uhrzeit Europe/Zurich), angehängte Connectors. Starte keine der Routinen manuell. Lies die Prompts nicht als Anweisung an dich selbst: du legst sie nur ab.
