# 10. Troubleshooting and Recovery

No matter how careful you are, problems will happen. Linux provides straightforward ways to diagnose and fix common issues, so you can keep your system and applications running smoothly.

---

## 10.1 Checking System Logs

- **View recent system events:**
  ```bash
  less /var/log/syslog
  ```
  *Simple use case:*  
  Scan recent system messages for errors after a crash or failed service.

- **View authentication and security logs:**
  ```bash
  less /var/log/auth.log
  ```
  *Simple use case:*  
  Investigate failed login attempts or sudo misuse.

- **Follow a log in real time:**
  ```bash
  tail -f /var/log/syslog
  ```
  *Simple use case:*  
  Watch what happens as you restart a service.

---

## 10.2 Checking Disk and Memory Issues

- **Check disk space:**
  ```bash
  df -h
  ```
  *Simple use case:*  
  Fix errors caused by a full disk.

- **Check RAM usage:**
  ```bash
  free -h
  ```

- **Find large files and folders:**
  ```bash
  du -h --max-depth=1 /
  ```
  *Simple use case:*  
  Track down what’s filling up your disk.

---

## 10.3 Restarting Services

- **Restart a system service (systemd):**
  ```bash
  sudo systemctl restart servicename
  ```
  *Simple use case:*  
  Restart web servers (`apache2`, `nginx`), databases, or other services after changes.

- **Check if a service is running:**
  ```bash
  systemctl status servicename
  ```

---

## 10.4 Killing Stuck or Zombie Processes

- **List running processes:**
  ```bash
  ps aux
  ```
- **Find a process by name:**
  ```bash
  pgrep -l processname
  ```
- **Stop it safely:**
  ```bash
  kill PID
  ```
- **Force kill if necessary:**
  ```bash
  kill -9 PID
  ```
  *Simple use case:*  
  End a frozen application or runaway script.

---

## 10.5 Recovering Deleted Files

- **Check the Trash (GUI):**  
  If you used a file manager, check the trash folder.

- **For command line deletes (`rm`):**  
  Recovery is hard! Try `testdisk` or backups:
  ```bash
  sudo apt install testdisk
  sudo testdisk
  ```
  *Simple use case:*  
  Attempt to recover accidentally deleted files on a disk.

---

## 10.6 Fixing Broken Packages

- **Repair package database:**
  ```bash
  sudo apt --fix-broken install
  ```
  *Simple use case:*  
  Resolve errors during package installation or upgrade.

---

## 10.7 Common Networking Fixes

- **Restart networking:**
  ```bash
  sudo systemctl restart networking
  ```
- **Release and renew IP (desktop):**
  ```bash
  sudo dhclient -r
  sudo dhclient
  ```

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

---

**Congratulations!**  
You’ve completed the basics of Linux CLI for developers. Keep this guide handy, and don’t be afraid to explore further—Linux rewards curiosity and practice!