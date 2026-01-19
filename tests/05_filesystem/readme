# **05 — Filesystem Write Tests**

This stage evaluates whether a BadUSB device can create or modify files on the target system using only keystroke injection.  
It remains fully non‑destructive and writes only harmless marker content to safe, temporary locations.

---

## **Purpose**
If a BadUSB can write files, it opens the door to:

- Dropping scripts  
- Creating scheduled tasks  
- Modifying configuration files  
- Planting persistence mechanisms  
- Staging payloads for later execution  

This test helps you determine:

- Whether the system allows file creation via keyboard‑driven shell commands  
- Whether write access is restricted by policy or security tooling  
- Whether temporary directories are protected  
- Whether execution policies interfere with file creation  

A system that blocks or restricts filesystem writes significantly reduces the impact of HID‑based attacks.

---

## **What This Test Does**
The payload for this stage:

1. Opens a shell or text editor (depending on OS)  
2. Creates a **harmless temporary file** in a safe location, such as:  
   - `%TEMP%` (Windows)  
   - `/tmp` (Linux/macOS)  
3. Writes a short marker string into the file  
4. Closes the application or shell  
5. Stops immediately  

It does **not**:

- Modify existing files  
- Write to system directories  
- Create executable scripts  
- Attempt persistence  
- Escalate privileges  

This keeps the test safe for production systems.

---

## **Expected Behaviour**
### **Pass**
A temporary file is created successfully and contains the marker text.

### **Fail**
The file cannot be created, the directory is protected, or security tooling blocks the write.

### **Partial**
The file is created but writing fails, or writing succeeds but the file is immediately quarantined or deleted by security tools.

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- Some environments restrict write access even in temporary directories — this is a strong defensive signal.  
- If the system requires elevated privileges for file creation in certain paths, this test may fail by design.  
- This test is safe to run repeatedly and leaves only a harmless temp file that can be deleted manually or by the OS.

---

## **Next Step**
If this test passes, continue to: /tests/06_script_host/ to evaluate whether the system allows a BadUSB device to open script hosts and run trivial, non‑destructive commands.
