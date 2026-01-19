# **04 — Browser Interaction Tests**

This stage evaluates whether a BadUSB device can open a **web browser** and perform **safe, controlled navigation**.  
It remains fully non‑destructive and does not interact with any real services beyond loading a harmless URL.

---

## **Purpose**
Once a browser is open, a BadUSB device may be able to:

- Navigate to URLs  
- Trigger downloads  
- Submit forms  
- Interact with cloud services  
- Exfiltrate typed data  

This test helps you determine:

- Whether the system allows browser launch via keyboard shortcuts  
- Whether navigation to a safe URL is possible  
- Whether security tooling intercepts or blocks automated browser control  
- Whether focus control is predictable  

If a system blocks browser automation at this stage, it significantly reduces the risk of remote interaction.

---

## **What This Test Does**
The payload for this stage:

1. Opens the default browser using a standard OS shortcut or menu sequence  
2. Navigates to a **safe, non‑interactive URL** (e.g., `about:blank` or a benign local file)  
3. Types a short marker string into the address bar or page (depending on OS behaviour)  
4. Stops immediately  

It does **not**:

- Submit forms  
- Trigger downloads  
- Interact with external services  
- Execute scripts  
- Attempt persistence  

This keeps the test safe for production systems.

---

## **Expected Behaviour**
### **Pass**
The browser opens and successfully navigates to the safe URL.  
The marker text appears where expected.

### **Fail**
The browser cannot be opened, navigation is blocked, or security tooling intercepts the attempt.

### **Partial**
The browser opens but navigation fails, or navigation works but typing is blocked or filtered.

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- Some managed environments block browser automation entirely — this is a strong defensive signal.  
- Navigation to local URLs (e.g., `about:blank`) is recommended for maximum safety.  
- This test is safe to run repeatedly and leaves no trace.

---

## **Next Step**
If this test passes, continue to: /tests/05_filesystem/ to evaluate whether the system allows a BadUSB device to create or modify files in a controlled, harmless way.
