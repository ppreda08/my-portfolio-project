# 🔍 Nmap Scan & Vulnerability Analysis (scanme.nmap.org)

## ⚠️ Disclaimer
This scan was performed on **scanme.nmap.org**, an officially authorized and safe testing target provided by Nmap.

---

## 🎯 Objective
To perform reconnaissance and vulnerability scanning on a public test system using Nmap and analyze potential security risks.

---

## 🛠️ Tools Used
- Nmap (Network Mapper)
- NSE (Nmap Scripting Engine)

---

## 🔎 Steps Performed

### 1. Initial Port Scan
**Command:**
nmap scanme.nmap.org

**Result:**
- Open ports: 22 (SSH), 80 (HTTP), 9929, 31337
- Most other ports are closed

---

### 2. Service Enumeration
**Command:**
nmap -sV scanme.nmap.org

**Result:**
- SSH: OpenSSH (Ubuntu)
- HTTP: Apache (Ubuntu)

---

### 3. Advanced Scan
**Command:**
nmap -A scanme.nmap.org

**Result:**
- OS detected: Linux
- Additional host and service details identified

---

### 4. Vulnerability Scan
**Command:**
nmap --script=vuln scanme.nmap.org

**Result:**
- Potential vulnerability detected:
  - Slowloris DoS (CVE-2007-6750)

---

### 5. Full Port Scan
**Command:**
nmap -p- scanme.nmap.org

**Purpose:**
Scan all 65535 TCP ports to identify hidden or non-standard services.

**Result:**
- Confirmed open ports: 22 (SSH), 80 (HTTP), 9929, 31337
- Port 25 (SMTP) detected as filtered
- No additional hidden open ports discovered

**Insight:**
The full scan confirms the initial findings and shows that no unexpected services are exposed.  
The presence of a filtered SMTP port suggests firewall or access control rules are in place.

---

## 🌐 HTTP Enumeration

### Command Used:
nmap --script=http-enum scanme.nmap.org

### Purpose:
To discover publicly accessible web directories and hidden paths.

### Findings:
- Discovered directory: `/images/`
- Possible exposure of public resources

---

## 🔑 Key Findings
- Port 22 (SSH) is open → remote access service
- Port 80 (HTTP) is open → web server available
- Additional high ports detected (9929, 31337)
- `/images/` directory exposed
- No major vulnerabilities confirmed

---

## ⚠️ Security Analysis
- SSH exposure → brute-force risk
- HTTP service → potential web attack surface
- Directory exposure → information disclosure risk
- No critical vulnerabilities, but monitoring required

---

## 🛡️ Mitigation Recommendations
- Disable SSH password authentication (use key-based login)
- Implement rate limiting / fail2ban for SSH
- Keep web server updated
- Disable directory listing on web server
- Restrict unnecessary open ports via firewall

---

## 🧠 Analysis
The system exposes multiple services including SSH and HTTP, as well as a public web directory.  
While no critical vulnerabilities were confirmed, these services increase the attack surface.

---

## 🎯 Attacker Perspective
An attacker could:
- Attempt brute-force attacks on SSH
- Explore exposed directories for sensitive files
- Target web server vulnerabilities

---

## 🛡️ Defender Perspective
A defender should:
- Monitor login attempts and logs
- Restrict SSH access
- Patch and update services
- Monitor web traffic for unusual activity

---

## ⚙️ Commands Used
- nmap scanme.nmap.org
- nmap -sV scanme.nmap.org
- nmap -A scanme.nmap.org
- nmap --script=vuln scanme.nmap.org
- nmap --script=http-enum scanme.nmap.org
- nmap -p- scanme.nmap.org

---

## 🧠 Skills Demonstrated
- Network reconnaissance
- Port scanning
- Service enumeration
- Vulnerability assessment
- Web enumeration
- Security analysis and reporting

---

## 📌 Conclusion
This project demonstrates practical use of Nmap for reconnaissance, service detection, and vulnerability analysis.  
It highlights how exposed services and directories contribute to potential attack vectors and the importance of proper system hardening.