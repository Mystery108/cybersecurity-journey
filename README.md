# 🛡️ Cybersecurity & AI Security — 18 Month Roadmap

**B.Tech CSE Fresher → ₹15–20 LPA Security Professional**  
*June 2026 – December 2027*

---

## 📊 Progress Dashboard

| Metric | Count |
|--------|-------|
| **Total Topics** | 25+ |
| **Total Subtopics** | 80+ |
| **Resources** | 300+ |
| **Certifications** | 3 (eJPT, OSCP, AI Red Team) |
| **Portfolio Projects** | 5 |

---

## Phase 1️⃣ — Foundation Fortress (Months 1–3)

### Month 1 — Linux + Networking + Python

<details>
<summary><strong>📋 Linux Fundamentals</strong> <code>Core Skill</code></summary>

#### Filesystem & Navigation
- [ ] Master Linux directory tree (/etc, /tmp, /var/log, /proc)
- [ ] Commands: pwd, ls -la, cd, cat, less, head, tail, file, strings

**Resources:**
- 🟢 [OverTheWire Bandit](https://overthewire.org/wargames/bandit/) (Free Lab)
- 🟠 [TryHackMe Linux 1](https://tryhackme.com/room/linuxfundamentals1) (Paid Lab)

**Key Concepts:**
- Security dirs: /etc (configs), /tmp (world-writable), /var/log (evidence), /proc (live memory)
- `find / -name '*.conf' 2>/dev/null` — find configs
- `grep -ri 'password' /var/www/` — find hardcoded creds

**Interview Questions:**
- ❓ What is /proc and why matters to attackers?
- ❓ How to find all files modified in last 24 hours?

---

#### File Permissions & SUID
- [ ] Understand rwx, chmod numbers (4,2,1)
- [ ] Learn SUID/SGID/Sticky bit exploitation
- [ ] Exploit SUID binaries for privilege escalation

**Resources:**
- 🟠 [GTFOBins](https://gtfobins.github.io) (Free Lab)
- 🟠 [THM Linux PrivEsc](https://tryhackme.com/room/linuxprivesc) (Paid Lab)

**Key Concepts:**
- chmod 755 = rwxr-xr-x, 644 = rw-r--r--
- SUID (4000): runs as file owner → root SUID = privesc
- `find / -perm -u=s -type f 2>/dev/null` — find SUID binaries

**Interview Questions:**
- ❓ Explain SUID and exploitation
- ❓ How does chmod 4755 differ from chmod 755?

---

#### Users, Groups & Sudo
- [ ] User enumeration and sudo misconfigurations
- [ ] Understand /etc/passwd vs /etc/shadow

**Resources:**
- 🟢 [Understanding /etc/passwd](https://www.cyberciti.biz/faq/understanding-etcpasswd-file-format/)
- 🟠 [THM Sudo Security](https://tryhackme.com/room/sudovulnsbypass) (Paid Lab)

**Key Concepts:**
- `sudo -l` → always run first on Linux shell
- UID 0 = root. Multiple UID 0 = backdoor sign

**Interview Questions:**
- ❓ You find `(ALL) NOPASSWD: /usr/bin/python3` in sudo -l. What to do?

</details>

---

<details>
<summary><strong>🌐 Networking Fundamentals</strong> <code>Core Skill</code></summary>

#### OSI Model & TCP/IP
- [ ] Understand all 7 OSI layers
- [ ] Master TCP 3-way handshake

**Resources:**
- 🟢 [Professor Messer Net+](https://www.professormesser.com/network-plus/) (Free)

**Key Concepts:**
- L1 Physical → L2 MAC → L3 IP → L4 TCP/UDP → L7 HTTP
- TCP: SYN → SYN-ACK → ACK
- Ports: 22 SSH, 80 HTTP, 443 HTTPS, 445 SMB, 3306 MySQL

**Interview Questions:**
- ❓ What happens at every layer when you type google.com?

</details>

---

<details>
<summary><strong>🐍 Python for Security</strong> <code>Core Skill</code></summary>

#### Python Basics → Security Focus
- [ ] Learn fundamentals (not full course)
- [ ] Build socket tools, use requests, scapy

**Resources:**
- 🟢 [Automate Boring Stuff](https://automatetheboringstuff.com) (Free)
- 🟠 [Black Hat Python](https://nostarch.com/black-hat-python2E) (Paid)

**Key Concepts:**
- `socket`: TCP/UDP clients, port scanner
- `requests`: HTTP GET/POST, sessions
- `scapy`: raw packets, ARP spoof

**Interview Questions:**
- ❓ Write a Python port scanner

</details>

---

### Month 2 — Web Security + Burp Suite

<details>
<summary><strong>🕷️ OWASP Top 10</strong> <code>CRITICAL</code></summary>

#### A01: Broken Access Control
- [ ] IDOR (Insecure Direct Object Reference)
- [ ] Path traversal attacks
- [ ] Privilege escalation

**Resources:**
- 🟠 [PortSwigger Access Control](https://portswigger.net/web-security/access-control) (Free Lab)

**Key Concepts:**
- IDOR: `user_id=123` → `user_id=124`
- Path traversal: `../../../etc/passwd`

**Interview Questions:**
- ❓ You find `/api/user?id=1001` returns your data. Next?

---

#### A03: Injection
- [ ] SQL injection (SQLi, XSS, Command)

**Resources:**
- 🟠 [PortSwigger SQLi Labs](https://portswigger.net/web-security/sql-injection) (Free Lab)
- 🟠 [PortSwigger XSS Labs](https://portswigger.net/web-security/cross-site-scripting) (Free Lab)

**Key Concepts:**
- SQLi: `' OR '1'='1` → Union-based → Blind
- XSS: Reflected, Stored, DOM-based

**Interview Questions:**
- ❓ Explain Union-based SQLi step by step

---

#### A10: SSRF
- [ ] Server-Side Request Forgery
- [ ] AWS metadata endpoint exploitation

**Resources:**
- 🟠 [PortSwigger SSRF](https://portswigger.net/web-security/ssrf) (Free Lab)

**Key Concepts:**
- SSRF → internal services access
- AWS: `http://169.254.169.254/latest/meta-data/iam/security-credentials/`

</details>

---

<details>
<summary><strong>🔧 Burp Suite Mastery</strong> <code>Tool</code></summary>

#### Proxy, Repeater & Intruder
- [ ] Master Proxy workflow
- [ ] Learn Repeater for manual testing
- [ ] Understand Intruder modes

**Resources:**
- 🟠 [PortSwigger Burp Academy](https://portswigger.net/burp/documentation/desktop/getting-started) (Free)

**Interview Questions:**
- ❓ How do you test IDOR with Burp?

</details>

---

### Month 3 — Git + SOC Basics

<details>
<summary><strong>💻 Git & GitHub Portfolio</strong> <code>Career</code></summary>

#### Git Fundamentals
- [ ] Git commands (init, clone, commit, push, pull)
- [ ] Branching and .gitignore

**Resources:**
- 🟢 [Pro Git Book](https://git-scm.com/book/en/v2) (Free)

**Interview Questions:**
- ❓ How would you use git blame in security code review?

</details>

---

<details>
<summary><strong>🛡️ SOC Fundamentals</strong> <code>Blue Team</code></summary>

#### SIEM & Logs
- [ ] SIEM architecture (Splunk, Sentinel)
- [ ] Windows Event IDs
- [ ] MITRE ATT&CK framework

**Resources:**
- 🟠 [THM SOC Level 1](https://tryhackme.com/path/outline/soclevel1) (Paid Lab)
- 🟢 [Splunk Training](https://www.splunk.com/en_us/training/free-courses/) (Free)

**Interview Questions:**
- ❓ What Windows Event ID detects Pass-the-Hash?

</details>

---

## Phase 2️⃣ — Core Offensive Security (Months 4–7)

<details>
<summary><strong>🔐 Active Directory Attacks</strong> <code>High Value</code></summary>

#### BloodHound Enumeration
- [ ] Install and run SharpHound
- [ ] Identify Domain Admin paths

**Resources:**
- 🟠 [BloodHound](https://github.com/BloodHoundAD/BloodHound) (Free Lab)
- 🟠 [THM AD Basics](https://tryhackme.com/room/activedirectorybasics) (Paid Lab)

**Interview Questions:**
- ❓ What is BloodHound and SharpHound?

---

#### Kerberoasting
- [ ] Request TGS tickets
- [ ] Crack RC4 hashes with hashcat

**Resources:**
- 🟠 [Impacket](https://github.com/fortra/impacket) (Free Lab)

**Interview Questions:**
- ❓ Explain difference between Kerberoasting and AS-REP Roasting

</details>

---

<details>
<summary><strong>🪟 Windows Privilege Escalation</strong> <code>High Value</code></summary>

#### WinPEAS & Enumeration
- [ ] Run WinPEAS tool
- [ ] Check token privileges

**Resources:**
- 🟠 [PEASS-ng](https://github.com/peass-ng/PEASS-ng) (Free Lab)

**Interview Questions:**
- ❓ You have SeImpersonatePrivilege. Escalate to SYSTEM?

</details>

---

## Phase 3️⃣ — Advanced & Certifications (Months 8–11)

<details>
<summary><strong>🏆 OSCP Exam Preparation</strong> <code>Gold Standard</code></summary>

#### OSCP Course & Labs
- [ ] Complete PEN-200 materials
- [ ] Practice 70+ lab machines
- [ ] Master buffer overflow
- [ ] Learn pivoting & tunneling

**Resources:**
- 🟠 [Offensive Security PEN-200](https://www.offsec.com/courses/pen-200/) (Paid - ₹124,000)
- 🟠 [TJNull OSCP List](https://docs.google.com/spreadsheets/d/1dwSMIAPIam0PuRBkCiDI88pU3yzrqqHkDtBngUHNCw8/) (Free Lab)

**Interview Questions:**
- ❓ Walk through your methodology on a new machine

</details>

---

## Phase 4️⃣ — AI Security Specialist (Months 12–15)

<details>
<summary><strong>🤖 OWASP LLM Top 10</strong> <code>Emerging</code></summary>

#### Prompt Injection & Jailbreaking
- [ ] Understand direct prompt injection
- [ ] Learn indirect injection attacks
- [ ] Master jailbreaking techniques

**Resources:**
- 🟠 [Gandalf by Lakera](https://gandalf.lakera.ai) (Free Lab)
- 🟢 [OWASP LLM Top 10](https://owasp.org/www-project-top-10-for-large-language-model-applications/) (Free)

**Interview Questions:**
- ❓ What is indirect prompt injection? Give real scenario

</details>

---

## Phase 5️⃣ — Job Ready (Months 16–18)

<details>
<summary><strong>💼 Technical Interview Mastery</strong> <code>Career</code></summary>

#### Interview Preparation
- [ ] Master top 5 security topics
- [ ] Know attack + defense for each
- [ ] Practice live hacking
- [ ] Write sample pentest reports

**Resources:**
- 🟠 [HTB Academy Interview Prep](https://academy.hackthebox.com) (Free)

**Interview Questions:**
- ❓ Tell me about a machine you hacked
- ❓ How would you approach black-box pentesting?

</details>

---

## 💰 Salary Timeline

| Stage | Months | Role | Expected Salary |
|-------|--------|------|-----------------|
| **After Phase 1** | 3 | Junior SOC Analyst | ₹8–10 LPA |
| **After Phase 2** | 7 | Security Engineer (eJPT) | ₹12–15 LPA |
| **After Phase 3** | 11 | Penetration Tester (OSCP) | ₹18–22 LPA |
| **After Phase 4** | 15 | AI Security Specialist | ₹25–30+ LPA |

---

## 🎓 Certifications

| Cert | Cost | Timeline | Difficulty |
|------|------|----------|-----------|
| **eJPT** | ~₹200 | Month 6 | Beginner |
| **OSCP** | ~₹124,000 | Month 10 | Advanced |
| **AI Red Team** | Self-study | Month 14 | Expert |

---

## 📚 More Files

- 📋 [5 Portfolio Projects](PROJECTS.md)
- ❓ [Top 50 Interview Questions](INTERVIEW_GUIDE.md)
- 🔗 [All 300+ Resources](RESOURCES.md)

---

## 🚀 Getting Started

1. Start Phase 1 — one subtopic/day
2. Track progress — check off boxes
3. Build projects — portfolio > certs early
4. Join communities — HackTheBox, TryHackMe, CTFs
5. Apply early — don't wait for OSCP

---

## 💡 Success Tips

✅ **Consistency > Intensity** — 1hr daily beats 5hr once/week

✅ **Learn by Doing** — hands-on labs matter most

✅ **Document** — blog posts, writeups = social proof

✅ **Network** — LinkedIn, Twitter, communities

✅ **Practice explaining** — clear communication = better interviews

---

**Made with 🛡️ for B.Tech CSE freshers**

*Start now. Stay consistent. Become a security pro.* 🎯

*Last Updated: June 2026*
