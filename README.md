# Practical Linux Command Line Guide (Ubuntu/Debian) – Developer Edition

A hands-on, real-world guide for developers and power users, focused on Ubuntu/Debian (but widely applicable to other Linux distributions).  
This outline covers essential and advanced Linux CLI usage with practical examples and industry best practices.

---

## 1. Introduction to Linux and the Command Line
- What is Linux? What is Ubuntu/Debian?
- Why use the command line? Real-world developer scenarios
- Understanding the shell (bash, zsh)
- Terminal vs. GUI: strengths and use cases

---

## 2. Getting Started: The Terminal and Basic Navigation
- Opening the terminal (shortcut keys, remote access with SSH)
- The prompt, executing commands, basic syntax
- Navigating directories: `pwd`, `ls`, `cd`
  - Real-world case: Finding a project folder quickly
- Path shortcuts (`.`, `..`, `~`, tab completion)

---

## 3. Working with Files and Directories
- Creating, copying, moving, renaming: `touch`, `mkdir`, `cp`, `mv`
- Deleting files/directories: `rm`, `rmdir`, `rm -r`
  - Safety tips: preventing accidental deletion
- Viewing and editing files: `cat`, `less`, `head`, `tail`, `nano`, `vim`
- File permissions and ownership: `ls -l`, `chmod`, `chown`
  - Real-world case: Fixing a permission error on a project file

---

## 4. Searching, Finding, and Managing Content
- `find`, `locate`, `grep` – searching for files/folders and inside files
  - Real-world case: Finding a bug in a large codebase
- `wc`, `sort`, `uniq`, `cut`, `awk`, `sed` basics

---

## 5. Package Management and Installing Software
- `apt update`, `apt upgrade`, `apt install`, `apt remove`, `apt search`
  - Real-world case: Installing Node.js, Python, or a code editor
- Managing repositories (PPAs)

---

## 6. Networking and Internet Utilities
- Checking connectivity: `ping`, `curl`, `wget`
- Viewing network info: `ifconfig`, `ip`, `netstat`, `ss`
- SSH basics for remote development

---

## 7. Processes and System Monitoring
- Viewing running processes: `ps`, `top`, `htop`
- Managing processes: `kill`, `killall`, `pkill`, `&`, `jobs`, `fg`, `bg`
- Monitoring system resources: `df`, `du`, `free`, `uptime`

---

## 8. Disk and Filesystem Management
- Checking disk usage: `df`, `du`
- Mounting drives, USBs: `mount`, `umount`
- Understanding `/etc/fstab` and automounting

---

## 9. Scripting and Automation
- Writing simple bash scripts
- Scheduled tasks: `cron`, `crontab`
- Real-world case: Automating backups or deployments

---

## 10. Users, Groups, and Permissions
- Managing users: `adduser`, `usermod`, `deluser`
- Groups and sudo privileges (`sudo`, `/etc/sudoers`)
- Real-world case: Granting a teammate project folder access

---

## 11. Environment Variables and Shell Configuration
- Setting and exporting variables
- Editing `.bashrc`, `.profile`, `.bash_aliases`
- Real-world case: Adding a tool to `$PATH`

---

## 12. Advanced Tools and Productivity Hacks
- Tmux/screen for persistent sessions
- SSH keys and agent for passwordless login
- Aliases and functions for repetitive tasks
- Clipboard (`xclip`, `xsel`) and file transfer tricks

---

## 13. Troubleshooting and System Recovery
- Reading log files: `dmesg`, `/var/log/`
- Disk and memory troubleshooting
- Rescue mode, recovery shells, and fixing a “broken” system

---

## 14. Security Best Practices
- Keeping the system updated
- Using firewalls: `ufw` basics
- Real-world case: Blocking a suspicious IP

---

## 15. Further Resources and Next Steps
- Man pages and help (`man`, `--help`)
- Online communities and documentation
- Recommended books and courses

---

**Each section will include:**
- A concise explanation
- Real-world case/examples
- Practical commands and one-liners
- Tips, best practices, and gotchas

---

**Ready? Start with: [1. Introduction to Linux and the Command Line](./01-introduction-to-linux-cli_Version3.md)**
