# cybersecurity-task-1
 Cyber Security Internship – Task 1: Port Scanning

 Objective:
Use Nmap to scan the local network, identify active hosts, open ports, and analyze potential security exposures.

---

Tools Used:
- Nmap (Advanced Scan Command used: `-T4 -A -v`)
- ipconfig (to find my local IP)

---

My Setup:
- My IP Address: 192.168.213.203
- Local Network Range Scanned: 192.168.213.0/24
- Command Used:
ipconfig
nmap -T4 -A -v 192.168.213.0/24
nmap -sS 192.168.213.203
