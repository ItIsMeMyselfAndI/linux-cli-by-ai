# 2. Getting Started: The Terminal and Basic Navigation

Learning to move around your system with the command line is the first step to becoming comfortable on Linux. This section will show you how to open a terminal, understand the prompt, and navigate directories efficiently.

---

## 2.1 Opening the Terminal

- **On Ubuntu/Debian Desktop:**
  - Press <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>T</kbd>
  - Or, search for “Terminal” in your applications menu.
- **On a remote server:**
  - Use SSH to connect:
    ```bash
    ssh youruser@yourserver.com
    ```
- **Simple use case:**  
  Open the terminal to run updates, edit files, or deploy code from anywhere.

---

## 2.2 Understanding the Prompt

- The prompt typically looks like:
  ```
  youruser@hostname:~/current/directory$
  ```
  - `youruser` is your username.
  - `hostname` is your computer/server name.
  - `~/current/directory` shows your current location in the filesystem.

**Syntax note:**  
Anything you type after the `$` is a command.

- **Simple use case:**  
  If your prompt shows `~/projects/myapp`, you know you're inside your project folder.

---

## 2.3 Navigating Directories

- **Show your current directory:**
  ```bash
  pwd
  ```
  (`pwd` = print working directory)

- **List files and folders:**
  ```bash
  ls
  ls -l        # Detailed list with permissions, size, dates
  ls -a        # Show hidden files (starting with .)
  ```

- **Change directory:**
  ```bash
  cd /path/to/folder
  cd ..        # Go up one directory level
  cd           # Go to your home directory
  cd ~/Desktop # Go to your Desktop folder
  cd -         # Jump back to previous directory
  ```

**Syntax note:**  
- `cd` changes your current directory.
- `..` means “parent directory.”
- `~` means your home directory.

- **Simple use case:**  
  You want to edit a script on your Desktop:
  ```bash
  cd ~/Desktop
  nano myscript.sh
  ```

---

## 2.4 Using Path Shortcuts and Tab Completion

- `.` : current directory (e.g., `./script.sh` runs a script in the current folder)
- `..` : parent directory
- `~` : home directory
- `-` : previous directory

- **Tab Completion:**  
  Press <kbd>Tab</kbd> while typing a file or directory name to auto-complete it.  
  Example:
  ```
  cd Doc<Tab>
  ```
  will auto-complete to `Documents` if that folder exists.

- **Simple use case:**  
  Quickly navigate or run scripts without typing full names.

---

## 2.5 Viewing a Directory Tree

- **Show a tree of files and folders:**
  ```bash
  sudo apt install tree   # Install tree if you don't have it
  tree .
  ```
- **Simple use case:**  
  Visualize the structure of your codebase or a project folder.

---

## 2.6 Command Line Syntax Recap

- **General format:**
  ```
  command [options] [arguments]
  ```
  - Example:
    ```bash
    ls -lh /var/log
    ```
    - `ls` is the command (list directory)
    - `-lh` are the options (long format, human-readable sizes)
    - `/var/log` is the argument (directory to list)

---

## 2.7 Real-World Practice

1. Open your terminal.
2. Use `pwd` to see your current location.
3. Use `ls` and `ls -l` to list files.
4. Use `cd` to move into your project folder.
5. Use `cd ..` to go up, and `cd -` to switch between folders.

---

## 2.8 Tips and Best Practices

- Use tab completion and arrow keys for speed.
- Keep your home and project folders organized for easier navigation.
- Don’t be afraid to explore—navigation commands are safe!

---

**Next:** Working with files and directories—create, copy, move, delete, and edit using the CLI!