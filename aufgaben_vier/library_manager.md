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

![uml](library_manager_uml.png)
