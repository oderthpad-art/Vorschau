# Karateverein Dallenwil – Website v1.0-rc17.13

Stand: 6. Oktober 2026. Statische Website aus HTML, CSS und JavaScript, unabhängig von Base44 und ohne Build-Schritt.

## Aktueller Umfang

- Startseite mit Trainingsangebot, Zeiten, Trainingsort und ausführlichen Vereinsinhalten.
- Vereinsseite mit Vorstand, Mitgliedschaft und Preisen sowie Vereinsgeschichte.
- Sieben Trainerprofile: Adrian Schön, Daniela Wyss-Schön, Robert Wyss-Schön, Thomas Odermatt, Jaqueline Migliaccio, Claudia Erni und Michelle Erni.
- Fünf Vorstandsprofile. Die frühere `vorstand.html` leitet auf den Vorstandsabschnitt der Vereinsseite weiter.
- Shinkyokushin-Seite mit Dojo-Eid und Sosai-Masutatsu-Oyama-Inhalten.
- Training für Kinder ab 6 Jahren und Erwachsene ab 18 Jahren.
- Kontaktseite mit Anruf-, WhatsApp- und E-Mail-Links für Präsidentin und Vizepräsidentin; das Kontaktformular wurde entfernt.
- Impressum und Datenschutz, Hell/Dunkel-Modus, responsives Menü und Animationen.
- Sitemap, Robots-Datei, Webmanifest und Vereinslogo als Favicon.

## Aktuelle Änderungen

| Version | Änderung |
| --- | --- |
| RC17.3 | Neues Foto von Jaqueline in Trainerteam, Vorstand und beiden Profilseiten; angepasster Bildausschnitt. |
| RC17.4 | Neues Foto von Michelle in beiden Bereichen und Profilseiten; angepasste Kopfgrösse. |
| RC17.5 | Neues Foto von Claudia in beiden Bereichen und Profilseiten; angepasste Kopfgrösse. |
| RC17.6 | Erwachsenentraining auf der Trainingsseite auf 18 Jahre korrigiert. |
| RC17.7 | Postleitzahl in der Datenschutzerklärung auf 6383 Dallenwil korrigiert. |
| RC17.8 | Anmeldungshinweis auf der Trainingsseite: „Melde dich vorher an.“ |
| RC17.9 | Trainerrollen auf den Detailseiten von Jaqueline, Claudia und Michelle wie bei Thomas dargestellt: „Trainer Kinder & Erwachsene“. |
| RC17.10 | Server-Konfiguration für Content Security Policy und Schutz gegen Clickjacking ergänzt. |
| RC17.13 | Formulierung zur Übereinstimmung von Karate-Philosophie und J+S-Grundsätzen auf Start- und Vereinsseite angepasst. |
| RC17.12 | J+S-Artikel auf Start- und Vereinsseite erweitert: gemeinsame Werte mit Karate, verantwortungsvolle Förderung und offizielle Quellen. |
| RC17.11 | Danielas Telefonnummer und WhatsApp-Link auf +41762485674 aktualisiert; README auf den aktuellen Stand gebracht. |

Die ausführliche Versionshistorie steht in [CHANGELOG.md](CHANGELOG.md).

## Kontakt

Daniela Wyss-Schön: **+41 76 248 56 74**. Anruflinks verwenden `tel:+41762485674`, der WhatsApp-Link verwendet `https://wa.me/41762485674`.

## Lokal testen

ZIP entpacken. Im entpackten Website-Ordner starten:

```bash
python -m http.server 8000
```

Dann `http://localhost:8000` öffnen. Auch ein direkter Aufruf von `index.html` ist möglich. Der lokale Python-Server verarbeitet die `.htaccess` nicht und setzt damit die enthaltenen Sicherheits-Header nicht.

## Veröffentlichung und Sicherheits-Header

Den Inhalt des Website-Ordners inklusive `.htaccess` in das Webverzeichnis hochladen. Bei bestehender `.htaccess` vorher sichern und die Header-Regeln mit den vorhandenen Regeln zusammenführen.

Die `.htaccess` setzt auf Apache-kompatiblem Hosting mit `mod_headers` und entsprechender Berechtigung eine Content Security Policy sowie `X-Frame-Options: DENY`. Andere Hosting-Systeme benötigen eine eigene Header-Konfiguration. Nach dem Upload die tatsächlichen Antwort-Header und die Website-Funktionen prüfen; anschliessend Aikido erneut scannen lassen. Die Wirksamkeit auf dem Live-Server wurde hier nicht bestätigt.

Details stehen in [SICHERHEIT.md](SICHERHEIT.md). Bei Änderungen an Inline-Skripten oder strukturierten Daten müssen die SHA-256-Hashes der CSP angepasst werden.

## Pflege bei jeder neuen Version

- README mit Versionsnummer, aktuellem Umfang und Änderungen nachführen.
- VERSION und CHANGELOG synchron aktualisieren.
- Kontaktangaben in sichtbarem Text, Anruf- und WhatsApp-Links abgleichen.
- Interne Links, Bildverweise und ZIP-Inhalt prüfen.
- Nur freigegebene Vereinsbilder verwenden.
