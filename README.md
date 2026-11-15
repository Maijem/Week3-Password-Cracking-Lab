# 🔐 Module 1 — Password Cracking with JTR

**🎯 Task:** Crack the password of `My Locked PDF1.pdf` using JTR John and JTR Johnny on Windows.

## 🛠️ Tools
- John the Ripper 1.9.0-jumbo-1 (64-bit Windows binaries, zip)
- Johnny GUI 2.2 (Windows)
- PDF Hash Extractor — onlinehashcrack.com/tools-pdf-hash-extractor.php

## 📝 Steps

1. **⬇️ Install JTR**
   - Downloaded from openwall.com/john
   - Extracted the zip to Downloads

2. **⬇️ Install Johnny**
   - Downloaded Johnny 2.2 (Windows) from openwall.info/wiki/john/johnny
   - Ran the installer

3. **🔗 Link Johnny to John**
   - Opened Johnny → Settings → Browse
   - Navigated to `john-1.9.0-jumbo.../run/`
   - Selected `john.exe`
   - Johnny detected the version (1.9.0-jumbo-1) ✅

4. **🧮 Extract the PDF hash**
   - Uploaded `My Locked PDF1.pdf` to onlinehashcrack.com's PDF Hash Extractor
   - Copied the output hash (starts with `$pdf$`)

5. **📋 Prep the hash file**
   - Pasted hash into Notepad
   - Checked for and removed any stray characters (e.g. leading `b'`)
   - Saved as `hash1.txt` (All Files type, not `.txt.txt`)

6. **⚡ Run the attack**
   - In Johnny: Open password file → selected `hash1.txt`
   - Clicked "Start new attack"
   - Waited for completion ⏳

7. **🎉 Result**
   - Password cracked: `password1`
   - Opened the PDF, entered the password → unlocked successfully 🔓

## 🚩 Flag
```
nw{networkwalks_flag1_jtr_270521_1}
```

# 🔐 Module 2 — Password Cracking with Networkwalks Tools

**🎯 Task:** Crack the password of `My Locked PDF1.pdf` using the Networkwalks Hash Calculator and Password Cracker — both browser-based, no installation required. 🌐

## 🛠️ Tools
- Networkwalks Hash Calculator — networkwalks.com/hash-calculator/
- Networkwalks Password Cracker — networkwalks.com/password-cracker/

## 📝 Steps

1. **⬇️ Get the file**
   - Downloaded `My Locked PDF1.pdf` from the lab page

2. **🧮 Extract the PDF hash**
   - Opened the Networkwalks Hash Calculator
   - Uploaded the locked PDF
   - Tool detected it as password-protected and generated a crackable hash (`$pdf$...` format — not the generic MD5/SHA file checksums also shown on the page) ⚠️
   - Copied the full hash value

3. **⚡ Run the cracker**
   - Opened the Networkwalks Password Cracker
   - Pasted the `$pdf$...` hash into the PDF HASH field
   - Left it on the built-in wordlist 📖
   - Clicked "START CRACKING"

4. **🎉 Result**
   - Tool displayed "PASSWORD CRACKED SUCCESSFULLY" ✅
   - Password recovered: `password1`
   - Opened the PDF, entered the password → unlocked successfully 🔓

