# 9. System Security and User Management

Securing your Linux system and managing who can access and modify files is vital for any developer or administrator. Linux offers robust tools for controlling users, groups, and permissions, allowing you to limit access, enforce security policies, and audit activity.

---

## 9.1 User Accounts

- **Add a new user**
  ```bash
  sudo adduser newusername
  ```
  - **Syntax:**  
    `sudo adduser [username]`  
    - `sudo` runs with administrative rights.  
    - `adduser` creates a new user and prompts for details (password, etc.).
  - **Simple use case:**  
    Give a teammate or application its own login for accountability and isolation.

- **Delete a user**
  ```bash
  sudo deluser username
  ```
  - **Syntax:**  
    `sudo deluser [username]`
    - Removes the user account and optionally its home directory.
  - **Simple use case:**  
    Remove access for someone who no longer needs it.

- **List all users**
  ```bash
  cat /etc/passwd
  ```
  - **Syntax:**  
    `cat /etc/passwd`
    - Shows each user as a line, with info separated by colons.
  - **Simple use case:**  
    Quickly see all local accounts on the system.

---

## 9.2 Groups and Permissions

- **Add a user to a group**
  ```bash
  sudo usermod -aG groupname username
  ```
  - **Syntax:**  
    `sudo usermod -aG [group] [user]`
    - `-aG` appends the user to a group.
  - **Simple use case:**  
    Grant a user access to developer tools, Docker, or sudo privileges.

- **List groups for a user**
  ```bash
  groups username
  ```
  - **Syntax:**  
    `groups [username]`
    - Shows all groups a user belongs to.
  - **Simple use case:**  
    Check group-based access and permissions.

- **See file ownership and permissions**
  ```bash
  ls -l
  ```
  - **Syntax:**  
    `ls -l`
    - Shows permissions, owner, group, and file size/date.
  - **Simple use case:**  
    Audit who can access or modify files.

- **Change file owner**
  ```bash
  sudo chown user:group file.txt
  ```
  - **Syntax:**  
    `sudo chown [user]:[group] [file]`
    - Sets new owner and group for a file.
  - **Simple use case:**  
    Assign files to the correct user or group after a transfer.

- **Change permissions**
  ```bash
  chmod 600 secrets.txt   # Only owner can read/write
  chmod 755 script.sh    # Owner can rwx, others can rx
  ```
  - **Syntax:**  
    `chmod [mode] [file]`
    - Numeric (`600`, `755`) or symbolic (`+x`) modes.
  - **Simple use case:**  
    Restrict access to sensitive files or make scripts executable.

---

## 9.3 Sudo and Privileged Access

- **Run a command as root**
  ```bash
  sudo command
  ```
  - **Syntax:**  
    `sudo [command]`
    - Temporarily run a single command as the superuser.
  - **Simple use case:**  
    Install software, edit system files, or restart services securely.

- **Switch to the root user**
  ```bash
  sudo -i
  ```
  - **Syntax:**  
    `sudo -i`
    - Opens a root shell for advanced administration.
  - **Simple use case:**  
    Perform a series of admin tasks without typing `sudo` each time.

- **List users with sudo rights**
  ```bash
  getent group sudo
  ```
  - **Syntax:**  
    `getent group [groupname]`
    - Shows all members of the `sudo` (admin) group.
  - **Simple use case:**  
    Audit who has admin access to the system.

---

## 9.4 Basic Security Best Practices

- Use strong, unique passwords for all accounts.
- Only use `sudo` when necessary, and log out of root shells promptly.
- Limit the number of users in the `sudo` group.
- Regularly update your system:
  ```bash
  sudo apt update && sudo apt upgrade
  ```
  - Keep patched against vulnerabilities.
- Lock accounts that don’t need login:
  ```bash
  sudo usermod -L username
  ```
  - Prevents password logins for that user.

---

## 9.5 Monitoring and Auditing

- **View recent login attempts**
  ```bash
  last
  ```
  - **Syntax:**  
    `last`
    - Lists recent logins, reboots, and their times.
  - **Simple use case:**  
    Check who accessed the system recently.

- **See failed login attempts**
  ```bash
  sudo cat /var/log/auth.log | grep "Failed"
  ```
  - **Syntax:**  
    `cat /var/log/auth.log | grep [pattern]`
    - View and search the authentication log for failures.
  - **Simple use case:**  
    Investigate possible break-in attempts.

- **Check currently logged-in users**
  ```bash
  who
  ```
  - **Syntax:**  
    `who`
    - Lists all users currently logged in.
  - **Simple use case:**  
    See who is connected to your server right now.

---

## 9.6 Real-World Practice

1. Add a user to the `sudo` group:
   ```bash
   sudo usermod -aG sudo newusername
   ```
2. Change permissions on a sensitive file:
   ```bash
   chmod 600 ~/.ssh/id_rsa
   ```
3. Check who is currently logged in:
   ```bash
   who
   ```

---

## 9.7 Tips and Best Practices

- Never share your password or SSH keys.
- Use SSH keys instead of passwords for server logins.
- Remove or lock unused accounts.
- Regularly backup and keep your system updated for security.

---

**Next:** [10. Troubleshooting and Recovery](./10-troubleshooting-and-recovery_Version2.md)
