# Overpass – TryHackMe Write-Up

> Difficulty: Easy  
> Tags: Linux, Enumeration, SSH, Cracking

---

## 🔍 Recon

```bash
nmap -sC -sV -oN overpass-nmap.txt 10.10.10.10

Found ports: 22 (SSH), 80 (HTTP)
```

Visited website → downloaded source → saw hardcoded credentials...

Used SSH login:
```
ssh james@10.10.10.10
password: ********
```

🧨 Privilege Escalation
Used sudo -l, found backup script running as root...

Edited script → got root shell.

🏁 Root Flag
```
cat /root/root.txt
```
