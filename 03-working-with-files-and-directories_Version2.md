# 3. Working with Files and Directories

Managing files and directories is one of the most common tasks on the Linux command line. Here you’ll learn how to create, view, copy, move, and delete files/folders, along with basic permissions.

---

## 3.1 Creating Files and Directories

- **Create an empty file:**
  ```bash
  touch filename.txt
  ```
  *Simple use case:* Start a new README or script file.

- **Create a new directory:**
  ```bash
  mkdir myfolder
  ```
  *Simple use case:* Make a new folder for a project or assignment.

- **Create nested directories:**
  ```bash
  mkdir -p parent/child/grandchild
  ```
  *Simple use case:* Set up a project structure in one command.

---

## 3.2 Copying and Moving

- **Copy a file:**
  ```bash
  cp original.txt backup.txt
  ```
  *Simple use case:* Make a backup before editing a file.

- **Copy a directory (and contents):**
  ```bash
  cp -r sourcedir targetdir
  ```
  *Simple use case:* Duplicate a code or asset folder.

- **Move (or rename) a file or directory:**
  ```bash
  mv oldname.txt newname.txt
  mv file.txt /path/to/anotherfolder/
  ```
  *Simple use case:* Rename a file or organize files into folders.

---

## 3.3 Deleting Files and Directories

- **Remove a file:**
  ```bash
  rm unwanted.txt
  ```
  *Simple use case:* Delete old or temporary files.

- **Remove an empty directory:**
  ```bash
  rmdir emptyfolder
  ```

- **Remove a directory and all its contents (CAUTION):**
  ```bash
  rm -r foldername
  ```
  *Simple use case:* Clean up after a project build.

**Syntax note:**  
- `-r` stands for “recursive” (needed for deleting directories with files inside).

---

## 3.4 Viewing File Contents

- **Show contents of a file:**
  ```bash
  cat file.txt
  ```

- **Scroll through a file:**
  ```bash
  less file.txt
  ```
  *Simple use case:* Read log files or documentation.

- **See the start/end of a file:**
  ```bash
  head file.txt    # First 10 lines
  tail file.txt    # Last 10 lines
  ```

---

## 3.5 Editing Files

- **Edit with nano (simple editor):**
  ```bash
  nano file.txt
  ```
  *Simple use case:* Make quick changes to config or code files.

- **Edit with vim (advanced editor):**
  ```bash
  vim file.txt
  ```

---

## 3.6 File Permissions and Ownership

- **List files with permissions:**
  ```bash
  ls -l
  ```
  Output example:
  ```
  -rw-r--r-- 1 user user 1234 Aug 10 09:00 notes.txt
  ```
  - First column: File type and permissions
  - `d` = directory, `-` = file
  - `rwx` = read, write, execute

- **Change permissions:**
  ```bash
  chmod +x script.sh      # Make script executable
  chmod 644 file.txt      # Set read/write for owner, read for others
  ```
  *Simple use case:* Enable running a script or lock down a config file.

- **Change owner:**
  ```bash
  sudo chown newuser:newgroup file.txt
  ```
  *Simple use case:* Fix ownership after moving files between users.

---

## 3.7 Real-World Practice

1. Create a folder for a new project:
   ```bash
   mkdir ~/projects/demo
   cd ~/projects/demo
   touch README.md
   ```
2. Copy a template file:
   ```bash
   cp ~/templates/base.py .
   ```
3. Delete the folder after testing:
   ```bash
   cd ~
   rm -r ~/projects/demo
   ```

---

## 3.8 Tips and Gotchas

- Double-check before running `rm -r`—deletions are permanent!
- Use tab completion to quickly fill out file and folder names.
- Organize files in logical directories for easier navigation and management.

---

**Next:** Searching and managing content—find files, search inside files, and manipulate data efficiently!