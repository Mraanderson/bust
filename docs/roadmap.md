# **BUST Roadmap**

A forward‑looking plan for improving the BadUSB Safety Tester project.  
This roadmap focuses on clarity, safety, cross‑platform support, and a polished user experience.

---

## **1. README Enhancements**

Improve the project’s first impression and usability.

- Add a centered hero section (logo + title + tagline)
- Add optional badges (status, safety, license, defensive scope)
- Add a Quick Start section for new users
- Add a Documentation section linking to all `/docs` files
- Add a Repository Structure overview
- Add a “Why This Matters” section for non‑technical readers

---

## **2. Combined Test Improvements**

Enhance the multi‑stage combined test experience.

- Finalize the Windows combined 01–06 test
- Add a Linux combined 01–06 test
- Add a macOS combined 01–06 test
- Add a cross‑platform combined test selector
- Improve the Notepad‑based live checklist formatting
- Add optional “verbose mode” with more detailed logging

---

## **3. Platform Expansion**

Extend BUST beyond Windows.

- Create `/tests_linux/` with 01–07 equivalents
- Create `/tests_mac/` with 01–07 equivalents
- Add platform‑specific READMEs explaining differences
- Add detection notes for hardened environments (AppArmor, SIP, etc.)

---

## **4. Device‑Specific Payload Variants**

Support more HID‑capable hardware.

- Evil‑Cardputer‑optimized payloads (current default)
- Rubber Ducky v1/v2 variants
- CircuitPython HID variants
- Flipper Zero HID variants
- M5Stack Cardputer ADV native HID API variants
- Add a compatibility matrix to `/docs`

---

## **5. Documentation Enhancements**

Strengthen clarity and onboarding.

- Add diagrams showing test progression
- Add a “How to interpret results” guide
- Add a “Hardening recommendations” section
- Add a “Common failure modes” troubleshooting page
- Add a “Safe testing environments” guide

---

## **6. Persistence Testing Improvements**

Keep persistence tests safe, reversible, and explicit.

- Add Linux persistence + undo pair
- Add macOS persistence + undo pair
- Add a unified “undo_all” payload for lab resets
- Add a persistence audit checklist

---

## **7. Optional GUI Tools (Future Exploration)**

Long‑term, nice‑to‑have ideas.

- A small desktop viewer that parses BUST logs
- A web‑based “BUST Report Generator”
- A visual comparison tool for multiple test runs

---

## **8. Community & Contribution**

Make the project more welcoming and collaborative.

- Add CONTRIBUTING.md
- Add issue templates (bug, enhancement, safety concern)
- Add PR templates
- Add a “How to write safe payloads” guide

---

## **9. Release Milestones**

### **v0.2 — Current Work**

- Windows tests 01–07 complete  
- Combined 01–06 test  
- Core documentation (methodology, threat model, glossary, security, conduct)

### **v0.3 — Next Steps**

- README polish  
- Linux/macOS test scaffolding  
- Device compatibility notes  
- Roadmap publication  

### **v1.0 — Stable Release**

- Full cross‑platform test suite  
- Full documentation set  
- Combined tests for all OSes  
- Undo payloads for all persistence tests  
- Hardened, audited payload library  
