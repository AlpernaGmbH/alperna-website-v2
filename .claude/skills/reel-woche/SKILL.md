---
name: reel-woche
description: Wöchentlicher Reel-Watcher-Lauf auf dem Mac. Analysiert die gespeicherten Instagram-Reels lokal (jakeb144/reel-watcher), schreibt pro Reel eine JSON-Studie und erstellt einen Wochenbericht, was sich für Alperna zum Nachbauen lohnt. Auslösen mit /reel-woche in Claude Code auf dem Mac. Beim ersten Mal richtet der Skill Homebrew, uv, ffmpeg und das Tool ein.
---

# Reel-Woche: gespeicherte Reels auswerten

Läuft nur auf einem Apple-Silicon-Mac (M1 oder neuer). Alles ausser dem Medien-Download läuft lokal.
Diese Cloud-Session kann das nicht ausführen. Der Skill ist für Claude Code auf dem Mac gedacht.

## Harte Regeln

1. Kein Geld ohne Freigabe. `--run` ruft Apify auf (rund 0,002 Dollar pro Reel). Immer zuerst den Dry-Run zeigen, die Anzahl nennen und auf ein «ok» warten.
2. `APIFY_TOKEN` nur aus der Umgebung lesen. Nie in eine Datei, ein Log, eine URL oder einen Commit schreiben.
3. Kein Login bei Instagram, keine Cookies, keine UI-Automation. Reel-URLs kommen aus dem offiziellen Datenexport oder aus einer URL-Liste.
4. Keine Medien, Frames, Transkripte oder Studien in ein Git-Repo. Alles bleibt unter `~/reel-watcher/out`.
5. Modell-Output ist ein Entwurf. Namen, Zitate und Zahlen aus der Analyse nie als Fakt weitergeben.

## Teil A: Erststart (einmal, rund 20 Minuten plus Modell-Download)

Prüfe jeden Schritt mit dem Befehl links, führe den Schritt rechts nur aus, wenn die Prüfung fehlschlägt.

| Prüfung | Falls nötig |
|---|---|
| `uname -m` ergibt `arm64` | Sonst abbrechen: Intel-Macs werden nicht unterstützt. |
| `which brew` | Homebrew installieren: `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`. Danach die zwei Zeilen ausführen, die das Skript am Ende ausgibt (sie tragen `brew` in `~/.zprofile` ein). Neues Terminal öffnen. |
| `which ffmpeg uv` | `brew install ffmpeg uv` |
| `test -d ~/reel-watcher` | `git clone https://github.com/jakeb144/reel-watcher ~/reel-watcher` |
| `cd ~/reel-watcher && uv sync` läuft durch | Fehler im Chat zeigen, nicht raten. |
| `sysctl -n hw.memsize` | Unter 32 GB: Modellgrösse `small` (rund 6 GB Download). Ab 32 GB: `large` (rund 20 GB). Dem Nutzer sagen, was geladen wird. |
| `security find-generic-password -s apify -w` liefert einen Wert | Apify-Konto auf console.apify.com anlegen, Token kopieren, dann `security add-generic-password -a "$USER" -s apify -w` ausführen (fragt den Token interaktiv ab, so landet er im Schlüsselbund und nie in einer Datei). |

Danach ein Probelauf ohne Netz und ohne Kosten mit irgendeinem eigenen MP4:

```
cd ~/reel-watcher
uv run reel-watcher study --local ~/Movies/irgendein-clip.mp4 --out-root ./out
cat out/study/irgendein-clip.json
```

Erst wenn das durchläuft, geht es zu Teil B.

### Reel-Liste füllen

Zwei Wege, der zweite ist für den Wochenrhythmus der praktische:

1. Instagram-Datenexport (sauber, aber langsam, dauert bis zu 48 Stunden): Instagram, Einstellungen, Accounts Center, Deine Informationen und Berechtigungen, Deine Informationen herunterladen, nur «Gespeichert» anhaken, Format JSON. Datei `your_instagram_activity/saved/saved_posts.json` entpacken und umwandeln: `uv run reel-watcher export pfad/saved_posts.json -o ~/reel-watcher/urls.tsv`.
2. Laufende Liste (empfohlen): Beim Speichern eines Reels in Instagram zusätzlich «Link kopieren» und die URL in `~/reel-watcher/urls.tsv` anhängen, eine URL pro Zeile. Optional hinter einem Tab ein Sammlungsname, zum Beispiel `Hooks` oder `Vereine`. Fertige Reels werden beim nächsten Lauf übersprungen, die Datei darf also wachsen.

