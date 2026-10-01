# Sicherheits-Header – RC17.10

Die enthaltene .htaccess setzt bei Apache-kompatiblem Hosting mit aktiviertem mod_headers:

- Content-Security-Policy: lokale Dateien und ausdrücklich erlaubte Inline-Skripte; keine fremden Frames oder Plugins.
- X-Frame-Options: DENY, um die Einbettung der Website in fremde Seiten zu unterbinden.

## Installation und Prüfung

Den gesamten Inhalt des Website-Ordners inklusive .htaccess in das Webverzeichnis hochladen. Vorhandene .htaccess-Regeln vorher sichern und die neuen Header-Regeln ergänzen, statt andere Regeln zu überschreiben.

Die Konfiguration benötigt mod_headers und die Berechtigung, Header in .htaccess zu setzen. Bei einem anderen Webserver müssen dieselben Header in dessen Konfiguration eingetragen werden. Ein lokaler Aufruf per Doppelklick setzt keine HTTP-Header.

Nach dem Hochladen Hauptseite und Profilseiten öffnen, Menü und Hell/Dunkel testen. Im Netzwerk-Tab der Browser-Entwicklerwerkzeuge die Antwort-Header des HTML-Dokuments auf Content-Security-Policy und X-Frame-Options prüfen. Danach Aikido erneut scannen lassen.

Die CSP erlaubt bestehende Inline-Skripte über SHA-256-Hashes. Werden diese Skripte oder die strukturierten Daten verändert, müssen die Hashes in .htaccess aktualisiert werden. Externe Links zu WhatsApp und E-Mail bleiben möglich.

Die Server-Konfiguration wurde vorbereitet; die tatsächlich ausgelieferten Header sind nach der Veröffentlichung zu prüfen.
