# A4 – Library Manager (Prog #2)

## 1) Anforderungsliste (funktionale Anforderungen)

- Das Programm zeigt ein Hauptmenü mit Optionen (Hinzufügen, Löschen, Suchen, Anzeigen, Ausleihen, Zurückgeben, Beenden).
- Der Benutzer kann ein Buch hinzufügen (Titel, Autor, ISBN, Jahr).
- Das Programm prüft, dass die ISBN nicht leer ist und nicht doppelt existiert.
- Der Benutzer kann alle Bücher anzeigen lassen (sortiert nach Titel).
- Der Benutzer kann Bücher nach Titel oder Autor suchen (Teilwortsuche).
- Der Benutzer kann ein Buch über die ISBN löschen.
- Der Benutzer kann ein Buch ausleihen (ISBN + Name Entleiher).
- Der Benutzer kann ein Buch zurückgeben (ISBN).
- Das Programm zeigt verständliche Fehlermeldungen bei ungültigen Eingaben oder wenn ein Buch nicht gefunden wird.
- Das Programm läuft in einer Schleife, bis der Benutzer „Beenden“ auswählt.

## 2) Aktivitätsdiagramm (Textbeschreibung)

Start → Menü anzeigen → Eingabe wählen  
→ **Entscheidung (switch Auswahl)**

- **Fall: Hinzufügen**
  → Daten eingeben
  → validieren
  → speichern
  → zurück zum Menü

- **Fall: Anzeigen**
  → Liste sortieren
  → ausgeben
  → zurück zum Menü

- **Fall: Suchen**
  → Suchtext eingeben
  → Treffer berechnen
  → ausgeben
  → zurück zum Menü

- **Fall: Löschen**
  → ISBN eingeben
  → Buch finden
  → löschen oder Fehlermeldung
  → zurück zum Menü

- **Fall: Ausleihen**
  → ISBN + Name eingeben
  → prüfen ob Buch verfügbar
  → Status auf „ausgeliehen“ setzen oder Fehlermeldung
  → zurück zum Menü

- **Fall: Zurückgeben**
  → ISBN eingeben
  → Status auf „verfügbar“ setzen oder Fehlermeldung
  → zurück zum Menü

- **Fall: Beenden**
  → Ende

@startuml
title Activity Diagram - Library Manager (Prog #2)

start
repeat
:Hauptmenü anzeigen;
:Auswahl einlesen;

if (Auswahl == 1\n(Buch hinzufügen)?) then (ja)
:Titel/Autor/ISBN/Jahr einlesen;
if (ISBN leer oder doppelt?) then (ja)
:Fehlermeldung ausgeben;
else (nein)
:Buch speichern;
:Bestätigung ausgeben;
endif

elseif (Auswahl == 2\n(Alle anzeigen)?) then (ja)
:Bücher nach Titel sortieren;
:Liste ausgeben;

elseif (Auswahl == 3\n(Suchen)?) then (ja)
:Suchtext einlesen;
:Treffer berechnen;
:Treffer ausgeben;

elseif (Auswahl == 4\n(Löschen)?) then (ja)
:ISBN einlesen;
if (Buch gefunden?) then (ja)
:Buch löschen;
:Bestätigung ausgeben;
else (nein)
:Fehlermeldung ausgeben;
endif

elseif (Auswahl == 5\n(Ausleihen)?) then (ja)
:ISBN + Entleihername einlesen;
if (Buch gefunden und verfügbar?) then (ja)
:Status auf "ausgeliehen" setzen;
:Bestätigung ausgeben;
else (nein)
:Fehlermeldung ausgeben;
endif

elseif (Auswahl == 6\n(Zurückgeben)?) then (ja)
:ISBN einlesen;
if (Buch gefunden und ausgeliehen?) then (ja)
:Status auf "verfügbar" setzen;
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
