# D4 – Workout Tracker (Prog #3)

## Komplexe Datentypen

- `ArrayList<WorkoutEntry> entries` → alle Einträge (add/remove/anzeigen)
- `HashMap<String, ArrayList<WorkoutEntry>> byExercise` → Übung → Einträge
- eigener Datentyp: `WorkoutEntry`

## Globale Prozessdaten

| Variable     | Typ                                        | Zweck               |
| ------------ | ------------------------------------------ | ------------------- |
| `SCANNER`    | `Scanner`                                  | Benutzereingaben    |
| `entries`    | `ArrayList<WorkoutEntry>`                  | alle Einträge       |
| `byExercise` | `HashMap<String, ArrayList<WorkoutEntry>>` | Index für Statistik |
| `nextId`     | `int`                                      | eindeutige IDs      |

## Methoden mit Parametern

- `addEntry(ArrayList<WorkoutEntry>, HashMap<String, ArrayList<WorkoutEntry>>, WorkoutEntry)`
- `deleteEntry(ArrayList<WorkoutEntry>, HashMap<String, ArrayList<WorkoutEntry>>, int)`
- `printEntriesByDate(ArrayList<WorkoutEntry>, String)`
- `printMaxWeight(HashMap<String, ArrayList<WorkoutEntry>>, String)`
