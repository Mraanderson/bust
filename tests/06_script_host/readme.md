# **06 — Script Host Access Tests**

This stage evaluates whether a BadUSB device can open **script execution environments** and run **trivial, non‑destructive commands**.  
It remains fully safe and does not create or modify any files, nor does it execute anything harmful.

---

## **Purpose**
If a BadUSB can access a script host, it may be able to:

- Run PowerShell commands  
- Execute shell scripts  
- Trigger automation engines  
- Bypass certain GUI restrictions  
- Chain into more advanced behaviours  

This test helps you determine:

- Whether script hosts can be launched via keyboard shortcuts  
- Whether execution policies or MDM controls block script engines  
- Whether trivial commands can run without prompts  
- Whether the environment is restricted (e.g., Constrained Language Mode in PowerShell)  

Blocking script hosts is one of the strongest defensive measures against HID‑based attacks.

---

## **What This Test Does**
The payload for this stage:

1. Opens a script host such as:  
   - **PowerShell** (Windows)  
   - **CMD with PowerShell call** (Windows fallback)  
   - **Terminal with a shell command** (Linux/macOS)  
2. Runs a **harmless, read‑only command**, such as:  
   - `Write-Output "BUST Test"`  
   - `echo "BUST Test"`  
3. Leaves the output visible  
4. Stops immediately  

It does **not**:

- Modify files  
- Change system settings  
- Download anything  
- Attempt persistence  
- Escalate privileges  

This keeps the test safe for production systems.

---

## **Expected Behaviour**
### **Pass**
The script host opens and the trivial command executes successfully.

### **Fail**
The script host is blocked, restricted, or triggers a security prompt.

### **Partial**
The script host opens but the command fails, or the host runs in a restricted mode (e.g., PowerShell Constrained Language Mode).

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- Many enterprise systems enforce strict script‑execution policies — this is a strong defensive signal.  
- PowerShell may open but run in a restricted mode, which still counts as a **partial** result.  
- This test is safe to run repeatedly and leaves no trace.

---

## **Next Step**
If this test passes, continue to: /tests/07_persistence_lab_only/ to evaluate whether a BadUSB device could perform **lab‑only**, **non‑destructive**, **reversible** persistence actions in a controlled environment.
