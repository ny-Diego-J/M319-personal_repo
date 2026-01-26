# A4 – Workout Tracker (Prog #3)

## 1) Anforderungsliste (funktionale Anforderungen)

- Das Programm zeigt ein Hauptmenü (Eintrag hinzufügen, Anzeigen, Anzeigen nach Datum, Statistik, Löschen, Beenden).
- Der Benutzer kann einen Trainingseintrag hinzufügen (Datum, Übung, Sätze, Wiederholungen, Gewicht).
- Das Programm prüft Eingaben: Sätze ≥ 1, Wiederholungen ≥ 1, Gewicht ≥ 0.
- Jeder Eintrag bekommt eine eindeutige ID, damit man ihn löschen kann.
- Der Benutzer kann alle Einträge anzeigen lassen.
- Der Benutzer kann Einträge für ein bestimmtes Datum filtern und anzeigen lassen.
- Der Benutzer kann für eine Übung die Statistik „maximales Gewicht“ anzeigen lassen.
- Der Benutzer kann einen Eintrag anhand der ID löschen.
- Das Programm gibt Fehlermeldungen aus, wenn Eingaben ungültig sind oder keine Daten vorhanden sind.
- Das Programm läuft in einer Schleife, bis der Benutzer „Beenden“ auswählt.

## 2) Aktivitätsdiagramm (Textbeschreibung)

Start → Menü anzeigen → Eingabe wählen
→ **Entscheidung (switch Auswahl)**

- **Fall: Eintrag hinzufügen**
  → Daten eingeben
  → validieren
  → speichern
  → zurück zum Menü

- **Fall: Alle anzeigen**
  → Einträge ausgeben
  → zurück zum Menü

- **Fall: Nach Datum anzeigen**
  → Datum eingeben
  → Einträge filtern
  → ausgeben
  → zurück zum Menü

- **Fall: Statistik anzeigen**
  → Übung eingeben
  → maximales Gewicht berechnen
  → Ergebnis ausgeben
  → zurück zum Menü

- **Fall: Eintrag löschen**
  → ID eingeben
  → Eintrag finden
  → löschen oder Fehlermeldung
  → zurück zum Menü

- **Fall: Beenden**
  → Ende

@startuml
title Activity Diagram - Workout Tracker (Prog #3)

start
repeat
:Hauptmenü anzeigen;
:Auswahl einlesen;

if (Auswahl == 1\n(Eintrag hinzufügen)?) then (ja)
:Datum/Übung/Sätze/Wdh/Gewicht einlesen;
if (Eingaben ungültig?\n(Sätze<1 oder Wdh<1 oder Gewicht<0)) then (ja)
:Fehlermeldung ausgeben;
else (nein)
:ID vergeben;
:Eintrag speichern;
:Bestätigung ausgeben;
endif

elseif (Auswahl == 2\n(Alle anzeigen)?) then (ja)
if (Einträge vorhanden?) then (ja)
:Alle Einträge ausgeben;
else (nein)
:Hinweis "keine Einträge" ausgeben;
endif

elseif (Auswahl == 3\n(Nach Datum anzeigen)?) then (ja)
:Datum einlesen;
:Einträge filtern;
if (Treffer vorhanden?) then (ja)
:Treffer ausgeben;
else (nein)
:Hinweis "keine Treffer" ausgeben;
endif

elseif (Auswahl == 4\n(Statistik)?) then (ja)
:Übung einlesen;
if (Übung existiert?) then (ja)
:Max-Gewicht berechnen;
:Ergebnis ausgeben;
else (nein)
:Hinweis "keine Daten" ausgeben;
endif

elseif (Auswahl == 5\n(Löschen)?) then (ja)
:ID einlesen;
if (ID gefunden?) then (ja)
:Eintrag löschen;
:Bestätigung ausgeben;
else (nein)
:Fehlermeldung ausgeben;
endif

elseif (Auswahl == 0\n(Beenden)?) then (ja)
break
else (ungültig)
:Fehlermeldung ausgeben;
endif

repeat while (Weiter?) is (ja)

stop
@enduml