## Teil B: Wochenlauf (jede Woche, Auslöser ist der Nutzer mit /reel-woche)

1. Vorbedingungen prüfen: `cd ~/reel-watcher && uv run reel-watcher --help` läuft, `urls.tsv` existiert. Token aus dem Schlüsselbund in die Umgebung holen, nur für diesen Prozess: `export APIFY_TOKEN="$(security find-generic-password -s apify -w)"`. Den Wert nie ausgeben.
2. Kontext setzen, damit das Urteil zu Alperna passt: `export REEL_WATCHER_CONTEXT="Marketing-Agentur für Schweizer KMU und Vereine, baut LinkedIn- und Instagram-Content für Kunden"`.
3. Dry-Run: `uv run reel-watcher study --input urls.tsv --out-root ./out`. Anzahl neuer Reels nennen, Kosten schätzen (Anzahl mal 0,002 Dollar), auf «ok» warten.
4. Nach Freigabe: `uv run reel-watcher study --input urls.tsv --out-root ./out --run --limit 20`. Fehlgeschlagene Reels stehen in `out/study/_failed.jsonl`, nur auf Wunsch mit `--retry-failed` wiederholen.
5. Bericht bauen, ohne Modellaufruf, rein aus `out/study/*.json` (Dateien mit `_` am Anfang überspringen). Pro Reel lesen: `post.author`, `post.views`, `post.likes`, `post.comments`, `analysis.hook`, `analysis.format`, `analysis.why_it_works`, `analysis.cta`, `giveaway`, `analysis.takeaway`, `collections`, `analyzed_at`. Nur Reels mit `analyzed_at` in den letzten 8 Tagen zählen zu dieser Woche.
6. Bericht als `~/reel-watcher/out/reports/KW<nn>_<Jahr>.md` schreiben, Aufbau:
   - Kopf: Anzahl analysierter Reels, Anzahl Fehler, Apify-Kosten aus `out/apify_cost.jsonl`.
   - «Lohnt sich nachzubauen»: höchstens 5 Reels, sortiert nach `analysis.takeaway.relevant` zuerst, dann Views. Pro Reel: Autor, URL, Hook (gesprochen und eingeblendet), Format, warum es funktioniert, was Alperna daraus konkret bauen kann (ein Satz, bezogen auf KMU oder Vereine), Bild `out/study/<code>.jpg`.
   - «Hook-Formeln der Woche»: die `analysis.hook.type`-Werte gezählt, je ein Beispiel.
   - «Giveaway-Mechaniken»: alle Reels mit `giveaway.offered` true, mit Keyword und Angebot. Nur als Beobachtung, nie zum Nachkommentieren.
   - «Nicht lohnend»: Reels mit `analysis.takeaway.relevant` false in einer Zeile pro Reel.
   - «Offen»: fehlgeschlagene Codes aus `_failed.jsonl`.
7. Im Chat nur den Kopf und die Liste «Lohnt sich nachzubauen» zeigen, dazu der Pfad zum Bericht. Keine Transkripte im Chat.
8. Alle 4 Wochen anbieten: Advice-Library bauen nach `~/reel-watcher/prompts/build_advice_library.md`, dann `uv run reel-watcher advice --in library.json --out advice-library.html`.

## Fehlerfälle

- `uv sync` oder Modell-Download bricht ab: Fehlermeldung zeigen, Plattenplatz prüfen (`df -h ~`), nicht erneut starten ohne Rückfrage.
- Apify meldet Kostenlimit: Batch-Deckel steht standardmässig bei 2 Dollar, Erhöhung nur mit `--apify-batch-cap-usd` nach Freigabe.
- `urls.tsv` leer oder alle Reels schon analysiert: melden, kein Lauf, kein Bericht.
- Kein Token im Schlüsselbund: Teil A, letzte Zeile der Tabelle.
