# **01 — Basic HID Acceptance**

This test verifies the most fundamental capability of a BadUSB device:  
**Can the system recognise it as a keyboard and accept keystrokes?**

This is the safest and least intrusive test in the entire BUST suite.  
It performs no system changes, opens no applications, and runs no commands.

---

## **Purpose**
Before testing anything more advanced, you need to confirm that the target system:

- Accepts HID input from an untrusted USB device  
- Does not block or restrict keystrokes at the OS or policy level  
- Does not trigger device‑class restrictions, pop‑ups, or security prompts  

If this test fails, the system is already well‑hardened — and the rest of the suite is unnecessary.

---

## **What This Test Does**
The payload for this stage simply:

1. Types a short, unique marker string into whatever window is currently focused  
2. Stops immediately  

It does **not**:

- Open applications  
- Launch shells  
- Modify files  
- Interact with the network  
- Attempt persistence  

This makes it safe for production systems.

---

## **Expected Behaviour**
### **Pass**
You see the marker text appear in the currently focused input field.

### **Fail**
Nothing appears, or the system blocks the keystrokes entirely.

### **Partial**
Keystrokes appear delayed, filtered, or modified — indicating input sanitisation or security tooling.

---

## **Payload**
See `payload.txt` in this folder for the example script.

The payload is intentionally minimal so you can adapt it to your device’s scripting language (DuckyScript, CircuitPython, Cardputer ADV HID, etc.).

---

## **Notes**
- If the system is locked, this test will type into the lock screen field — this is expected and still counts as a pass.  
- If the system requires a trusted‑device whitelist, this test will fail by design.  
- This test is safe to run repeatedly.

---

## **Next Step**
If this test passes, proceed to: /tests/02_app_launch/ to evaluate whether the system allows global shortcuts and application launches.
