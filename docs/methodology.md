# **BUST — Testing Methodology**

This document explains the philosophy, structure, and reasoning behind the BadUSB Safety Tester suite.  
BUST is designed for defenders, auditors, and system owners who want a safe, repeatable way to evaluate BadUSB exposure.

---

## **Core Principles**
BUST is built on three foundational ideas:

### **1. Non‑Destructive by Design**
Every test is intentionally harmless.  
No payload modifies system settings, downloads content, or escalates privileges.

### **2. Transparent and Understandable**
All payloads are readable, simple, and easy to audit.  
There is no obfuscation, encoding, or trickery.

### **3. Defensive, Not Offensive**
BUST is not a red‑team toolkit.  
It reveals *what could happen* if a malicious HID device were plugged in — nothing more.

---

## **Test Progression**
The suite is structured from **lowest capability** to **highest capability**:

1. Basic HID acceptance  
2. Application launch  
3. Shell access  
4. Browser interaction  
5. Filesystem write  
6. Script host access  
7. Lab-only persistence  

This progression ensures:

- You can stop early if the system is already hardened  
- Each stage builds on the previous one  
- Risk remains minimal at every step  

---

## **How to Run Tests**
1. Connect your BadUSB-capable device  
2. Load the payload for the stage you want to test  
3. Observe behaviour  
4. Record results in the checklist  
5. Move to the next stage only if appropriate  

---

## **Interpreting Results**
### **Pass**
The system allows the tested behaviour.

### **Partial**
The system allows some behaviour but restricts or modifies other parts.

### **Fail**
The system blocks the behaviour entirely.

Partial results are often the most interesting — they reveal where controls exist but may not be fully effective.

---

## **Safety Boundaries**
- Stages 01–06 are safe for production systems  
- Stage 07 is **lab-only**  
- All persistence actions are reversible  
- No payloads contain harmful commands  

---

## **Using Results for Hardening**
BUST results can guide:

- Group Policy adjustments  
- MDM restrictions  
- USB device control policies  
- Script execution policies  
- Application whitelisting  
- Browser automation restrictions  
- Privilege separation  

The goal is not to “pass every test” — the goal is to understand exposure and reduce unnecessary risk.

---

## **Conclusion**
BUST provides a structured, safe, and transparent way to evaluate BadUSB attack surface.  
Use it to inform policy, improve hardening, and build confidence in your defensive posture.
