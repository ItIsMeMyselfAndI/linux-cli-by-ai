# 4. Searching, Finding, and Managing Content

As your projects grow, quickly locating files and searching inside them becomes essential. The Linux CLI offers powerful tools to help you find what you need, even in massive codebases or directories.

---

## 4.1 Finding Files and Directories

- **Find files by name:**
  ```bash
  find /path/to/search -name "filename.txt"
  ```
  *Simple use case:*  
  You can’t remember where you saved a config file, so you search your project directory for "settings.py":
  ```bash
  find . -name "settings.py"
  ```

- **Find directories by name:**
  ```bash
  find /path/to/search -type d -name "logs"
  ```
  *Simple use case:*  
  Locate all log folders in your workspace.

---

## 4.2 Fast File Lookup with `locate`

- **Update database (recommended after adding/removing many files):**
  ```bash
  sudo updatedb
  ```
- **Locate a file anywhere on the system:**
  ```bash
  locate filename.txt
  ```
  *Simple use case:*  
  Instantly find every README.md on your machine:
  ```bash
  locate README.md
  ```

---

## 4.3 Searching Inside Files with `grep`

- **Basic search for a word:**
  ```bash
  grep "pattern" filename.txt
  ```
  *Simple use case:*  
  Find all lines containing "error" in a log file:
  ```bash
  grep "error" app.log
  ```

- **Recursive search in all files and subfolders:**
  ```bash
  grep -r "TODO" .
  ```
  *Simple use case:*  
  List all places in your codebase where you left a TODO comment.

- **Show line numbers and highlight matches:**
  ```bash
  grep -n --color "main" *.py
  ```

---

## 4.4 Counting, Sorting, and Filtering

- **Count lines, words, or characters:**
  ```bash
  wc -l filename.txt     # Line count
  wc -w filename.txt     # Word count
  wc -c filename.txt     # Character count
  ```
  *Simple use case:*  
  Count the number of lines in a data or log file.

- **Sort and remove duplicate lines:**
  ```bash
  sort file.txt | uniq
  ```
  *Simple use case:*  
  Get a list of unique usernames from a file.

- **Extract a column from delimited text:**
  ```bash
  cut -d',' -f2 data.csv
  ```
  *Simple use case:*  
  Show only the email addresses (second column) from a CSV export.

---

## 4.5 Advanced Text Processing: `awk` and `sed`

- **Extract fields with awk:**
  ```bash
  awk '{print $1, $3}' file.txt
  ```
  *Simple use case:*  
  Print the first and third columns of a server log.

- **Find and replace text with sed:**
  ```bash
  sed 's/old/new/g' file.txt
  ```
  *Simple use case:*  
  Replace all instances of "localhost" with "127.0.0.1" in a config.

---

## 4.6 Practice: Real-World Examples

1. **Find all Python files in your project:**
   ```bash
   find . -name "*.py"
   ```
2. **Search for a function definition in your codebase:**
   ```bash
   grep -rn "def process_data" .
   ```
3. **List unique error codes in a log:**
   ```bash
   grep "ERROR" app.log | cut -d' ' -f3 | sort | uniq
   ```

---

## 4.7 Tips and Best Practices

- Use `grep --color` for easier reading of search results.
- Combine commands with pipes (`|`) for powerful oneliners.
- For huge projects, `locate` is much faster than `find` (after updating the database).
- Always test your search/filter command on a small file first if you’re unsure.

---

**Next:** Package management—installing, updating, and removing software with apt!