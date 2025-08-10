# 6. Networking and Internet Utilities

Linux gives you powerful tools to check connectivity, transfer files, and troubleshoot network issues right from the CLI. These are essential for developers working with servers, APIs, or remote systems.

---

## 6.1 Checking Network Connectivity

- **Ping another machine or website**
  ```bash
  ping google.com
  ```
  - **Syntax:**  
    `ping [hostname or IP]`  
    Sends small packets to the target to check if it’s reachable and measures response time.  
  - **Simple use case:**  
    Check if your server can reach the internet or if a website is up.

- **Test a specific number of packets**
  ```bash
  ping -c 4 github.com
  ```
  - **Syntax:**  
    `ping -c [count] [hostname or IP]`  
    The `-c` option limits the number of ping attempts.
  - **Simple use case:**  
    Quickly test if a host is reachable without endless output.

---

## 6.2 Downloading Files from the Internet

- **Download a file with wget**
  ```bash
  wget https://example.com/file.zip
  ```
  - **Syntax:**  
    `wget [URL]`  
    Downloads a file from the provided URL to your current directory.
  - **Simple use case:**  
    Download a release or dataset directly to your server.

- **Download with curl**
  ```bash
  curl -O https://example.com/file.zip
  ```
  - **Syntax:**  
    `curl -O [URL]`  
    The `-O` flag tells curl to save the file with its original name.
  - **Simple use case:**  
    Download files or test a direct download link.

---

## 6.3 Viewing Network Configuration

- **Show IP addresses (modern method)**
  ```bash
  ip addr
  ```
  - **Syntax:**  
    `ip addr`  
    Lists all network interfaces and their addresses.
  - **Simple use case:**  
    Find your server’s IP address.

- **Show older ifconfig output (if installed)**
  ```bash
  ifconfig
  ```
  - **Syntax:**  
    `ifconfig`  
    Shows similar information; may not be preinstalled on all systems.
  - **Simple use case:**  
    Legacy tool for quick interface info.

- **View routing table**
  ```bash
  ip route
  ```
  - **Syntax:**  
    `ip route`  
    Displays how network traffic is routed.
  - **Simple use case:**  
    Debug networking issues or find the default gateway.

---

## 6.4 Checking Open Ports and Services

- **List open ports with netstat (if installed)**
  ```bash
  netstat -tuln
  ```
  - **Syntax:**  
    `netstat -tuln`  
    - `-t` TCP, `-u` UDP, `-l` listening, `-n` numeric addresses.
  - **Simple use case:**  
    See if your web server or database is listening on the right port.

- **Check open ports with ss (modern tool)**
  ```bash
  ss -tuln
  ```
  - **Syntax:**  
    `ss -tuln`  
    `ss` is a faster, modern replacement for `netstat`.
  - **Simple use case:**  
    Check which processes are using which ports.

---

## 6.5 Secure Remote Access with SSH

- **Connect to a remote machine**
  ```bash
  ssh user@host
  ```
  - **Syntax:**  
    `ssh [user]@[hostname or IP]`
    - `user` is your login on the remote machine.
  - **Simple use case:**  
    Deploy code, update configs, or transfer logs securely.

- **Copy files to/from remote machine**
  ```bash
  scp file.txt user@host:/path/
  scp user@host:/path/file.txt .
  ```
  - **Syntax:**  
    `scp [source] [user@host:destination]`  
    Copy files securely over SSH.
  - **Simple use case:**  
    Transfer files to and from servers without FTP.

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

**Next:** [7. Processes and System Monitoring](./07-processes-and-system-monitoring.md)