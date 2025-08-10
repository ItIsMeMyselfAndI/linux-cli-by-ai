# 3. Working with Files and Directories

Managing files and directories is at the heart of using the Linux command line. Here you’ll learn how to create, view, copy, move, and delete files and folders, and how to manage permissions.

---

## 3.1 Creating Files and Directories

- **Create an empty file**
  ```bash
  touch filename.txt
  ```
  - **Syntax:**  
    `touch [filename]`
  - **Simple use case:**  
    Start a new file (e.g., a README or script) instantly.

- **Create a new directory**
  ```bash
  mkdir myfolder
  ```
  - **Syntax:**  
    `mkdir [directoryname]`
  - **Simple use case:**  
    Make a folder for a project or assignment.

- **Create nested directories**
  ```bash
  mkdir -p parent/child/grandchild
  ```
  - **Syntax:**  
    `mkdir -p [directory path]`
    - `-p` tells `mkdir` to create parent directories as needed.
  - **Simple use case:**  
    Set up a project structure in one command.

---

## 3.2 Copying and Moving

- **Copy a file**
  ```bash
  cp original.txt backup.txt
  ```
  - **Syntax:**  
    `cp [source] [destination]`
  - **Simple use case:**  
    Make a backup before editing a file.

- **Copy a directory (and its contents)**
  ```bash
  cp -r sourcedir targetdir
  ```
  - **Syntax:**  
    `cp -r [source directory] [destination directory]`
    - `-r` stands for "recursive" (copy all contents/folders).
  - **Simple use case:**  
    Duplicate a code or asset folder.

- **Move or rename a file/directory**
  ```bash
  mv oldname.txt newname.txt
  mv file.txt /path/to/anotherfolder/
  ```
  - **Syntax:**  
    `mv [source] [destination]`
  - **Simple use case:**  
    Rename a file or organize files into folders.

---

## 3.3 Deleting Files and Directories

- **Remove a file**
  ```bash
  rm unwanted.txt
  ```
  - **Syntax:**  
    `rm [filename]`
  - **Simple use case:**  
    Delete old or temporary files.

- **Remove an empty directory**
  ```bash
  rmdir emptyfolder
  ```
  - **Syntax:**  
    `rmdir [directoryname]`
  - **Simple use case:**  
    Delete a folder that’s no longer needed.

- **Remove a directory and all its contents (CAUTION)**
  ```bash
  rm -r foldername
  ```
  - **Syntax:**  
    `rm -r [directoryname]`
    - `-r` = recursive, deletes everything inside.
  - **Simple use case:**  
    Clean up after a project build.

---

## 3.4 Viewing File Contents

- **Show contents of a file**
  ```bash
  cat file.txt
  ```
  - **Syntax:**  
    `cat [filename]`
  - **Simple use case:**  
    Quickly read a short file.

- **Scroll through a file**
  ```bash
  less file.txt
  ```
  - **Syntax:**  
    `less [filename]`
  - **Simple use case:**  
    Read long files page by page.

- **See the start/end of a file**
  ```bash
  head file.txt     # First 10 lines
  tail file.txt     # Last 10 lines
  ```
  - **Syntax:**  
    `head [filename]` or `tail [filename]`
  - **Simple use case:**  
    Preview large files or see recent log entries.

---

## 3.5 Editing Files

- **Edit with nano (simple editor)**
  ```bash
  nano file.txt
  ```
  - **Syntax:**  
    `nano [filename]`
  - **Simple use case:**  
    Make quick changes to config or code files.

- **Edit with vim (advanced editor)**
  ```bash
  vim file.txt
  ```
  - **Syntax:**  
    `vim [filename]`
  - **Simple use case:**  
    Power users can edit files with advanced features.

---

## 3.6 File Permissions and Ownership

- **List files with permissions**
  ```bash
  ls -l
  ```
  - **Syntax:**  
    `ls -l`
  - **Simple use case:**  
    See who owns a file and who can read/write/execute it.

- **Change permissions**
  ```bash
  chmod +x script.sh      # Make executable
  chmod 644 file.txt      # Owner read/write, others read
  ```
  - **Syntax:**  
    `chmod [mode] [filename]`
    - `+x` adds execute permission
    - `644` sets specific permissions (rw-r--r--)
  - **Simple use case:**  
    Enable running a script or set file security.

- **Change owner**
  ```bash
  sudo chown newuser:newgroup file.txt
  ```
  - **Syntax:**  
    `chown [user]:[group] [filename]`
  - **Simple use case:**  
    Fix ownership after moving files between users.

---

## 3.7 Real-World Practice

1. Create a project folder and file:
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
- Use tab completion to fill out file and folder names.
- Organize files in logical directories for easier navigation.

---

**Next:** [4. Searching, Finding, and Managing Content](./04-searching-and-managing-content_Version3.md)
