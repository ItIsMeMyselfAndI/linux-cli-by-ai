# 7. Processes and System Monitoring

Monitoring, controlling, and understanding running programs (“processes”) is critical for troubleshooting, performance tuning, and daily system management. The Linux command line gives you precise tools for these tasks.

---

## 7.1 Viewing Running Processes

- **List all running processes**
  ```bash
  ps aux
  ```
  - **Syntax:**  
    `ps aux`  
    - `ps`: process status  
    - `a`: show processes for all users  
    - `u`: display the user/owner  
    - `x`: show processes without a controlling terminal  
  - **Simple use case:**  
    See every process running on your system, including background services.

- **Dynamic, real-time process viewer**
  ```bash
  top
  ```
  - **Syntax:**  
    `top`  
    Shows a live updating list of processes, sorted by CPU usage.
  - **Simple use case:**  
    Find out which processes are using the most CPU or memory right now.

- **Interactive process viewer (with color and more features)**
  ```bash
  htop
  ```
  - **Syntax:**  
    `htop`  
    Like `top`, but interactive—navigate with arrows, kill processes, sort, etc.  
    May require installation: `sudo apt install htop`
  - **Simple use case:**  
    Easily monitor and manage processes through a user-friendly interface.

---

## 7.2 Finding Specific Processes

- **Search for a process by name**
  ```bash
  ps aux | grep python
  ```
  - **Syntax:**  
    `ps aux | grep [pattern]`  
    - Pipes (`|`) output of `ps aux` to `grep`, which searches for matching lines.
  - **Simple use case:**  
    Check if your Python application is running.

- **Get process ID (PID) by name**
  ```bash
  pgrep -l nginx
  ```
  - **Syntax:**  
    `pgrep -l [name]`  
    - `-l` option shows process names alongside their PIDs.
  - **Simple use case:**  
    Find the PID of a web server to restart or stop it.

---

## 7.3 Stopping and Managing Processes

- **Terminate (stop) a process by PID**
  ```bash
  kill 12345
  ```
  - **Syntax:**  
    `kill [PID]`  
    - `PID` is the process ID number.
  - **Simple use case:**  
    Stop a stuck or runaway program.

- **Force-terminate a process**
  ```bash
  kill -9 12345
  ```
  - **Syntax:**  
    `kill -9 [PID]`  
    - `-9` sends the SIGKILL signal, which cannot be ignored.
  - **Simple use case:**  
    Forcefully end a process that won’t stop with a regular kill.

- **Stop all processes by name**
  ```bash
  pkill firefox
  ```
  - **Syntax:**  
    `pkill [name]`  
    - Sends the default TERM signal to all matching processes.
  - **Simple use case:**  
    Close all browser windows at once.

---

## 7.4 Checking System Resources

- **Show free and used memory**
  ```bash
  free -h
  ```
  - **Syntax:**  
    `free -h`  
    - `-h` means “human-readable” sizes (MB, GB).
  - **Simple use case:**  
    Check if you’re running out of RAM.

- **View disk space usage**
  ```bash
  df -h
  ```
  - **Syntax:**  
    `df -h`  
    - `-h` for human-readable output.
  - **Simple use case:**  
    See if your hard drive is almost full.

- **Check disk usage of a specific folder**
  ```bash
  du -sh /path/to/folder
  ```
  - **Syntax:**  
    `du -sh [directory]`  
    - `-s` summarizes, `-h` for human-readable.
  - **Simple use case:**  
    Find out how much space a project or folder is using.

---

## 7.5 Monitoring Logs

- **View a log file in real-time**
  ```bash
  tail -f /var/log/syslog
  ```
  - **Syntax:**  
    `tail -f [file]`  
    - `-f` means “follow”—shows new lines as they’re written.
  - **Simple use case:**  
    Debug a service by watching its log as you restart it.

---

## 7.6 Real-World Practice

1. **Check what’s running and sort by memory:**
   ```bash
   top
   ```
2. **Find and kill a stuck Python process:**
   ```bash
   pgrep -l python
   kill <PID>
   ```
3. **Check if your disk is getting full:**
   ```bash
   df -h
   ```
4. **Watch live server logs:**
   ```bash
   tail -f /var/log/nginx/error.log
   ```

---

## 7.7 Tips and Best Practices

- Use `htop` for an easier, interactive overview.
- Avoid using `kill -9` unless necessary—it can cause data loss.
- Regularly check `df -h` and `free -h` to prevent resource exhaustion.
- Monitor logs when troubleshooting or after making changes.

---

**Next:** [8. Scripting and Automation](./08-scripting-and-automation_Version2.md)
