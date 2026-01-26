# D4 – Library Manager (Prog #2)

## Komplexe Datentypen

- `ArrayList<Book> books` → speichert alle Bücher (add/remove/sort/ausgeben)
- `HashMap<String, Book> isbnIndex` → ISBN → Buch (containsKey/get/put/remove)
- eigener Datentyp: `Book`

## Globale Prozessdaten

| Variable    | Typ                     | Zweck                      |
| ----------- | ----------------------- | -------------------------- |
| `SCANNER`   | `Scanner`               | Benutzereingaben           |
| `books`     | `ArrayList<Book>`       | alle Bücher                |
| `isbnIndex` | `HashMap<String, Book>` | schnelles Finden über ISBN |

## Methoden mit Parametern

- `addBook(ArrayList<Book>, HashMap<String, Book>, Book)`
- `removeBook(ArrayList<Book>, HashMap<String, Book>, String)`
- `searchBooks(ArrayList<Book>, String)`
- `borrowBook(HashMap<String, Book>, String, String)`
- `returnBook(HashMap<String, Book>, String)`
