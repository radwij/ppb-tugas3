# NoteKeeper - Flutter SQFlite Note-Taking App

**I Putu Raditya Partha Wijaya / 5025221210** 

**NoteKeeper** is a Flutter-based mobile application that allows users to manage personal notes with priority levels, using local storage via SQLite through the `sqflite` plugin. This app demonstrates full CRUD (Create, Read, Update, Delete) functionality with a simple and intuitive UI.

---

## Features

- Add new notes with title, description, and priority
- Edit or delete existing notes
- Notes are saved locally using SQLite
- Priority levels visualized with color and icons
- Responsive and reactive UI using `setState`

---

## How the App Works

### 1. `note.dart` – The Note Model

This file defines the `Note` class, which represents each note. It includes fields like:
- `id`: The unique identifier
- `title`: Title of the note
- `description`: Content of the note
- `priority`: Either 1 (High) or 2 (Low)
- `date`: Timestamp string when the note was saved

It includes:
- Two constructors (`Note` and `Note.withId`)
- Getters and setters
- `toMap()` method to convert a note to a database-friendly map
- `fromMapObject()` to recreate a `Note` from a database map

---

### 2. `note_detail.dart` – Note Editor Screen

This file provides the screen for creating or editing a note.

**Features:**
- Dropdown for selecting priority
- TextFields for entering title and description
- Save and Delete buttons
- Alert dialogs for operation results

**Logic:**
- If the note has an ID, the app performs an `UPDATE` on save
- If the ID is null, it performs an `INSERT`
- Deleting a note checks whether it already exists in the database

Methods:
- `updateTitle()` and `updateDescription()` update the `Note` object
- `_save()` stores the note
- `_delete()` removes the note

---

### 3. `note_list.dart` – List Display Screen

This screen displays all saved notes in a scrollable list.

**Features:**
- Each note is shown with its title, date, and priority badge
- Delete icon to remove a note
- FAB to add a new note
- Tap on a note to edit

**Logic:**
- `updateListView()` fetches notes from the database and updates the UI
- `navigateToDetail()` moves to the detail screen and awaits result
- `_delete()` deletes the selected note from the database
- `getPriorityColor()` and `getPriorityIcon()` customize the visuals

---

### 4. `main.dart` – Entry Point

This file runs the application and sets the theme and home screen.

```dart
void main() {
  runApp(MyApp());
}
```


---

### 5. Referensi

https://github.com/smartherd/Flutter-Demos
