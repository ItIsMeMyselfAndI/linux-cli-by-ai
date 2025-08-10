# 10. Troubleshooting and Recovery

No matter how careful you are, problems will happen. Linux provides straightforward ways to diagnose and fix common issues, so you can keep your system and applications running smoothly.

---

## 10.1 Checking System Logs

- **View recent system events**
  ```bash
  less /var/log/syslog
  ```
  - **Syntax:**  
    `less [filename]`
    - Opens the file in a scrollable viewer. Use arrow keys to move, `q` to quit.
  - **Simple use case:**  
    Scan recent system messages for errors after a crash or failed service.

- **View authentication and security logs**
  ```bash
  less /var/log/auth.log
  ```
  - **Syntax:**  
    Same as above, but targets the authentication log.
  - **Simple use case:**  
    Investigate failed login attempts or sudo misuse.

- **Follow a log in real time**
  ```bash
  tail -f /var/log/syslog
  ```
  - **Syntax:**  
    `tail -f [filename]`
    - `-f` means “follow”—shows new lines as they’re written.
  - **Simple use case:**  
    Watch what happens as you restart a service or reproduce a bug.

---

## 10.2 Checking Disk and Memory Issues

- **Check disk space**
  ```bash
  df -h
  ```
  - **Syntax:**  
    `df -h`
    - `-h` makes sizes “human-readable” (MB/GB).
  - **Simple use case:**  
    Fix errors caused by a full disk.

- **Check RAM usage**
  ```bash
  free -h
  ```
  - **Syntax:**  
    `free -h`
    - Displays total, used, and free memory in human-readable format.
  - **Simple use case:**  
    See if your system is running low on memory.

- **Find large files and folders**
  ```bash
  du -h --max-depth=1 /
  ```
  - **Syntax:**  
    `du -h --max-depth=1 [directory]`
    - `du` = disk usage, `-h` = human-readable, `--max-depth=1` = only the first level of folders.
  - **Simple use case:**  
    Track down what’s filling up your disk.

---

## 10.3 Restarting Services

- **Restart a system service (systemd)**
  ```bash
  sudo systemctl restart servicename
  ```
  - **Syntax:**  
    `sudo systemctl restart [service]`
    - Restarts the named service (like nginx, apache2, etc.)
  - **Simple use case:**  
    Restart web servers, databases, or other services after changes.

- **Check if a service is running**
  ```bash
  systemctl status servicename
  ```
  - **Syntax:**  
    `systemctl status [service]`
    - Shows status, logs, and errors for the service.
  - **Simple use case:**  
    See why a service failed to start.

---

## 10.4 Killing Stuck or Zombie Processes

- **List running processes**
  ```bash
  ps aux
  ```
  - **Syntax:**  
    `ps aux`
    - Shows all running processes with details.
  - **Simple use case:**  
    Find the PID (process ID) of a stuck program.

- **Find a process by name**
  ```bash
  pgrep -l processname
  ```
  - **Syntax:**  
    `pgrep -l [processname]`
    - Lists PIDs and names for matching processes.
  - **Simple use case:**  
    Get the PID of a frozen app to kill it.

- **Stop it safely**
  ```bash
  kill PID
  ```
  - **Syntax:**  
    `kill [PID]`
    - Sends a TERM signal (asks the process to stop).
  - **Simple use case:**  
    Gracefully shut down a process.

- **Force kill if necessary**
  ```bash
  kill -9 PID
  ```
  - **Syntax:**  
    `kill -9 [PID]`
    - Sends SIGKILL, which cannot be ignored.
  - **Simple use case:**  
    End a frozen application or runaway script.

---

## 10.5 Recovering Deleted Files

- **Check the Trash (GUI):**
  - If you used a file manager, check the trash folder.

- **For command line deletes (`rm`):**  
  - Recovery is difficult; try `testdisk` or backups:
    ```bash
    sudo apt install testdisk
    sudo testdisk
    ```
    - **Syntax:**  
      `sudo apt install [package]` to install, then run `testdisk`.
    - **Simple use case:**  
      Attempt to recover accidentally deleted files on a disk.

---

## 10.6 Fixing Broken Packages

- **Repair package database**
  ```bash
  sudo apt --fix-broken install
  ```
  - **Syntax:**  
    `sudo apt --fix-broken install`
    - Attempts to fix broken dependencies and incomplete installs.
  - **Simple use case:**  
    Resolve errors during package installation or upgrade.

---

## 10.7 Common Networking Fixes

- **Restart networking**
  ```bash
  sudo systemctl restart networking
  ```
  - **Syntax:**  
    `sudo systemctl restart networking`
    - Restarts the networking service.
  - **Simple use case:**  
    Fix network connection issues.

- **Release and renew IP (desktop)**
  ```bash
  sudo dhclient -r
  sudo dhclient
  ```
  - **Syntax:**  
    `sudo dhclient -r` releases the address; `sudo dhclient` requests a new one.
  - **Simple use case:**  
    Get a new IP address if your network changes.

---

## 10.8 Real-World Practice

1. After a failed install, try:
   ```bash
   sudo apt --fix-broken install
   ```
2. If your web server won’t start, check its status and logs:
   ```bash
   systemctl status nginx
   less /var/log/nginx/error.log
   ```
3. If disk is full, find and delete large files:
   ```bash
   du -h --max-depth=1 ~
   rm ~/Downloads/largefile.iso
   ```

---

## 10.9 Tips and Best Practices

- Always check logs first—most answers are there.
- Don’t panic if you delete something—stop using the disk and try recovery tools.
- Make regular backups to avoid disaster.
- Use `systemctl status` and logs to debug failing services.
- Document fixes for future reference.

---

**Next:**  
You’ve completed the basics!  
Check the [./](./) directory for more resources, advanced guides, or revisit earlier lessons.
Go to [advanced](./11-advanced-tips-and-next-steps_Version2.md) topics
