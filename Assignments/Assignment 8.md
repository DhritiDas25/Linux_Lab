# Assignment 8
### Objective: Set up and verify secure GUI access from your laptop to a friend's laptop on the same or different network using SSH (X11 or VNC). Assume you have explicit permission.

## ⭕1. Prepare and Secure the Remote Machine (run on friend's laptop)

### 1. SSH should be downloaded. 
### 🔸If not then use the command: 
```bash
sudo apt update
sudo apt install -y openssh-server
```
### 📸Image Snapshots:
![alt text](<WhatsApp Image 2025-11-03 at 21.16.14_0045f499.jpg>)

![alt text](<WhatsApp Image 2025-11-03 at 21.16.46_f7e8dcfc-1.jpg>)

### 2. Check your as well as your friend's ip address beforehand using:
```bash
ip a
```
### 🔸If it shows:
```bash
inet 172.20.10.5/28 brd 172.20.10.15 scope global dynamic enp0s3
``` 
### Then the ip address is **172.20.10.5**.
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 23.00.15_f493fce9.jpg>)
### Here the ip is: **127.0.0.1**.
### 3. Create a non-root user and enable SSH:
```bash
sudo useradd -m frienduser || true
sudo systemctl enable --now ssh
```
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 21.18.44_1632d03b.jpg>)

### 4. Add your public key to `/home/frienduser/.ssh/authorized_keys` and set correct permissions:
```bash
mkdir -p /home/frienduser/.ssh/ && echo "<your-pubkey>" >>
sudo chmod 700 /home/frienduser/.ssh
sudo chmod 600 /home/frienduser/.ssh/authorized-keys
sudo chown -R frienduser:frienduser /home/frienduser/.ssh
```
### OR
```bash
sudo mkdir -p /home/frienduser/.ssh/
echo "<your-pubkey>" | sudo tee -a /home/frienduser/.ssh/authorized-keys
sudo chmod 700 /home/frienduser/.ssh
sudo chmod 600 /home/frienduser/.ssh/authorized-keys
sudo chown -R frienduser:frienduser /home/frienduser/.ssh
```
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 21.19.33_8e03c076.jpg>)

## ⭕2. Connect & Test X11 Forwarding (single GUI app)
### 🔸From your laptop, test key-based SSH + X11:
```bash
ssh -p 22 -x frienduser@FRIEND_IP
```
### 🔸It will ask for the friend's password.
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 21.21.27_c3697990.jpg>)

### 🔸After entering the password, run the command:
```bash
xeyes
```
### OR
```bash
gedit &
```
### 🔸If its successful the GUI app opens on your machine and is responsive.

### 📸Image Snapshot:
![alt text](image-66.png)

## ⭕3. Set Up VNC over SSH (full desktop)
### i) Update and then download the VNC server on your friends laptop:
```bash
sudo apt update
sudo apt install tigervnc-standalone-server
```

### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 22.35.57_99c7a5cd.jpg>)

### ii) On your friend's laptop start the VNC server:
```bash
vncser :1
```
### It will ask to set atleast a 6 characters password and verify it.
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 22.45.03_1cc31fd6.jpg>)

### iii) On your laptop create tunnel:
```bash
ssh -L 5901:localhost:5901 -p 22 frienduser@FRIEND_IP -N &
```
### **Here 5901 is a port.**

### 🔸It'll ask for the friend's password.
### 📸Image Snapshot:
![alt text](<WhatsApp Image 2025-11-03 at 22.45.03_1cc31fd6-1.jpg>)

### iv) After entering the password, open VNC viewer to `localhost:5901`.
### v) If it's successful full remote desktop will be visible and clipboard/keyboard will be usable.