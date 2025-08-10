# 5. Package Management and Installing Software

Software on Linux is managed through package managers, which make it easy to install, update, and remove applications from central repositories. On Debian and Ubuntu systems, the standard tool is `apt`.

---

## 5.1 Updating the Package List and System

- **Update your list of available packages**
  ```bash
  sudo apt update
  ```
  - **Syntax:**  
    `sudo apt update`  
    - `sudo` runs the command as a superuser (admin).
    - `apt` is the package manager command.
    - `update` tells `apt` to refresh its list of available software.
  - **Simple use case:**  
    Make sure you're seeing the latest versions before installing or upgrading any software.

- **Upgrade all installed packages**
  ```bash
  sudo apt upgrade
  ```
  - **Syntax:**  
    `sudo apt upgrade`  
    - `upgrade` downloads and installs the newest versions of all packages currently installed.
  - **Simple use case:**  
    Keep your system secure and up-to-date.

---

## 5.2 Installing New Software

- **Install a package**
  ```bash
  sudo apt install packagename
  ```
  - **Syntax:**  
    `sudo apt install [package]`
    - `[package]` is the name of the software you want to install.
  - **Simple use case:**  
    Install Git:
    ```bash
    sudo apt install git
    ```

- **Install multiple packages at once**
  ```bash
  sudo apt install git curl vim
  ```
  - **Syntax:**  
    `sudo apt install [package1] [package2] ...`
  - **Simple use case:**  
    Set up your development environment in one command.

---

## 5.3 Removing Software

- **Remove a package (keep configs)**
  ```bash
  sudo apt remove packagename
  ```
  - **Syntax:**  
    `sudo apt remove [package]`
  - **Simple use case:**  
    Uninstall an app but keep your settings.

- **Remove a package and its configuration files**
  ```bash
  sudo apt purge packagename
  ```
  - **Syntax:**  
    `sudo apt purge [package]`
  - **Simple use case:**  
    Do a thorough cleanup if you don't plan to reinstall.

---

## 5.4 Searching for Packages

- **Search for a package by name or description**
  ```bash
  apt search keyword
  ```
  - **Syntax:**  
    `apt search [term]`
  - **Simple use case:**  
    Find all packages related to Python:
    ```bash
    apt search python
    ```

---

## 5.5 Viewing Package Details

- **Show detailed info about a package**
  ```bash
  apt show packagename
  ```
  - **Syntax:**  
    `apt show [package]`
  - **Simple use case:**  
    See the version, description, dependencies, and more before installing.

---

## 5.6 Managing Repositories

- **Add a new PPA (Personal Package Archive)**
  ```bash
  sudo add-apt-repository ppa:user/ppa-name
  sudo apt update
  ```
  - **Syntax:**  
    `sudo add-apt-repository [ppa:...]`
    - Follow with `sudo apt update` to refresh the package list.
  - **Simple use case:**  
    Get the latest version of a tool that's not in the official repositories.

---

## 5.7 Real-World Practice

1. **Update and upgrade your system:**
   ```bash
   sudo apt update
   sudo apt upgrade
   ```
2. **Install a new editor:**
   ```bash
   sudo apt install vim
   ```
3. **Remove a game you don’t use:**
   ```bash
   sudo apt remove aisleriot
   ```
4. **Search for a tool:**
   ```bash
   apt search docker
   ```

---

## 5.8 Tips and Best Practices

- Run `sudo apt update` regularly for fresh package lists.
- Always read what a package will do with `apt show` before installing.
- Be careful with `purge`—it removes all config files too.
- Only add trusted PPAs to avoid security risks.

---

**Next:** [6. Networking and Internet Utilities](./06-networking-and-internet-tools_Version2.md)
