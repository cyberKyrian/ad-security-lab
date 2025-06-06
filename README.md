# 🧱 Active Directory Security Lab: Real-World AD Hardening

### 👤 Author: Kyrian Onyeagusi

### 🧠 Focus: Enterprise-Relevant AD Misconfiguration and Hardening Lab

### 🌍 Location: Fully Remote (Nigeria)

---

## 🧰 Lab Overview

In this project, I simulated a basic enterprise Active Directory environment with real-world misconfigurations and then hardened the environment using industry best practices. The goal was to demonstrate practical knowledge of domain management, vulnerability remediation, and Windows enterprise security controls.

This lab was designed to mirror issues commonly found in business environments and provide actionable solutions to prevent misuse, privilege escalation, and data leaks.

---

## 🖥️ Environment Setup

### Domain Controller (DC01):

* Windows Server 2019
* Active Directory Domain Services (AD DS) installed
* Domain: `cyberlab.local`

### Client Workstation (CLIENT01):

* Windows 10 (Domain-joined)
* Used to simulate a regular employee workstation

### Domain User:

* Username: `jdoe`
* Created in ADUC under the `Users` OU

> ✅ **Screenshot:** Active Directory installation and domain promotion wizard showing domain setup as `cyberlab.local` (./screenshots/domain-setup-1.png)
> ✅ **Screenshot:** `jdoe@cyberlab.local` created in ADUC
> ✅ **Screenshot:** CLIENT01 joined to domain successfully

---

## 🔓 Simulated Misconfigurations & Hardenings

### 🔹 1. Weak Password Policy

**Issue Simulated:**

* Minimum password length: 4
* Password complexity: Disabled

**Why it matters:** Weak passwords are easy targets for brute-force attacks and credential stuffing.

> ✅ **Screenshot:** Group Policy settings showing weak password configuration

**Hardening Applied:**

* Enabled password complexity
* Increased minimum length to 12
* Set password expiry to 30 days

> ✅ **Screenshot:** Group Policy updated to reflect secure password policy

---

### 🔹 2. Excessive Admin Privileges

**Issue Simulated:**

* Regular user `jdoe` was added to the `Domain Admins` group

**Why it matters:** Over-provisioning users increases the attack surface for privilege escalation.

> ✅ **Screenshot:** ADUC showing `jdoe` as a member of Domain Admins

**Hardening Applied:**

* Removed `jdoe` from Domain Admins
* Principle of least privilege enforced

> ✅ **Screenshot:** Group membership of `jdoe` restricted to default Users group

---

### 🔹 3. Insecure Shared Folder Permissions

**Issue Simulated:**

* Folder on CLIENT01 shared with “Everyone: Full Control”

**Why it matters:** Open access can lead to unauthorized modification or exfiltration of sensitive data.

> ✅ **Screenshot:** Folder sharing settings showing “Everyone” with Full Control

**Hardening Applied:**

* Removed Everyone
* Assigned access only to necessary users/groups with minimal privileges

> ✅ **Screenshot:** Modified sharing and NTFS permissions to reflect secure access

---

### 🔹 4. Lack of Audit Logging

**Issue Simulated:**

* No logon/logoff or privilege use audit policies enabled

**Why it matters:** Without auditing, detecting misuse or breaches becomes difficult

> ✅ **Screenshot:** Local Security Policy showing default (weak) audit settings

**Hardening Applied:**

* Enabled advanced auditing policies via Group Policy
* Policies set for logon events, privilege use, object access, and account management
* Validated logs via Event Viewer

> ✅ **Screenshot:** Event Viewer log showing successful logon event for `jdoe`

---

## 🔐 Tools & Skills Demonstrated

* Active Directory Domain Services
* Group Policy Management
* Windows Server & Client Hardening
* Access Control Lists (ACLs)
* Event Viewer & Audit Policy Configuration
* User Role Review & Access Minimization

---

## 📌 Conclusion

This lab mirrors real-life scenarios that junior cybersecurity analysts or IT security personnel face when securing enterprise networks. Each misconfiguration reflects a common vulnerability, and the corresponding hardening step shows my ability to recognize, resolve, and document cybersecurity risks in an Active Directory environment.
