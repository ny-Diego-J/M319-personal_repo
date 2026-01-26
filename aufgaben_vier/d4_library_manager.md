# D4 – Library Manager (Prog #2)

## 1) Komplexe Datentypen (mind. 2)

**DT1:** `ArrayList<Book> books`

- Zweck: Speichert **alle Bücher** in einer Liste
- Verwendete Standard-Operationen:
  - `add()` → Buch hinzufügen
  - `remove()` → Buch löschen
  - `sort()` → Bücher sortieren (z.B. nach Titel)
  - foreach-Loop → Bücher anzeigen

**DT2:** `HashMap<String, Book> isbnIndex`

- Zweck: Indexiert Bücher nach **ISBN** (ISBN → Book Objekt) für schnellen Zugriff
- Verwendete Standard-Operationen:
  - `containsKey(isbn)` → prüfen ob ISBN bereits existiert
  - `put(isbn, book)` → Buch im Index speichern
  - `get(isbn)` → Buch schnell finden
  - `remove(isbn)` → Buch aus Index entfernen

**DT3 (eigener komplexer Datentyp):** `Book`

- Zweck: Modelliert ein Buch als Objekt mit mehreren Eigenschaften

---

## 2) Globale Prozessdaten (Klassenvariablen)

Diese Variablen sind global im Programm gespeichert und werden im Ablauf verwendet:

| Variable    | Datentyp                | Zweck                                  |
| ----------- | ----------------------- | -------------------------------------- |
| `SCANNER`   | `Scanner`               | Liest Benutzereingaben aus der Konsole |
| `books`     | `ArrayList<Book>`       | Speichert alle Bücher                  |
| `isbnIndex` | `HashMap<String, Book>` | Schnelles Finden von Büchern über ISBN |

---

## 3) Methoden mit Parameterübergabe (primitive + komplexe Typen)

### Wichtige Methoden im Programm

**M1:** `addBook(ArrayList<Book> books, HashMap<String, Book> isbnIndex, Book book)`

- Parameter-Typen: **komplex + komplex + komplex**
- Zweck: Fügt ein neues Buch hinzu (Liste + Index)

**M2:** `removeBook(ArrayList<Book> books, HashMap<String, Book> isbnIndex, String isbn)`

- Parameter-Typen: **komplex + komplex + String**
- Zweck: Löscht ein Buch anhand ISBN aus beiden Datenstrukturen

**M3:** `searchBooks(ArrayList<Book> books, String query)`

- Parameter-Typen: **komplex + String**
- Zweck: Sucht Bücher nach Titel oder Autor (Teilwortsuche)

**M4:** `borrowBook(HashMap<String, Book> isbnIndex, String isbn, String borrowerName)`

- Parameter-Typen: **komplex + String + String**
- Zweck: Setzt ein Buch auf ausgeliehen und speichert den Entleihernamen

**M5:** `returnBook(HashMap<String, Book> isbnIndex, String isbn)`

- Parameter-Typen: **komplex + String**
- Zweck: Gibt ein Buch zurück (Status auf verfügbar)

**M6:** `printAllBooks(ArrayList<Book> books)`

- Parameter-Typ: **komplex**
- Zweck: Sortiert und gibt alle Bücher aus

---

## 4) Standardmethoden für komplexe Datentypen (Nachweis)

Im Programm werden Standardmethoden von komplexen Datentypen verwendet:

### ArrayList

- `add(book)`
- `remove(book)`
- `sort(...)`
- Iteration mit foreach

### HashMap

- `containsKey(isbn)`
- `put(isbn, book)`
- `get(isbn)`
- `remove(isbn)`

---

## 5) Fazit

Das Programm erfüllt D4, weil:

- mindestens 2 komplexe Datentypen eingesetzt werden (`ArrayList`, `HashMap`)
- Methoden mit Parameterübergabe verwendet werden (primitive + komplex)
- Prozessdaten global gespeichert und klar beschrieben sind
- Standardoperationen auf den komplexen Datentypen vorkommen
