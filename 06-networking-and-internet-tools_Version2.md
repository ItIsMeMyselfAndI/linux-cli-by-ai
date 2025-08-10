# 6. Networking and Internet Utilities

Linux gives you powerful tools to check connectivity, transfer files, and troubleshoot network issues right from the CLI. These are essential for developers working with servers, APIs, or remote systems.

---

## 6.1 Checking Network Connectivity

- **Ping another machine or website:**
  ```bash
  ping google.com
  ```
  - Press <kbd>Ctrl</kbd>+<kbd>C</kbd> to stop.
  *Simple use case:*  
  Check if your server can reach the internet or if a website is up.

- **Test a specific number of packets:**
  ```bash
  ping -c 4 github.com
  ```
  *Simple use case:*  
  Quickly test if a host is reachable.

---

## 6.2 Downloading Files from the Internet

- **Download a file with wget:**
  ```bash
  wget https://example.com/file.zip
  ```
  *Simple use case:*  
  Download a release or dataset directly to your server.

- **Download with curl:**
  ```bash
  curl -O https://example.com/file.zip
  ```
  *Simple use case:*  
  Curl is also used for API testing and automation.

---

## 6.3 Viewing Network Configuration

- **Show IP addresses (modern method):**
  ```bash
  ip addr
  ```
- **Show older ifconfig output (if installed):**
  ```bash
  ifconfig
  ```
- **View routing table:**
  ```bash
  ip route
  ```

*Simple use case:*  
Find your server’s IP address or debug connectivity issues.

---

## 6.4 Checking Open Ports and Services

- **List open ports with netstat (if installed):**
  ```bash
  netstat -tuln
  ```
- **Check open ports with ss (modern tool):**
  ```bash
  ss -tuln
  ```
  *Simple use case:*  
  See if your web server or database is listening on the right port.

---

## 6.5 Secure Remote Access with SSH

- **Connect to a remote machine:**
  ```bash
  ssh user@host
  ```
- **Copy files to/from remote machine:**
  ```bash
  scp file.txt user@host:/path/
  scp user@host:/path/file.txt .
  ```
  *Simple use case:*  
  Deploy code, update configs, or transfer logs securely.

---

## 6.6 Real-World Practice

1. Test if a website is up:
   ```bash
   ping -c 2 github.com
   ```
2. Download a script:
   ```bash
   wget https://raw.githubusercontent.com/user/repo/main/install.sh
   ```
3. SSH into your cloud server:
   ```bash
   ssh youruser@yourserver.com
   ```
4. Check if your web server is running:
   ```bash
   ss -tuln
   ```

---

## 6.7 Tips and Best Practices

- Use `ping` to quickly diagnose network issues.
- `curl` is excellent for testing REST APIs.
- Always use SSH for secure remote administration and file transfers.
- Use `ss` instead of `netstat` on new systems.

---

**Next:** Processes and system monitoring—track, manage, and optimize what runs on your system!