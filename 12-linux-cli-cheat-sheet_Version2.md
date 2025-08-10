# 12. Linux CLI Quick Reference Cheat Sheet

A handy, at-a-glance summary of the most useful Linux command-line tools, syntax, and flags for day-to-day productivity.

---

## Navigation

| Command                   | Description                            |
|---------------------------|----------------------------------------|
| `pwd`                     | Print current directory                |
| `ls`                      | List files and folders                 |
| `ls -l`                   | Long list (details)                    |
| `ls -a`                   | Show hidden files                      |
| `cd folder`               | Change directory                       |
| `cd ..`                   | Go up one directory                    |
| `cd ~`                    | Go to home directory                   |

---

## File & Directory Operations

| Command                       | Description                               |
|-------------------------------|-------------------------------------------|
| `touch file.txt`              | Create empty file                         |
| `mkdir folder`                | Create new directory                      |
| `cp file1 file2`              | Copy file                                 |
| `cp -r dir1 dir2`             | Copy directory recursively                |
| `mv file1 file2`              | Move/rename file                          |
| `rm file.txt`                 | Delete file                               |
| `rm -r folder`                | Delete directory recursively              |
| `cat file.txt`                | Show file contents                        |
| `less file.txt`               | View file page by page                    |
| `head file.txt`               | Show first 10 lines                       |
| `tail file.txt`               | Show last 10 lines                        |

---

## Search & Filters

| Command                              | Description                                    |
|--------------------------------------|------------------------------------------------|
| `find . -name "*.py"`                | Find Python files in current directory         |
| `grep "foo" file.txt`                | Search for "foo" in file                       |
| `grep -r "pattern" .`                | Recursively search for pattern                 |
| `wc -l file.txt`                     | Count lines in file                            |
| `sort file.txt | uniq`                | Sort and remove duplicates                     |
| `cut -d',' -f2 file.csv`             | Extract 2nd column from CSV                    |

---

## Package Management (APT)

| Command                         | Description                              |
|----------------------------------|------------------------------------------|
| `sudo apt update`                | Update package list                      |
| `sudo apt upgrade`               | Upgrade packages                         |
| `sudo apt install pkg`           | Install package                          |
| `sudo apt remove pkg`            | Remove package                           |
| `apt search keyword`             | Search for packages                      |

---

## Networking

| Command                            | Description                                |
|-------------------------------------|--------------------------------------------|
| `ping host.com`                     | Check connectivity                         |
| `wget url`                          | Download file                              |
| `curl -O url`                       | Download file                              |
| `ip addr`                           | Show network interfaces & IPs              |
| `ss -tuln`                          | Show open ports                            |
| `ssh user@host`                     | Connect via SSH                            |
| `scp file user@host:/path/`         | Copy file over SSH                         |

---

## System Monitoring

| Command                      | Description                             |
|------------------------------|-----------------------------------------|
| `ps aux`                     | List all processes                      |
| `top` / `htop`               | Live process monitor                    |
| `free -h`                    | Show memory usage                       |
| `df -h`                      | Disk space usage                        |
| `du -sh folder/`             | Disk usage of folder                    |
| `tail -f /var/log/syslog`    | Follow system log                       |

---

## Scripting

| Command/Shebang            | Description                                |
|----------------------------|--------------------------------------------|
| `#!/bin/bash`              | Start of shell script                      |
| `chmod +x script.sh`       | Make script executable                     |
| `./script.sh`              | Run script                                 |
| `$1 $2 ...`                | Script arguments                           |
| `for f in *.txt; do ...; done` | Loop over files                       |
| `if [ -f file ]; then ... fi`   | If condition                         |

---

## User & Permissions

| Command                          | Description                              |
|-----------------------------------|------------------------------------------|
| `sudo adduser newuser`            | Add user                                 |
| `sudo deluser user`               | Delete user                              |
| `groups user`                     | List user groups                         |
| `sudo usermod -aG group user`     | Add user to group                        |
| `sudo chown user:group file`      | Change owner/group of file               |
| `chmod 755 file`                  | Set permissions                          |

---

## Troubleshooting

| Command                               | Description                             |
|----------------------------------------|-----------------------------------------|
| `less /var/log/syslog`                 | View system logs                        |
| `systemctl status service`             | Service status/details                  |
| `sudo apt --fix-broken install`        | Repair broken packages                  |
| `kill PID` / `kill -9 PID`             | Stop/force stop a process               |

---

## Miscellaneous

| Command/Key        | Description                                  |
|--------------------|----------------------------------------------|
| `history`          | Show command history                         |
| `sudo !!`          | Repeat last command as sudo                  |
| `alias ll='ls -lah'` | Create shortcut command                    |
| `<Tab>`            | Autocomplete file/folder name                |
| `<Ctrl>+C`         | Cancel running command                       |
| `<Ctrl>+Z`         | Pause/put command in background              |
| `man command`      | Show manual/help for command                 |

---

**Tip:** When stuck, try `man command` or `command --help` for built-in documentation!

---