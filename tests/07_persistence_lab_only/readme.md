# **07 — Persistence Tests (Lab Only)**

This stage evaluates whether a BadUSB device could perform **basic, reversible persistence actions** in a controlled **lab environment**.  
These tests are **strictly non‑destructive**, but they must **never** be run on production systems.

---

## **Purpose**
Persistence is the point where a BadUSB attack moves from “momentary access” to “lasting impact.”  
Even harmless persistence tests can reveal:

- Whether profile scripts can be modified  
- Whether scheduled tasks can be created  
- Whether startup folders are writable  
- Whether execution policies block persistence mechanisms  
- Whether privilege boundaries prevent long‑term changes  

This stage helps you understand how well a system prevents **ongoing footholds** created through keystroke injection.

---

## **What This Test Does**
The payload for this stage performs **one** of the following safe, reversible actions (depending on OS):

1. **Appends a harmless marker line** to a user‑level profile script  
   - e.g., PowerShell profile, `.bashrc`, `.zshrc`  
2. **Creates a one‑shot scheduled task** that runs a benign command  
3. **Drops a harmless marker file** into a user‑level startup directory  

Each action is:

- Non‑destructive  
- Fully reversible  
- Contained to user‑level scope  
- Safe for lab systems  

It does **not**:

- Modify system‑level files  
- Create privileged tasks  
- Download or execute external content  
- Escalate privileges  
- Obfuscate behaviour  

---

## **Expected Behaviour**
### **Pass**
The persistence mechanism is created successfully and behaves as expected.

### **Fail**
The system blocks the modification, prevents task creation, or restricts access to startup locations.

### **Partial**
The persistence mechanism is created but is immediately removed, quarantined, or disabled by security tooling.

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Safety Notice**
- These tests are **lab‑only** by design.  
- Do not run them on production, corporate, or sensitive systems.  
- Always revert changes after testing.  
- Document results clearly for audit and hardening purposes.

---

## **Reverting Changes**
Each persistence test includes a matching **undo** step in its description.  
Reversal typically involves:

- Removing a marker line from a profile script  
- Deleting a scheduled task  
- Removing a startup file  

All changes are user‑level and easy to revert manually.

---

## **Next Step**
This is the final stage of the BUST suite.  
After completing this test, review your results and compare them against:

/docs/checklist.md
/docs/methodology.md

to build a clear picture of your system’s BadUSB exposure.
