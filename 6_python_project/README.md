# 📔 Personal Journal Manager — Python File Handling Project

A console-based journal application demonstrating file I/O, exception handling, and object-oriented design — letting users add, view, search, and delete timestamped journal entries stored in a text file.

---

## 📌 Project Overview

| Property | Details |
|---|---|
| **Language** | Python 3 (Jupyter Notebook) |
| **File** | `6_fileoperator.ipynb` |
| **Type** | Console-based, menu-driven file management application |
| **Key Concepts** | File I/O (`open` modes: `x`, `a`, `r`), Exception Handling, Classes, `datetime`, `os` module |

---

## 🏗️ Class Structure

| Class | Purpose |
|---|---|
| `JournalManager` | Encapsulates all journal operations — adding, viewing, searching, and deleting entries — against a text file (`journal.txt` by default) |

---

## 🧩 Core Methods

| Method | Purpose |
|---|---|
| `add_entry()` | Prompts for a journal entry, timestamps it with `datetime.now()`, creates the file if it doesn't exist (`"x"` mode), then appends the entry (`"a"` mode) |
| `view_entries()` | Opens the file in read mode (`"r"`) and prints all entries, or a friendly message if the file is empty |
| `search_entry()` | Reads all lines, reconstructs individual entries by splitting on blank lines, and prints any entry containing the user's keyword (case-insensitive) |
| `delete_entries()` | Confirms with the user before deleting the entire journal file using `os.remove()` |

---

## ⚙️ How It Works

The program runs a `main()` loop offering five options:

| Option | Action |
|---|---|
| 1 | Add a New Entry |
| 2 | View All Entries |
| 3 | Search for an Entry |
| 4 | Delete All Entries |
| 5 | Exit |

Each entry is saved with a timestamp, e.g.:

```
[2026-02-19 15:36:16]
hello prerita
```

---

## 🧪 Concepts Practiced

- Using different **file open modes** purposefully: `"x"` to safely create a file only if it doesn't already exist, `"a"` to append without overwriting, and `"r"` to read
- Structuring file operations inside a **class** to keep the filename and behavior bundled together
- **Exception handling** with targeted `except` blocks for `FileNotFoundError`, `PermissionError`, and a generic fallback `Exception`
- Using `os.path.exists()` to check for a file before attempting to read or delete it
- Timestamping records using `datetime.now().strftime(...)`
- Parsing a flat text file back into structured "entries" by tracking blank lines as separators
- Case-insensitive substring search across saved entries
- Requiring explicit user confirmation (`"yes"/"no"`) before a destructive action (deleting all entries)

---

## ▶️ How to Run

```bash
jupyter notebook 6_fileoperator.ipynb
```

Or convert and run as a script:

```bash
jupyter nbconvert --to script 6_fileoperator.ipynb
python 6_fileoperator.py
```

Use the menu to add, view, search, or delete journal entries stored in `journal.txt`.

---

## 🚧 Known Limitations & Improvement Opportunities

| Issue | Explanation | Suggested Fix |
|---|---|---|
| Last entry can be missed by search if file doesn't end in a blank line | `search_entry()` only finalizes an entry when it hits a blank line separator; if the file's final entry isn't followed by one, it won't be included in the search | Add a final check after the loop to flush any remaining `current_entry` content |
| No way to delete a single entry | `delete_entries()` only supports wiping the entire journal, not removing one specific entry | Add an option to search for an entry and delete just that match |
| Journal file path is fixed relative to where the script runs | `filename="journal.txt"` is relative, so entries could end up in different locations depending on the working directory | Use an absolute path (e.g. via `os.path.expanduser("~/journal.txt")`) for consistent storage location |

---

## 💡 What I Learned

- Practical differences between file modes (`"x"`, `"a"`, `"r"`) and when to use each safely
- How to wrap file operations in a class to keep related behavior and state (the filename) together
- Writing **targeted exception handling** — catching specific errors like `FileNotFoundError` and `PermissionError` before falling back to a generic handler
- How to reconstruct structured records from a flat text file using blank lines as a delimiter
- The importance of **confirming destructive actions** (like deleting all data) before executing them
- Using `datetime` to timestamp real-world records in a human-readable format

---

## 📁 Repository Contents

```
personal-journal-manager/
│
├── 6_fileoperator.ipynb   # Main Jupyter Notebook
└── README.md               # Project documentation
```

---

## 👤 Author

**Prerita Morashiya**
