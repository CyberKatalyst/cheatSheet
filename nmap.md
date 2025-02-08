# 🚀 **Nmap Cheat Sheet**

A quick reference guide for using **Nmap** effectively in **CTFs** and **security assessments**.

---

## 📡 1. Scan Types

| **Flag**   | **Description**                      | **Example**                  |
|:-----------|:------------------------------------|:-----------------------------|
| `-sS`      | SYN (stealth) scan                  | `nmap -sS <target>`          |
| `-sU`      | UDP scan                            | `nmap -sU <target>`          |
| `-sV`      | Service/version detection           | `nmap -sV <target>`          |
| `-O`       | OS detection                        | `nmap -O <target>`           |
| `-sC`      | Run default NSE scripts             | `nmap -sC <target>`          |
| `-A`       | Aggressive scan (OS, version, scripts, traceroute) | `nmap -A <target>` |

---

## ⚙️ 2. Timing & Performance

| **Flag**   | **Description**                      | **Example**                  |
|:-----------|:------------------------------------|:-----------------------------|
| `-T4`      | Faster scan timing (aggressive speed) | `nmap -T4 <target>`         |
| `-T0` to `-T5` | Timing templates (`0` = slowest, `5` = fastest) | `nmap -T3 <target>` |
| `-Pn`      | Skip host discovery (assume host is up) | `nmap -Pn <target>`         |

---

## 🎯 3. Port Scanning Options

| **Flag**   | **Description**                      | **Example**                  |
|:-----------|:------------------------------------|:-----------------------------|
| `-p`       | Specify ports to scan               | `nmap -p 22,80,443 <target>` |
| `-p-`      | Scan all 65,535 TCP ports           | `nmap -p- <target>`          |
| `-F`       | Fast scan (top 100 common ports)    | `nmap -F <target>`           |

---

## 🛠️ 4. Scripting & Advanced Enumeration

| **Flag**        | **Description**                      | **Example**                    |
|:----------------|:------------------------------------|:-------------------------------|
| `--script`      | Run specific NSE scripts            | `nmap --script=vuln <target>`  |
| `--script-args` | Pass arguments to scripts           | `nmap --script http-enum --script-args http.useragent="Mozilla" <target>` |

---

## 📥 5. Output Options

| **Flag**   | **Description**                      | **Example**                    |
|:-----------|:------------------------------------|:-------------------------------|
| `-oN`      | Save output in normal text format   | `nmap -oN output.txt <target>` |
| `-oX`      | Save output in XML format           | `nmap -oX output.xml <target>` |
| `-oG`      | Save output in grepable format      | `nmap -oG output.gnmap <target>` |
| `-oA`      | Save output in all formats (normal, XML, grepable) | `nmap -oA scan_results <target>` |

---

## 🔍 6. Verbosity & Debugging

| **Flag**   | **Description**                      | **Example**                  |
|:-----------|:------------------------------------|:-----------------------------|
| `-v`       | Increase verbosity (detailed output)| `nmap -v <target>`           |
| `-vv`      | Even more detailed output           | `nmap -vv <target>`          |
| `-d`       | Debugging output (for troubleshooting) | `nmap -d <target>`        |

---

## 🚀 Comprehensive Example

```bash
nmap -sS -sV -A -T4 -p 1-1000 --script=vuln -oA full_scan <target>
```

- **What It Does:**
  - `-sS` = Stealth SYN scan
  - `-sV` = Service/version detection
  - `-A` = Aggressive scan (OS, scripts, traceroute)
  - `-T4` = Faster scanning speed
  - `-p 1-1000` = Scan ports 1 to 1000
  - `--script=vuln` = Run vulnerability detection scripts
  - `-oA full_scan` = Save output in all formats

