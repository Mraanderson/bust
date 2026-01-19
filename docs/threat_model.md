# **BUST — Threat Model**

This document outlines the threat model behind the BadUSB Safety Tester.  
It defines what BUST assumes, what it does not assume, and what risks it is designed to evaluate.

---

## **Threat Actor Assumptions**
BUST models an attacker who:

- Has **physical access** to the target system  
- Can plug in a USB device  
- Uses a device that emulates a keyboard (HID)  
- Cannot escalate privileges without user-level access  
- Cannot bypass OS-level security prompts  

This represents a realistic BadUSB scenario.

---

## **Attacker Capabilities**
The attacker can:

- Send keystrokes at high speed  
- Trigger shortcuts  
- Open applications  
- Interact with shells  
- Navigate browsers  
- Write files  
- Attempt persistence (lab only)

The attacker cannot:

- Exploit kernel vulnerabilities  
- Inject drivers  
- Install unsigned software  
- Execute code outside HID input  
- Break encryption  
- Escalate privileges without OS permission  

---

## **Defender Assumptions**
The defender:

- Controls the system being tested  
- Has authority to perform the assessment  
- Wants to understand exposure, not exploit it  
- May be using enterprise security tooling  
- May have USB restrictions in place  

---

## **What BUST Evaluates**
BUST reveals whether a BadUSB device can:

- Gain initial foothold  
- Open a shell  
- Interact with the network  
- Write files  
- Execute scripts  
- Establish persistence  

Each stage corresponds to a real-world attacker milestone.

---

## **What BUST Does Not Evaluate**
BUST does **not** test:

- Kernel-level USB exploits  
- Driver vulnerabilities  
- USB stack overflow attacks  
- Firmware-level compromise  
- Hardware implants  
- DMA attacks (e.g., Thunderbolt)  

Those are outside the HID threat model.

---

## **Risk Interpretation**
A system that fails early (e.g., HID blocked) is strongly hardened.  
A system that passes all stages is highly exposed to BadUSB-style attacks.

Neither outcome is inherently “good” or “bad” — it depends on environment and risk tolerance.

---

## **Conclusion**
This threat model ensures BUST remains focused, safe, and aligned with real-world HID attack scenarios.  
It provides defenders with actionable insight into how a rogue USB keyboard could behave on their systems.
