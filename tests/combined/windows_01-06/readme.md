# **Combined Test 01–06 (Windows)**

This combined payload runs BUST stages 01 through 06 in sequence and logs each step into a visible Notepad window.  
It provides a real-time, user-friendly checklist so the operator can see exactly what the device is attempting.

The combined test remains:

- Fully non-destructive  
- Safe for production systems  
- Transparent and auditable  
- User-scope only  
- No persistence  
- No privilege escalation  

---

## **What This Combined Test Does**

1. Opens Notepad  
2. Prints a BUST header and checklist  
3. Runs each stage (01–06)  
4. After each stage, returns to Notepad and logs the attempt  
5. For Stage 03, captures `whoami` output and pastes it into Notepad  
6. Continues until all stages are attempted  

---

## **Checklist Output Example**

[BUST] Combined Test — Windows

[01] Basic HID ............. attempted
[02] App Launch ............ attempted
[03] Shell Access .......... attempted
whoami: DESKTOP-12345\User
[04] Browser Interaction .... attempted
[05] Filesystem Write ....... attempted
[06] Script Host Access ..... attempted

---

## **Safety Notes**

- All actions are visible to the user  
- No files are modified except a harmless temp file in Stage 05  
- No network interaction beyond loading example.com  
- No persistence  
- No elevation  

---

## **Files**

- `payload_combined_01-06.txt` — The HID payload  
