# 7. Processes and System Monitoring

Monitoring and controlling running programs (“processes”) is crucial for troubleshooting, performance tuning, and system management. The Linux CLI gives you detailed control over what runs on your system.

---

## 7.1 Viewing Running Processes

- **List all running processes:**
  ```bash
  ps aux
  ```
  - `ps` shows processes.
  - `a` = all users, `u` = user-oriented format, `x` = include processes without a terminal.

- **Dynamic real-time process viewer:**
  ```bash
  top
  ```
  - Use <kbd>q</kbd> to quit.
  - *Simple use case:*  
    See which processes are using the most CPU or memory.

- **Improved viewer with color and sorting:**
  ```bash
  htop
  ```
  - May need to install it: `sudo apt install htop`
  - *Simple use case:*  
    Interactive, easier monitoring and killing of misbehaving processes.

---

## 7.2 Finding Specific Processes

- **Search for a process by name:**
  ```bash
  ps aux | grep python
  ```
  *Simple use case:*  
  Check if your Python app is running.

- **Get process ID (PID):**
  ```bash
  pgrep -l nginx
  ```
  *Simple use case:*  
  Find the PID of a web server to restart or stop it.

---

## 7.3 Stopping and Managing Processes

- **Stop (terminate) a process by PID:**
  ```bash
  kill 12345
  ```
  - Replace `12345` with the actual PID.

- **Force-stop a process:**
  ```bash
  kill -9 12345
  ```
  - Use only if a process won’t stop normally.

- **Stop all processes by name:**
  ```bash
  pkill firefox
  ```

- **Simple use case:**  
  Kill a stuck script or server process that’s using too many resources.

---

## 7.4 Checking System Resources

- **Check free memory:**
  ```bash
  free -h
  ```
- **View disk usage:**
  ```bash
  df -h
  ```
  - *Simple use case:*  
    See if you’re running out of RAM or disk space.

- **Check disk usage of a specific folder:**
  ```bash
  du -sh /path/to/folder
  ```

---

## 7.5 Monitoring Logs

- **View a log file in real-time:**
  ```bash
  tail -f /var/log/syslog
  ```
  - *Simple use case:*  
    Watch log output while restarting a service to debug errors.

---

## 7.6 Real-World Practice

1. Check what’s running and sort by memory:
   ```bash
   top
   ```
2. Find and kill a stuck Python process:
   ```bash
   pgrep -l python
   kill <PID>
   ```
3. Check if your disk is getting full:
   ```bash
   df -h
   ```
4. Watch live server logs:
   ```bash
   tail -f /var/log/nginx/error.log
   ```

---

## 7.7 Tips and Best Practices

- Use `htop` for an easier, interactive overview.
- Be careful using `kill -9`; it forcefully ends processes and may cause data loss.
- Regularly check `df -h` and `free -h` to avoid running out of resources.
- Use log monitoring when troubleshooting or after making changes.

---

**Next:** Scripting and automation—speed up your workflow and eliminate repetitive tasks with shell scripting!