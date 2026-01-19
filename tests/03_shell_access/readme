# **03 — Shell Access Tests**

This stage evaluates whether a BadUSB device can open a **command‑line interface** and execute **harmless, read‑only commands**.  
It is still a safe, non‑destructive test and does not modify the system in any way.

---

## **Purpose**
Many real‑world BadUSB attacks rely on gaining access to a shell such as:

- CMD (Windows)  
- PowerShell (Windows)  
- Bash / Terminal (Linux, macOS)  

Once a shell is open, even simple commands can reveal valuable information or enable further actions.

This test helps you determine:

- Whether shells can be launched via keyboard shortcuts  
- Whether the OS prompts, blocks, or restricts shell access  
- Whether read‑only commands can be executed  
- Whether execution policies or MDM controls interfere  

If a system blocks shell access at this stage, it significantly reduces the attack surface.

---

## **What This Test Does**
The payload for this stage:

1. Opens a shell using a standard OS shortcut or menu sequence  
2. Runs **harmless identification commands**, such as:  
   - `whoami`  
   - `hostname`  
   - `date`  
3. Leaves the output visible  
4. Stops immediately  

It does **not**:

- Modify files  
- Change system settings  
- Interact with the network  
- Attempt persistence  
- Escalate privileges  

This keeps the test safe for production environments.

---

## **Expected Behaviour**
### **Pass**
A shell opens successfully and the identification commands run as expected.

### **Fail**
The shell cannot be opened, is blocked by policy, or triggers a security prompt.

### **Partial**
The shell opens but commands fail, or commands run but the shell is heavily restricted (e.g., limited PowerShell mode).

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- Some managed systems block CMD or PowerShell entirely — this is a strong defensive signal.  
- Linux/macOS environments may require different shortcuts depending on the desktop environment.  
- This test is safe to run repeatedly and leaves no trace beyond visible terminal output.

---

## **Next Step**
If this test passes, continue to: /tests/04_browser/ to evaluate whether the system allows a BadUSB device to open a browser and navigate to a safe URL.
