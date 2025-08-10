# 9. System Security and User Management

Keeping your system secure is critical. Linux provides granular user, group, and permission management, along with tools to help you monitor and secure your system.

---

## 9.1 User Accounts

- **Add a new user:**
  ```bash
  sudo adduser newusername
  ```
  *Simple use case:*  
  Give a teammate or service its own login.

- **Delete a user:**
  ```bash
  sudo deluser username
  ```
  *Simple use case:*  
  Remove access for someone who no longer needs it.

- **List all users:**
  ```bash
  cat /etc/passwd
  ```
  (Each line is a user account.)

---

## 9.2 Groups and Permissions

- **Add a user to a group:**
  ```bash
  sudo usermod -aG groupname username
  ```
  *Simple use case:*  
  Grant a user access to `docker`, `sudo`, or other system groups.

- **List groups for a user:**
  ```bash
  groups username
  ```

- **See file ownership and permissions:**
  ```bash
  ls -l
  ```
  - First column: permissions, third is owner, fourth is group

- **Change file owner:**
  ```bash
  sudo chown user:group file.txt
  ```

- **Change permissions:**
  ```bash
  chmod 600 secrets.txt   # Owner can read/write, no access for others
  chmod 755 script.sh    # Owner can rwx, others can rx
  ```

---

## 9.3 Sudo and Privileged Access

- **Run a command as root:**
  ```bash
  sudo command
  ```
  *Simple use case:*  
  Install software, edit system configs, or restart services.

- **Switch to the root user:**
  ```bash
  sudo -i
  ```

- **List users with sudo (admin) rights:**
  ```bash
  getent group sudo
  ```

---

## 9.4 Basic Security Best Practices

- Use strong passwords for all accounts.
- Only use `sudo` when necessary.
- Limit the number of users in the `sudo` group.
- Regularly update your system:
  ```bash
  sudo apt update && sudo apt upgrade
  ```
- Lock accounts that don’t need login:
  ```bash
  sudo usermod -L username
  ```

---

## 9.5 Monitoring and Auditing

- **View recent login attempts:**
  ```bash
  last
  ```
- **See failed login attempts:**
  ```bash
  sudo cat /var/log/auth.log | grep "Failed"
  ```
- **Check currently logged-in users:**
  ```bash
  who
  ```

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
- Use SSH keys instead of passwords for remote logins when possible.
- Remove unused accounts and lock those not in use.
- Make regular backups and keep your system updated for security.

---

**Next:** Troubleshooting and recovery—diagnosing problems and recovering your system from common issues!