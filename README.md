# Week 3 — Password Cracking (Network Walks Internship)

## 📌 Overview
This repository documents **Week 3** of my Cybersecurity Internship at **Network Walks**, focused on password cracking techniques using **John the Ripper (JTR)** and **Network Walks (NW) Tools**. The goal was to understand how weak passwords can be recovered from hashed/protected files and to reinforce the importance of strong password policies.

> ⚠️ **Disclaimer:** All activities in this repository were performed in a **controlled lab environment** for educational purposes only, using files/passwords created for this exercise. This is not intended to promote unauthorized access to any system, account, or document.

---

## 🗂️ Tasks Completed

### 🔹 W3-PM1: Password Cracking with JTR (John the Ripper)
- Installed and configured **John the Ripper (JTR)** software on Windows.
- Learned the general JTR workflow:
  1. Extract the hash from the protected file.
  2. Feed the hash into JTR.
  3. Run a dictionary or brute-force attack to recover the plaintext password.
- Practiced cracking password hashes using JTR's built-in wordlists (`rockyou.txt`).

### 🔹 W3-PM2: Password Cracking with Network Walks Tools
- Cracked password-protected **PDF files** containing weak/sample passwords.
- Used online hash extraction tools to generate the PDF hash before running it through the cracker:
  - [Online Hash Crack – PDF Hash Extractor](https://www.onlinehashcrack.com/tools-pdf-hash-extractor.php)
  - [Network Walks Hash Calculator](https://networkwalks.com/hash-calculator/)
- Ran the extracted `$pdf$` hash through the **[Network Walks Password Cracker](https://networkwalks.com/password-cracker/)** — a browser-based dictionary-attack tool that hashes each word in a wordlist and matches it against the PDF hash (same underlying idea as JTR).
- Compared results from online tools vs. local JTR cracking to validate the recovered passwords.

---

## 🛠️ Tools & Resources Used
| Tool | Purpose |
|------|---------|
| John the Ripper (JTR) | Local password/hash cracking |
| Online Hash Crack (PDF Hash Extractor) | Extracting hash from PDF files |
| Network Walks Hash Calculator | Generating/verifying file hashes |
| [Network Walks Password Cracker](https://networkwalks.com/password-cracker/) | Online dictionary-attack tool to crack the extracted `$pdf$` hash |
| Windows OS | Lab environment |

---

## 🔑 General Workflow (PDF Password Cracking)

```bash
# Step 1: Extract the hash from a password-protected PDF
# (using pdf2john.py or an online PDF hash extractor tool)
pdf2john.py sample.pdf > pdf_hash.txt

# Step 2: Run John the Ripper (Windows build) against the extracted hash
john.exe pdf_hash.txt

# Step 3: Show the cracked password
john.exe --show pdf_hash.txt
```

---

## ✅ Results / Evidence

**PDF Hash Extracted:**
```
$pdf$4*4*128*-1028*1*16*ca7f72f11459cba469f1005a8765ed51*32*f32d8fa1bfbe2648226dffc39f7909ea0021446990b9e4114071a4d9104984c1*32*9322f50c29569712067a775264635e4954ccb1b99e209d664984054ffad30a6a
```

**Cracked Password:** `good-luck`

**Screenshots:**
| Description | File |
|--------------|------|
| JTR successfully recovering the PDF password | `screenshots/jtr_cracked_password.png` |
| Flag capture confirmation from Network Walks | `screenshots/flag_captured.png` |

**Flag Captured:** `nw{cybersecurity_flag_captured_2608}`

> 📁 Add the `hash_1.txt` file and the two screenshots above to a `screenshots/` (and `hashes/`) folder in this repo so the links resolve correctly on GitHub.

---

## 📚 Key Learnings
- Understood how password hashes are extracted from PDF files before cracking.
- Learned the difference between **dictionary attacks** and **brute-force attacks**.
- Practiced using both **command-line (JTR)** and **online hash tools** for cross-verification.
- Reinforced why **weak/common passwords** are easily cracked, highlighting the need for strong password policies (length, complexity, MFA).

---

## 📅 Internship Details
- **Program:** Cybersecurity Internship
- **Organization:** Network Walks
- **Week:** 3
- **Modules:** Password Cracking with JTR, Password Cracking with Network Walks Tools

---

## 📄 License
This repository is for educational and internship documentation purposes only.
