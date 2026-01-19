# **BUST — Test Checklist**

A quick, structured checklist for running the full BadUSB Safety Tester suite.  
Use this to track results, compare systems, and document exposure.

---

## **Before You Begin**
- [ ] You are testing on a system you are authorised to assess  
- [ ] You understand that BUST is non-destructive  
- [ ] You have read the methodology  
- [ ] You have a BadUSB-capable device ready  
- [ ] You have a safe environment for lab-only tests (Stage 07)

---

## **01 — Basic HID Acceptance**
- [ ] Device recognised as keyboard  
- [ ] Marker text appears in focused window  
- [ ] No prompts or warnings triggered  
**Result:** Pass / Partial / Fail

---

## **02 — Application Launch**
- [ ] Global shortcut works  
- [ ] Benign app opens (Notepad/Terminal)  
- [ ] Marker text appears inside app  
**Result:** Pass / Partial / Fail

---

## **03 — Shell Access**
- [ ] Shell opens successfully  
- [ ] Identification commands run (`whoami`, `hostname`, etc.)  
- [ ] No privilege prompts or blocks  
**Result:** Pass / Partial / Fail

---

## **04 — Browser Interaction**
- [ ] Browser opens  
- [ ] Navigation to safe URL succeeds  
- [ ] Marker text appears in address bar or page  
**Result:** Pass / Partial / Fail

---

## **05 — Filesystem Write**
- [ ] Temporary file created  
- [ ] Marker text written  
- [ ] No blocks or quarantines  
**Result:** Pass / Partial / Fail

---

## **06 — Script Host Access**
- [ ] Script host opens (PowerShell, Bash, etc.)  
- [ ] Trivial command executes  
- [ ] No execution policy blocks  
**Result:** Pass / Partial / Fail

---

## **07 — Persistence (Lab Only)**
- [ ] Marker added to profile script OR  
- [ ] One-shot scheduled task created OR  
- [ ] Startup marker file created  
- [ ] Change successfully reverted  
**Result:** Pass / Partial / Fail

---

## **Overall Exposure Summary**
- [ ] HID accepted  
- [ ] Apps launchable  
- [ ] Shell accessible  
- [ ] Browser controllable  
- [ ] Files writable  
- [ ] Script hosts available  
- [ ] Persistence possible (lab only)

Use this summary to guide hardening and policy changes.
