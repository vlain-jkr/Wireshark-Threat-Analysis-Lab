# 🕵️ Wireshark Threat Analysis Lab — Every Packet Tells a Story

> “You can’t defend what you don’t see.”  
> — Some tired analyst staring at PCAPs at 3AM.

This project is your **Wireshark-powered threat hunting dojo**. From malicious payloads to lateral movement, every bit and byte becomes a clue. It’s not just packet capture — it’s **attack decryption**, **behavioral analysis**, and **network forensics** in one immersive lab.

Welcome to your **Wireshark Threat Analysis Lab**, where nothing goes unnoticed:  
- 📦 PCAPs that bleed secrets  
- 🔎 Filters that laser-focus your view  
- 🧠 Analysis that maps actions to adversaries  

---

## 🔍 What This Project Does

- Captures and analyzes simulated attacker traffic with Wireshark  
- Teaches **deep packet inspection** of suspicious behavior  
- Maps packet data to **MITRE ATT&CK** techniques  
- Trains eyes to spot **C2 traffic**, **credential theft**, and **exfiltration patterns**  
- Builds packet analysis intuition for **SOC**, **IR**, and **threat intel** roles  

---

## 🧰 Prerequisites

- Wireshark (GUI or CLI `tshark`)  
- Sample PCAP files (from real attacks or simulated traffic)  
- Test environment to generate traffic:
  - Kali Linux / Metasploit / Nmap / Netcat
  - Vulnerable containers like DVWA, Juice Shop  
- Basic knowledge of TCP/IP, DNS, HTTP, TLS, and common protocols  

---

## ⚙️ Example Attack Scenarios

### 🧪 Port Scan Detection (Nmap)
Filter:  
```
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

### 🎣 Credential Theft (HTTP POST)
Filter:  
```
http.request.method == "POST" && frame contains "password"
```

### 🔌 Reverse Shells (Netcat)
Filter:  
```
tcp.dstport == 4444 && tcp.len > 0
```

### 💥 Exploit Delivery (Metasploit Payloads)
Watch for suspicious payloads or malformed headers in SMB/HTTP sessions.

### 📤 Data Exfiltration (DNS/HTTP)
Filter:  
```
dns.qry.name contains "base64"  
http.request.uri contains "data="
```

---

## 📚 MITRE ATT&CK Mapping

Map observations to real-world tactics:  
- 🔍 T1046 – Network Service Scanning  
- 🎣 T1056 – Input Capture  
- 📤 T1041 – Exfiltration over C2 Channel  
- 🧬 T1071 – Application Layer Protocol  
- 🏹 T1059 – Command and Scripting Interpreter  

Use annotations in Wireshark or external tools (like `Arkime`, `MISP`) to tag each segment.

---

## 🎨 Visualization Tips

- Use **coloring rules** to highlight threat behavior  
- Follow streams (TCP or HTTP) for end-to-end insight  
- Use statistics:  
  - Conversations  
  - Protocol Hierarchy  
  - IO Graphs  

---

## 🚀 Lab Use Cases

- Practice packet-based incident response  
- Extract IOCs (IPs, hashes, domains) from captures  
- Build filtering cheat sheets for real-world threats  
- Train for blue team certs like **PCAP Analysis**, **GCIA**, or **Security+**  

---

## 📊 Skills Gained

Wireshark mastery, TCP/IP analysis, threat hunting, protocol inspection, ATT&CK correlation, PCAP parsing, SOC-level triage

---

## 👤 About Me

I’m Gunveer Singh (`vlain-jkr`) — listening to the wires, chasing ghost packets, and teaching networks to confess.  
Every flow has a fingerprint. Every packet tells a story. Let’s read between the lines.

---

*Clone it, capture it, crack it. Whether you're hunting threats or just love packets — this lab sees all.*
