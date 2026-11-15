# Semantiktest Web

Web-Nachbau des Windows-Programms `Semantiktest.exe` (WBW, Version 2.0) zur Semantik-Analyse.

- `semantiktest.html` – eigenständige Datei, läuft direkt im Browser (auch iPhone/Safari, offline nach dem ersten Laden der Schriften).
- `index.html` – gleicher Inhalt als Artifact-Seite.

## Methode (aus Programm und Daten rekonstruiert)

- 24 Gegensatzpaare (hoch–tief … gut–schlecht), Skala 1–7.
- Koordinaten: x/y = Pearson-Korrelation des Antwortprofils mit zwei festen Faktorprofilen (F1, F2).
  Gegen 3.535 Originalprofile geprüft: alle Koordinaten auf 2 Nachkommastellen identisch.
- Profile ohne Streuung (z. B. lauter 4er) liegen im Nullpunkt.
- Quadranten: x>0 & y>0 Kreativität, x>0 & y≤0 Passivität, x≤0 & y≤0 Stupidität, x≤0 & y>0 Aggressivität.
- Durchschnittsprofil: Korrelation des gemittelten Antwortprofils, nächster Referenzbegriff per euklidischer Distanz.
- Bereinigung wie Excel-Makro: Profile mit x² + y² < 0,3 werden ausgeblendet (alternativ Radius 0,3 laut Leitfaden).

## Daten

Import von `.ist`-Dateien des Originalprogramms, CSV-Exporten (24 Werte je Zeile + Bereich/Position/Beschäftigung) oder 24-stelligen Ziffernfolgen. Export als `.ist` oder CSV mit Koordinaten.
Profile werden nur lokal im Browser gespeichert.

## Semantiktest Live (Pilot)

`live.html` – Online-Befragung mit gemeinsamer Datenbank (claude.ai Artifact):

- Leitung (Editor/Owner): Befragungen anlegen, öffnen/schließen, Link und QR-Code, Live-Diagramm,
  Filter mit Mindestgruppengröße, Vorher/Nachher-Vergleich, Import alter .ist/.csv-Daten, Export, Ergebnis für Teilnehmer freigeben.
- Teilnehmer (Contributor): Fragebogen am Handy ausfüllen, eigene Einordnung sehen, Antwort ändern solange offen.
- Zugriffsregeln: `surveys` lesen alle / schreiben Leitung; `responses` je Person nur die eigene Antwort,
  alle Antworten sieht nur die Leitung; `imports` nur Leitung.
