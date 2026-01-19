# **BUST — Glossary**

A quick reference for terms used throughout the BadUSB Safety Tester project.

---

## **BadUSB**
A class of attacks where a USB device impersonates another device type (usually a keyboard) to perform malicious actions.

---

## **HID (Human Interface Device)**
A USB device class that includes keyboards and mice.  
BadUSB devices often emulate HID because it is implicitly trusted.

---

## **Keystroke Injection**
Sending automated keystrokes to a system to perform actions without user consent.

---

## **Payload**
A script or sequence of keystrokes executed by a BadUSB device.

---

## **Marker Text**
A harmless string used to verify that a payload executed successfully.

---

## **Execution Policy**
Rules that determine whether scripts can run (e.g., PowerShell execution policy).

---

## **Persistence**
Any mechanism that allows code or behaviour to continue after reboot or logout.

---

## **Constrained Language Mode**
A restricted PowerShell environment that limits available commands.

---

## **MDM (Mobile Device Management)**
Enterprise tooling that enforces security policies on endpoints.

---

## **Startup Folder**
A directory where files can be placed to run automatically at login.

---

## **Temporary Directory**
A safe location for short-lived files (`%TEMP%`, `/tmp`).

---

## **Global Shortcut**
A keyboard shortcut that works regardless of which application is focused.

---

## **Shell**
A command-line interface such as CMD, PowerShell, Bash, or Zsh.

---

## **Lab-Only Test**
A test that should only be run on non-production systems due to its persistent nature.
