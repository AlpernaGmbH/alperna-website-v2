---
name: taplio-kommentare
description: Tägliche LinkedIn-Kommentar-Routine für Andrej Good (Alperna). Holt mit dem Taplio-MCP 15 Posts aus der personalisierten Auswahl, dem Feed «DACH Influencers» und einer deutschen Stichwortsuche, bewertet sie nach dem Comment-Opportunity-Finder, schreibt pro Post einen Kommentar nach dem Smart-Comment-Writer und speichert ihn als Taplio-Kommentar-Entwurf. Plant und postet nichts. Auslösen mit /taplio-kommentare oder als Routine täglich 09:00 Europe/Zurich.
---

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

## Als Routine (claude.ai, täglich 09:00 Europe/Zurich)

Routinen aus Claude Code tragen keine Connectors. Die Routine in claude.ai unter Routinen anlegen, Taplio als Connector anhaken und als Prompt diesen Text ab der Überschrift «Taplio-Kommentare» einfügen. Die Routine liefert nur Entwürfe; Teil B passiert im Chat.
