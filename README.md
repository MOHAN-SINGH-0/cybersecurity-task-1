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


 Hosts Detected:
Nmap found 3 live hosts on my network.

Host: 192.168.213.203 (My Device)
Open Ports:
- 135/tcp (Microsoft Windows RPC)
- 139/tcp (Microsoft Windows netbios-ssn)
- 445/tcp (Microsoft-ds)
- 
Host: 192.168.213.112
Open Port:
- 53/tcp (DNS – dnsmasq 2.51)
- 
Host: 192.168.213.1 (Likely router)

All 1000 scanned ports are in ignored states
→ Not shown: 1000 closed tcp ports (conn-refused)

 Observations:
135, 139, 445 on my machine are often linked to Windows file sharing and RPC services.

Port 53 (DNS) on 192.168.213.112 is a possible DNS service, commonly used in routers or local servers.

192.168.213.1 had no open ports in this scan, which is common for firewalled gateways.

🔐 Security Risk Notes:
Port	     Service	         Risk  Description
135	    Microsoft RPC	   Can be exploited for remote code execution
139	    NetBIOS          	Vulnerable to SMB attacks if not secured
445     	Microsoft-DS	    Used in SMB attacks (e.g., WannaCry)
53	    DNS(dnsmasq)       	DNS cache poisoning, spoofing if misconfigured

Recommendations:

Disable SMB ports if file sharing is not needed.
Use a firewall to restrict unnecessary traffic.
Update and patch services regularly.
Restrict DNS access if the DNS server is internal only.


