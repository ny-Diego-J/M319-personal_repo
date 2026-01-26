# D4 – Workout Tracker (Prog #3)

## 1) Komplexe Datentypen (mind. 2)

**DT1:** `ArrayList<WorkoutEntry> entries`

- Zweck: Speichert **alle** Trainingseinträge in einer Liste
- Verwendete Standard-Operationen:
  - `add()` → Eintrag hinzufügen
  - `remove()` → Eintrag löschen
  - foreach-Loop → Einträge anzeigen/filtern

**DT2:** `HashMap<String, ArrayList<WorkoutEntry>> byExercise`

- Zweck: Indexiert Einträge nach **Übung** (Übungsname → Liste von Einträgen)
- Verwendete Standard-Operationen:
  - `putIfAbsent()` → neue Übung initialisieren
  - `get()` → Liste pro Übung holen
  - `remove()` → Übung entfernen wenn Liste leer ist

**DT3 (eigener komplexer Datentyp):** `WorkoutEntry`

- Zweck: Modelliert einen Trainingseintrag als Objekt mit mehreren Attributen

---

## 2) Globale Prozessdaten (Klassenvariablen)

Diese Variablen sind global im Programm gespeichert und werden im Ablauf verwendet:

| Variable     | Datentyp                                   | Zweck                                   |
| ------------ | ------------------------------------------ | --------------------------------------- |
| `SCANNER`    | `Scanner`                                  | Liest Benutzereingaben aus der Konsole  |
| `entries`    | `ArrayList<WorkoutEntry>`                  | Speichert alle Einträge                 |
| `byExercise` | `HashMap<String, ArrayList<WorkoutEntry>>` | Index für schnelle Statistik nach Übung |
| `nextId`     | `int`                                      | Vergibt eindeutige IDs für Einträge     |

---

## 3) Methoden mit Parameterübergabe (primitive + komplexe Typen)

### Wichtige Methoden im Programm

**M1:** `addEntry(ArrayList<WorkoutEntry> entries, HashMap<String, ArrayList<WorkoutEntry>> byExercise, WorkoutEntry entry)`

- Parameter-Typen: **komplex + komplex + komplex**
- Zweck: Speichert einen Eintrag in der Gesamtliste und im Übungsindex

**M2:** `deleteEntry(ArrayList<WorkoutEntry> entries, HashMap<String, ArrayList<WorkoutEntry>> byExercise, int id)`

- Parameter-Typen: **komplex + komplex + primitiv**
- Zweck: Löscht einen Eintrag anhand ID aus beiden Datenstrukturen

**M3:** `printAllEntries(ArrayList<WorkoutEntry> entries)`

- Parameter-Typ: **komplex**
- Zweck: Gibt alle Einträge aus

**M4:** `printEntriesByDate(ArrayList<WorkoutEntry> entries, String date)`

- Parameter-Typen: **komplex + String**
- Zweck: Filtert Einträge nach Datum

**M5:** `printMaxWeight(HashMap<String, ArrayList<WorkoutEntry>> byExercise, String exercise)`

- Parameter-Typen: **komplex + String**
- Zweck: Berechnet und zeigt das maximale Gewicht einer Übung an

**M6:** `isValidEntry(int sets, int reps, double weight)`

- Parameter-Typen: **primitive**
- Zweck: Validiert Eingabewerte für einen Eintrag

---

## 4) Standardmethoden für komplexe Datentypen (Nachweis)

Im Programm werden Standardmethoden von komplexen Datentypen verwendet:

### ArrayList

- `add(entry)`
- `remove(entry)`
- Iteration mit foreach

### HashMap

- `putIfAbsent(key, new ArrayList<>())`
- `get(key)`
- `remove(key)`

---

## 5) Fazit

Das Programm erfüllt D4, weil:

- mindestens 2 komplexe Datentypen eingesetzt werden (`ArrayList`, `HashMap`)
- Methoden mit Parameterübergabe verwendet werden (primitive + komplex)
- Prozessdaten global gespeichert und klar beschrieben sind
- Standardoperationen auf den komplexen Datentypen vorkommen
