# **02 — Application Launch Tests**

This stage evaluates whether the system allows a BadUSB device to trigger **global keyboard shortcuts** and open **benign applications**.  
It is still a safe, non‑destructive test and does not execute any commands beyond launching an app and typing a short message.

---

## **Purpose**
Many BadUSB attacks rely on the ability to:

- Open a text editor  
- Open a terminal or shell  
- Trigger OS‑level shortcuts  
- Shift focus to a predictable application  

If the system blocks or restricts these actions, it significantly reduces the attack surface.

This test helps you determine:

- Whether global shortcuts are honoured  
- Whether application launches are allowed  
- Whether the OS prompts, blocks, or ignores the attempt  
- Whether focus control is possible  

---

## **What This Test Does**
The payload for this stage:

1. Uses a standard OS shortcut to open a **benign application**  
   - Notepad (Windows)  
   - Terminal/Text Editor (Linux/macOS)  
2. Types a short, harmless marker message  
3. Stops immediately  

It does **not**:

- Run commands  
- Modify files  
- Interact with the network  
- Attempt persistence  
- Escalate privileges  

This keeps the test safe for production systems.

---

## **Expected Behaviour**
### **Pass**
The application opens normally and the marker text appears inside it.

### **Fail**
The shortcut is blocked, ignored, or triggers a security prompt.

### **Partial**
The application opens but typing fails, or typing works but the shortcut is intercepted by policy or security tooling.

---

## **Payload**
See `payload.txt` in this folder for the example script.

Payloads are intentionally simple so they can be adapted to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- If the system requires elevated privileges to open certain apps, this test may fail by design.  
- Some managed environments disable global shortcuts entirely — this is a strong defensive signal.  
- This test is safe to run repeatedly.

---

## **Next Step**
If this test passes, continue to: /tests/03_shell_access/ to evaluate whether the system allows a BadUSB device to open a shell and run harmless identification commands.
