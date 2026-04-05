# Nmap Scan & Vulnerability Analysis (scanme.nmap.org)

## 🎯 Objective
Perform reconnaissance and vulnerability scanning on a safe public test target using Nmap.

## 🛠️ Tools Used
- Nmap (Network Mapper)
- NSE (Nmap Scripting Engine)

## 🔍 Steps Performed

### 1. Initial Port Scan
Command:
nmap scanme.nmap.org

Result:
- Open ports: 22 (SSH), 80 (HTTP), 9929, 31337
- Most ports closed

### 2. Service Enumeration
Command:
nmap -sV scanme.nmap.org

Result:
- SSH: OpenSSH 6.6.1 (Ubuntu)
- HTTP: Apache 2.4.7 (Ubuntu)

### 3. Advanced Scan
Command:
nmap -A scanme.nmap.org

Result:
- OS detected: Linux
- Traceroute performed
- Server info discovered

### 4. Vulnerability Scan
Command:
nmap --script=vuln scanme.nmap.org

Result:
- Vulnerability found:
  - Slowloris DoS (CVE-2007-6750)
  - State: Likely Vulnerable

## ⚠️ Key Findings
- Outdated Apache server
- Potential DoS vulnerability
- No XSS found
- Interesting directory: /images/

## 🧠 Skills Demonstrated
- Port scanning
- Service enumeration
- OS detection
- Vulnerability scanning

## 📌 Conclusion
Demonstrated practical use of Nmap for reconnaissance and vulnerability detection.

## ⚠️ Disclaimer
Test performed on scanme.nmap.org (authorized test target).