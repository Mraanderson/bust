# **BUST — BadUSB Safety Tester**
![BUST Logo](https://raw.githubusercontent.com/Mraanderson/bust/main/docs/banner.jpg)
  ---------------------------
Safe HID payloads for testing your system’s resistance to keystroke‑injection attacks.  
No damage, no persistence — just clear visibility into what a rogue USB device could do.

---

## **What is BUST?**
BUST is a **blue‑team‑focused**, **non‑destructive** toolkit for evaluating how a computer responds to BadUSB‑style HID injection.  
It provides a structured set of harmless payloads you can run from devices like the **Cardputer ADV**, **Rubber Ducky**, or any HID‑emulating microcontroller.

The goal isn’t exploitation — it’s **exposure mapping**.  
BUST helps you understand:

- What an untrusted USB keyboard can do on a given system  
- Which shortcuts and shells are allowed  
- What the OS blocks or prompts for  
- Where hardening is effective  
- Where policy gaps exist  

All without risking system stability or modifying anything permanently.

---

## **Why BUST Exists**
BadUSB attacks are often overlooked because HID devices are implicitly trusted.  
Most organisations never test:

- Whether shells can be opened  
- Whether scripts can run  
- Whether browsers can be driven  
- Whether files can be written  
- Whether persistence is possible  

BUST provides a **safe, repeatable, auditable** way to test these behaviours.

This is **not** a red‑team exploit pack.  
This is a **defensive assessment toolkit**.

---

## **Test Categories**
BUST is organised from **lowest risk** to **highest capability**, allowing you to stop at any stage depending on your environment.

### **1. Basic HID Acceptance**
Tests whether the system recognises the device as a keyboard.  
Examples:  
- Type a marker string into the focused window  
- Send simple keystrokes  

---

### **2. Application Launch Tests**
Checks whether global shortcuts can open benign applications.  
Examples:  
- Open Notepad / Terminal  
- Type a harmless message  

---

### **3. Shell Access Tests**
Determines whether a BadUSB can reach a command interpreter.  
Examples:  
- Run `whoami`, `hostname`, `date`  

---

### **4. Browser Interaction Tests**
Evaluates whether the HID can drive a network‑facing application.  
Examples:  
- Open the default browser  
- Navigate to a safe URL  

---

### **5. Filesystem Write Tests**
Checks whether the HID can create or modify files.  
Examples:  
- Create a temp file  
- Write a marker string  

---

### **6. Script Host Access Tests**
Probes whether script engines can be opened with flags.  
Examples:  
- Launch PowerShell with `-NoProfile`  
- Run a trivial command  

---

### **7. Lab‑Only Persistence Tests**
Never run on production systems.  
Examples:  
- Append a harmless line to a profile script  
- Create a one‑shot scheduled task  

---

## **Recommended Test Order**
From least intrusive to most revealing:

1. Basic HID acceptance  
2. Application launch  
3. Shell access  
4. Browser navigation  
5. Filesystem write  
6. Script host access  
7. Lab‑only persistence  

This ordering ensures you can stop early if the system is already hardened.

---

Each test folder contains:

- A description  
- Expected behaviour  
- Pass/fail indicators  
- A safe payload example  

---

## **Project Philosophy**
BUST is built on three principles:

1. **Transparency** — every test is visible and understandable.  
2. **Non‑destructiveness** — no payload causes harm or disruption.  
3. **Defensive focus** — the goal is to reveal what *could* be done, not to do it.  

---

## **Contributing**
Contributions are welcome as long as they follow the safety rules:

- No destructive payloads  
- No persistence outside the lab‑only folder  
- No privilege escalation  
- No obfuscation  
- No malware or malware‑adjacent behaviour  

---

## **License**
MIT License — because defensive security research should be open, safe, and accessible.

