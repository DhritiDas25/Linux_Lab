# How to do Secure Shell Login?
## SSH
To do secure shell login we use **SSH**.

**SSH** stand for **Secure Shell** which is a cryptographic network protocol used to securely access and manage remote systems over an unsafe network system.

```bash 
Note:

Cryptographic network protocol: It is a set of rules and permissions that use cryptographic techniques to secure communication over a netwrok.
```
### What does SSH do?

It allows you to:

🔸 Login to remote Linux/Unix servers.

🔸 Execute commands on a remote machine.

🔸Transfer files securely using scp, sftp.

🔸Create encrypted tunnels or port forwards.

🔸Automate remote tasks or deployment.

```bash 
Note:
SCP (SECURE COPY PROTOCOL): -Securely copies files between hosts over SSH.
     -Based on SSH it encrypts both data and credentials.
     -Usage: scp file.txt user@remote_host:/path/to/destination
     -But SFTP is preferred over SCP.

SFTP (SECURE FILE TRANSFER PROTOCOL): -Securely transfers and manages files over SSH.
                                      -Uses SSH for encryption and authentication.
                                      -Usage: sftp user@remote_host
                                             Then use commands like ls, get, cd, etc.
```
## Advantages of SSH

| Secure Encryption | Encrypts all data transferred between client and server. |
| :---: | :----: |
| Secure Authentication | Supports publci key cryptography, which is more secure than passwords. |
| Data Integrity | Ensures unaltered communication |
| File Transfer| Secure ```scp``` and ```sftp```. |
| Port Forwarding | Tunnel other protocols securely. |
| Configureable | Highly confirgureable and supports compression to speed up slow connections. |

## How Use SSH login in Ubuntu Linux?

### **1. SSH Login (Client Side)**
If the remote server is already running an SSH server then log in using:
```bash
ssh username@hostname_or_ip
```
### **2. Install and Enable SSH**
#### *(The fololowing steps are optional. The purpose is to login without using a password.)*
#### 🔸If SSH server is not installed on your Ubuntu Linux then use:
```bash 
    sudo apt update
    sudo apt install openssh-server
```
#### 🔸Enable and Start SSH server:
```bash
sudo systemctl enable ssh
sudo systemctl start ssh
```
#### 🔸 Check SSH staus:
```bash
sudo systemctl status ssh
```
You should see: ```active(running)```

### **3. Use SSH Key Authentication (More Secure)**
#### 🔸On the Client (your local machine):
```bash
ssh-keygen
```
#### 🔸Accept defaults and then run:
```bash
ssh-copy-id username@hostname_or_ip
```
#### 🔸Now login is possible without using password:
```bash
ssh username@hostname_or_ip
```

### **4. Check SSH Port (Default 22)**

| Purpose | Explanations |
| :-----: | :----------: |
| Identify Active SSH Port | Know where SSH listens for incoming connections. |
| Security through Obscurity | Reduces automated attacks by changing the ports. |
|Firewall Configuration | Ensure port is opened or allowed to enable login. |
| Avoid Connection Failured | Coonnect to the correct port. |

#### 🔸If the SSH server is using andifferent port then use:
```bash
ssh -p PORT username@hostname_or_ip
```
### 5. Verify Port Listening
#### Ensure SSH daemon is listening on the correct port/interface:
```bash
ss -tuln | grep ssh
```
#### or
```bash
sudo netstat -tulpn | grep ssh
```
