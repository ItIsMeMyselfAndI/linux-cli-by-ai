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
    - **Syntax:**  
      `ssh username@hostname`
    - **Simple use case:**  
      Remotely manage a server or codebase from your own computer.

---

## 2.2 Understanding the Prompt

- The prompt typically looks like:
  ```
  youruser@hostname:~/current/directory$
  ```
  - `youruser` is your username.
  - `hostname` is your computer/server name.
  - `~/current/directory` shows your current location in the filesystem.
- **Syntax:**  
  The `$` indicates you’re a normal user (not root).

**Simple use case:**  
If your prompt shows `~/projects/myapp`, you know you're inside your project folder.

---

## 2.3 Navigating Directories

- **Show your current directory:**
  ```bash
  pwd
  ```
  - **Syntax:**  
    `pwd` stands for “print working directory”; no options needed.
  - **Simple use case:**  
    Find out exactly where you are in the filesystem.

- **List files and folders:**
  ```bash
  ls
  ls -l        # Detailed list with permissions, size, dates
  ls -a        # Show hidden files (starting with .)
  ```
  - **Syntax:**  
    `ls [options] [directory]`
    - `-l` = long/detailed format
    - `-a` = show all, including hidden files
  - **Simple use case:**  
    See what files and folders are in the current directory.

- **Change directory:**
  ```bash
  cd /path/to/folder
  cd ..        # Go up one directory level
  cd           # Go to your home directory
  cd ~/Desktop # Go to your Desktop folder
  cd -         # Jump back to previous directory
  ```
  - **Syntax:**  
    `cd [directory]`
    - `..` = parent directory
    - `~` = home directory
    - `-` = previous directory
  - **Simple use case:**  
    Move between project folders, your home, or up and down the directory tree.

---

## 2.4 Using Path Shortcuts and Tab Completion

- `.` : current directory (e.g., `./script.sh` runs a script in the current folder)
- `..` : parent directory
- `~` : home directory
- `-` : previous directory

- **Tab Completion:**  
  Press <kbd>Tab</kbd> while typing a file or directory name to auto-complete it.
  - **Syntax:**  
    Start typing, then press <kbd>Tab</kbd> to fill in the rest.
  - **Simple use case:**  
    Quickly navigate or run scripts without typing full names.

---

## 2.5 Viewing a Directory Tree

- **Show a tree of files and folders:**
  ```bash
  sudo apt install tree   # Install tree if you don't have it
  tree .
  ```
  - **Syntax:**  
    `tree [directory]`
  - **Simple use case:**  
    Visualize the structure of your codebase or a project folder.

---

## 2.6 Command Line Syntax Recap

- **General format:**
  ```
  command [options] [arguments]
  ```
  - **Example:**
    ```bash
    ls -lh /var/log
    ```
    - `ls` is the command (list directory)
    - `-lh` are the options (long format, human-readable sizes)
    - `/var/log` is the argument (directory to list)
  - **Simple use case:**  
    List log files with their sizes in a readable format.

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

**Next:** [3. Working with Files and Directories](./03-working-with-files-and-directories_Version3.md)
