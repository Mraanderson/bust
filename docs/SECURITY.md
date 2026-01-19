# **Security Policy**

BUST (BadUSB Safety Tester) is a defensive, non‑destructive project designed to help system owners understand and reduce their exposure to keystroke‑injection attacks.  
This document explains how security concerns, disclosures, and responsible use are handled.

---

## **Supported Versions**

BUST is a simple, static project with no runtime components.  
All versions of the repository are considered supported for:

- Documentation corrections  
- Safety improvements  
- Payload clarity  
- Non‑destructive behaviour guarantees  

There are **no** compiled binaries, services, or network‑reachable components.

---

## **Reporting a Vulnerability**

If you believe you have found:

- A safety issue  
- A payload that behaves unexpectedly  
- A test that is not fully non‑destructive  
- A documentation error that could mislead users  
- A scenario where BUST could be misused  

…please open a **GitHub Issue** with the label: **security** or contact the repository maintainer privately if the concern requires discretion.

When reporting, please include:

- A clear description of the issue  
- Steps to reproduce  
- Expected vs. actual behaviour  
- Environment details (OS, device, BadUSB platform)  

We will review and respond promptly.

---

## **Responsible Use**

BUST is intended for:

- Blue‑team assessments  
- Defensive research  
- Exposure mapping  
- Policy validation  
- Education and awareness  

It must **only** be used on systems you own or are explicitly authorised to test.

BUST must **not** be used for:

- Gaining unauthorised access  
- Bypassing security controls on systems you do not control  
- Delivering harmful payloads  
- Obfuscating malicious behaviour  

The project is intentionally designed to avoid destructive or offensive capabilities.

---

## **Scope of Security Concerns**

Because BUST is a defensive toolkit, security concerns typically relate to:

- Ensuring payloads remain safe and reversible  
- Preventing accidental destructive behaviour  
- Avoiding ambiguity that could lead to misuse  
- Maintaining transparency and auditability  

BUST does **not** include:

- Exploit code  
- Privilege escalation techniques  
- Malware  
- Obfuscation  
- Network‑based attacks  

Any contribution that introduces these will be rejected.

---

## **Disclosure Expectations**

If a vulnerability or safety issue is found:

- Please report it privately first  
- Allow maintainers time to investigate  
- Avoid public disclosure until a fix or clarification is available  

This ensures the project remains safe for all users.

---

## **Security Philosophy**

BUST is built on three pillars:

1. **Safety First**  
   Every payload must be harmless, reversible, and transparent.

2. **Clarity Over Cleverness**  
   No obfuscation, no tricks, no hidden behaviour.

3. **Defensive Intent**  
   The goal is to reveal exposure, not exploit it.

---

## **Thank You**

Security feedback strengthens the project and helps keep the community safe.  
If you take the time to report an issue, you’re contributing directly to a safer ecosystem.
