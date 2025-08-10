# 8. Scripting and Automation

Linux shines when it comes to automating repetitive tasks. Shell scripts let you run a series of commands in sequence, making your workflow more efficient and less error-prone.

---

## 8.1 What is a Shell Script?

- A **shell script** is a text file containing a list of commands for the shell to run.
- By convention, scripts end in `.sh` (e.g., `deploy.sh`).

*Simple use case:*  
Automatically back up your project folder every day instead of typing the copy command manually.

---

## 8.2 Creating and Running a Simple Script

- **Create a new script:**
  ```bash
  nano backup.sh
  ```
  Add this content:
  ```bash
  #!/bin/bash
  cp -r ~/projects/myapp ~/backups/myapp-$(date +%Y%m%d)
  echo "Backup completed!"
  ```
  - `#!/bin/bash` tells the system to use bash as the interpreter.
  - `cp -r` copies the project folder.
  - `$(date +%Y%m%d)` adds today’s date to the backup folder name.

- **Make the script executable:**
  ```bash
  chmod +x backup.sh
  ```

- **Run the script:**
  ```bash
  ./backup.sh
  ```

---

## 8.3 Adding Variables and Arguments

- **Variables:**
  ```bash
  NAME="World"
  echo "Hello, $NAME!"
  ```
  *Simple use case:*  
  Customize script output or logic.

- **Using arguments:**
  ```bash
  #!/bin/bash
  echo "First argument: $1"
  ```
  Run it:
  ```bash
  ./myscript.sh test
  ```
  Output:
  ```
  First argument: test
  ```

---

## 8.4 Loops and Conditionals

- **For loop:**
  ```bash
  for file in *.txt; do
    echo "Processing $file"
  done
  ```
  *Simple use case:*  
  Apply an action (like compression) to all `.txt` files in a folder.

- **If statement:**
  ```bash
  if [ -f config.yaml ]; then
    echo "Config exists."
  else
    echo "No config found."
  fi
  ```
  *Simple use case:*  
  Check if a config file exists before running a script.

---

## 8.5 Scheduling Tasks with Cron

- **Edit your crontab:**
  ```bash
  crontab -e
  ```
- **Run a script every day at 2am:**
  ```
  0 2 * * * /home/youruser/backup.sh
  ```
  *Simple use case:*  
  Automate daily backups, updates, or reports.

---

## 8.6 Real-World Practice

1. Write a script to clean up old logs:
   ```bash
   #!/bin/bash
   find ~/logs -name "*.log" -mtime +7 -delete
   ```
2. Make it executable and run it:
   ```bash
   chmod +x cleanlogs.sh
   ./cleanlogs.sh
   ```
3. Schedule it weekly in cron.

---

## 8.7 Tips and Best Practices

- Always add `#!/bin/bash` as the first line of your scripts.
- Use `chmod +x` to make scripts executable.
- Test scripts manually before scheduling with cron.
- Comment your scripts for future you (or teammates)!

---

**Next:** System security basics—user management, permissions, and best practices for keeping your system safe!