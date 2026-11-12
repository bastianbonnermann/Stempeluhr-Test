STEMPELUHR 4.0 – PROTOTYP VERSION 0.3

WICHTIG
- Dies ist ein separater Prototyp. Die bestehende Version 3.0 wird nicht verändert.
- Es werden keine Buchungen aus Version 3.0 importiert.
- Testdaten werden lokal im Browser gespeichert (localStorage, Schlüssel stempeluhr_v4_prototype).
- Vorläufiger Zeitkonto-Anfangsbestand: 77:46 h ab 01.01.2027. Der endgültige Wert wird zum 31.12.2026 aus Excel übernommen.
- Jahresurlaub: 30 Tage. Betriebsurlaub wird vom gleichen Urlaubsanspruch abgezogen.

BERECHNUNGSREGELN
- Montag bis Freitag: SOLL 8:00 h.
- Samstag/Sonntag: SOLL 0:00 h. Gearbeitete Nettozeit ist vollständig Pluszeit.
- Mehrere Kommen-/Gehen-Intervalle pro Tag sind möglich.
- Jedes ununterbrochene Intervall wird einzeln geprüft: ab 6:01 h werden 45 Minuten abgezogen; bis einschließlich 6:00 h kein Abzug.
- Unterbrechungen zwischen Intervallen zählen nicht als Arbeitszeit und lösen keinen zusätzlichen Pausenabzug aus.
- A Arbeitstag und D Dienstreise: IST aus Kommen/Gehen berechnet; SOLL 8 h werktags.
- B Betriebsurlaub, F Feiertag, K Krankheit, U Urlaub, H Home Office: werktags IST 8 h und SOLL 8 h.
- Z Zeitkonto: werktags IST 0 h, SOLL 8 h (−8 h).
- Manuelle Zeitkontoanpassungen werden mit Datum, Betrag und Grund als separate Buchung geführt.
- Das Zeitkonto wird chronologisch aus Anfangsbestand, Tagesdifferenzen und Anpassungen neu berechnet.
- Nachträgliche Änderungen an Tagesbuchungen wirken sich automatisch auf alle folgenden Kontostände aus.
- Die Zeitkontoübersicht zeigt getrennt die Summe der Tagesdifferenzen und manuellen Anpassungen.

ENTHALTENE FUNKTIONEN
- Übersicht und laufender Zeitkontostand
- Kommen/Gehen mit Minutenkorrektur
- Manuelle Tageserfassung
- Abwesenheitszeiträume
- Manuelle Zeitkontoanpassung
- Tagesauswertung und CSV-Export
- PDF über Drucken / Als PDF speichern
- JSON-Datensicherung und Zusammenführung einer Sicherung
- Offline-Cache

BEKANNTE PROTOTYP-GRENZEN
- Noch keine Übernahme der Feiertagskalender.
- Die nachträgliche Bearbeitung von Tagesbuchungen und nachvollziehbare Gegenbuchungen werden in späteren Schritten ergänzt.
- Die Vorschau/IST-Berechnung verwendet die Zeitspanne zwischen Kommen und Gehen und zieht die Pause einmal ab.
- Keine Synchronisierung zwischen Geräten.
- Noch keine Benutzerverwaltung oder Team-/Kollegenfunktion.
- Noch keine endgültige Prüfung sämtlicher Excel-Sonderfälle.
- Tagesbuchungen sind im Prototyp nicht löschbar; spätere Korrekturen werden als nachvollziehbare Gegenbuchungen ergänzt.

TESTEN
1. ZIP entpacken und lokal oder auf einem separaten Test-GitHub-Repository bereitstellen.
2. Nicht über die bestehende v3.0-Installation veröffentlichen.
3. Für Offline-Test einmal online öffnen und danach Verbindung trennen.
4. Die Berechnungen anhand der Excel-Datei gegenprüfen.


VERSION 0.6 – FEIERTAGSKALENDER-FIX
- Fehlende Funktionen für Osterberechnung, Feiertagsliste Rheinland-Pfalz und Feiertagsprüfung ergänzt.
- Feiertagsliste wird für das Jahr des ausgewählten Abwesenheitsbeginns aufgebaut.
- Urlaub am 24.12. und 31.12. wird mit jeweils 0,5 Tagen berechnet; Wochenenden und gesetzliche Feiertage mit 0 Tagen.
- Service-Worker-Cache wurde geändert, damit der Browser die korrigierte Version neu lädt.


VERSION 0.8 – URLAUBSÜBERTRAG
- Resturlaub wird ab 2027 automatisch aus dem Vorjahr übernommen.
- Für 2027 werden die in 2026 verbliebenen Urlaubstage zum Jahresanspruch addiert.
- Folgejahre übernehmen jeweils den positiven Resturlaub des Vorjahres.
- U und B reduzieren den Urlaubsbestand; Feiertage und Wochenenden werden weiterhin nicht abgezogen.
- Bestehende lokale Daten bleiben erhalten: gleicher localStorage-Schlüssel und gleiches Datenformat.


VERSION 4.1 – TAGESBUCHUNGEN BEARBEITEN
- In „Auswertung & Daten“ besitzt jede Tagesbuchung jetzt eine Aktion „Bearbeiten“.
- Tagesbuchungen können nachträglich geändert werden; die vorherige Fassung bleibt in der Änderungshistorie der Buchung erhalten.
- Tagesbuchungen können bei Bedarf entfernt werden. Die Entfernung wird zusätzlich im internen Änderungsprotokoll gespeichert.
- Nach jeder Änderung oder Entfernung werden Zeitkonto und Folgestände aus den verbleibenden Buchungen neu berechnet.
- Die Datensicherung enthält auch Änderungshistorien und das Änderungsprotokoll.
- Der Offline-Cache wurde erneuert, damit Browser nicht versehentlich die vorherige Oberfläche anzeigen.

TESTSCHRITT
1. In „Auswertung & Daten“ die Zeile 01.01.2027 suchen.
2. „Bearbeiten“ anklicken.
3. Prüfen, dass Kennzeichen F angezeigt wird.
4. „Buchung entfernen“ anklicken und bestätigen.
5. Prüfen, dass 01.01.2027 aus der Tagesbuchungstabelle verschwindet. Die automatische Feiertagsliste unter „Abwesenheit“ bleibt davon unberührt.
6. Anschließend eine JSON-Datensicherung herunterladen.


VERSION 4.1 – KORREKTUR MANUELLER ZEITKONTOANPASSUNGEN
- Manuelle Anpassungen können im Kontoverlauf einzeln entfernt werden (mit Sicherheitsabfrage).
- Neue manuelle Anpassungen vor dem eingestellten Zeitkonto-Start werden abgewiesen.
- Vorhandene Buchungen und Einstellungen bleiben bei einem Update im selben Browser-Speicher erhalten.
