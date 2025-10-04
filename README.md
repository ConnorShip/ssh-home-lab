# SSH Home Lab Project

## Overview
This project demonstrates the setup and use of a basic SSH server on Ubuntu and remote access from a Windows client.  
---

## Environment Setup
- **Ubuntu Server** (running OpenSSH server)
- **Windows 11 Home** (acting as a client, using built-in PowerShell SSH)
- **Networking**: Both machines configured on the same subnet for direct communication.

---

## Steps Performed

### 1. Update Ubuntu
- Installed updates & upgrades
    ```bash
    sudo apt update && sudo apt upgrade -y
    ```

### 2. Setup SSH on Ubuntu
- Installed OpenSSH:
  ```bash
  sudo apt install openssh-server -y
    ```
- Enabled & Verified SSH
    ```bash
    sudo systemctl enable ssh
    sudo systemctl start ssh
    sudo systemctl status ssh
    ```

### 3. Verify Network Connectivity

- Next I needed to ensure the server was reachable from my client machine
- On my Ubuntu machine I checked the ipv4 address and then ping'ed it from my client machine.

#### *Issue No.1*  
> **Network Connectivity Failure**  
Client (`192.168.0.x`) and server (`192.168.64.x`) were on different subnets.  
Resolved by adjusting Ubuntu’s network settings, then confirmed connectivity with a successful ping from Windows.

### 4. Connect via SSH
```
ssh username@<Ubuntu-IP>
```

### 5. Basic Commands
- Reviewed disk usage & Running processes
    ```
    df -h
    top
    ```
- Lastly I made a welcome message:
    ```
    sudo nano /etc/motd
    # Welcome to Connor's Home Lab!
    ```
