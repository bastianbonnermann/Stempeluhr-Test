STEMPELUHR 4.7 – TESTVERSION

Änderungen in Version 4.3:
- Übersicht kompakter gestaltet; Info-Karten unter der Zeiterfassung.
- Resturlaub zeigt automatisch das aktuelle Kalenderjahr.
- Letzte Buchungen aus der Übersicht entfernt; vollständige Liste unter „Auswertung & Daten“.
- Minutenkorrektur in zwei Reihen angeordnet: -1/+1 und -5/+5.
- Tageskennzeichen A/D/H direkt auf der Übersicht.
- H – Home Office erzeugt beim Auswählen automatisch eine Tagesbuchung mit Kommen 07:30 und Gehen 16:15.
- Die manuelle Zeitkontoanpassung kann im Kontoverlauf entfernt werden.

INSTALLATION / UPDATE AUF GITHUB PAGES:
Die Dateien aus diesem ZIP in das Stammverzeichnis des Test-Repositories hochladen und vorhandene Dateien ersetzen.

DATENHINWEIS:
Die Buchungen bleiben im lokalen Browser-Speicher (localStorage). Ein App-Update über GitHub Pages löscht diese Daten nicht. Vor größeren Updates trotzdem eine JSON-Sicherung erstellen.

WICHTIG:
Dies ist weiterhin eine Testversion. Vor dem alleinigen produktiven Einsatz die Funktionen und Datensicherung gründlich prüfen.


Änderungen in Version 4.5:
- PDF-Auswertung zeigt für jeden Monat mit erfassten Buchungen sämtliche Kalendertage.
- Wochentag und Datum werden für jeden Tag einzeln aufgeführt.
- Automatische Feiertage in Rheinland-Pfalz und Wochenendtage werden auch ohne manuelle Buchung angezeigt.
- Erfasste Arbeits-, Dienstreise-, Urlaubs-, Betriebsurlaubs- und sonstige Tagesbuchungen zeigen ihre eingetragenen Zeiten und Berechnungen.
- Monatsdifferenz bleibt am Ende jeder Monatsseite; nicht erfasste Werktage werden nicht in die Differenz eingerechnet.

Änderungen in Version 4.7:
- PDF-Monatsübersicht auf DIN A4 Hochformat mit angepassten Spaltenbreiten.
- Nicht erfasste Tage werden mit „–“ gekennzeichnet.
- Wochenendtage werden als „Wochenende“ bezeichnet.
