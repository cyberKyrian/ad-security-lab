# Active Directory Security Lab: Real-World AD Hardening

### Author: Kyrian Onyeagusi
🔗 [LinkedIn](https://www.linkedin.com/in/kyrian-onyeagusi/) | 📧 [Email](mailto:kyrianoc18@gmail.com)


### Focus: Enterprise-Relevant AD Misconfiguration and Hardening Lab

---

## Tools & Skills Demonstrated

* Active Directory Domain Services
* Group Policy Management
* Windows Server & Client Hardening
* Access Control Lists (ACLs)
* Event Viewer & Audit Policy Configuration
* User Role Review & Access Minimization

---

## Lab Overview

In this project, I simulated a basic enterprise Active Directory environment with real-world misconfigurations and then hardened the environment using industry best practices. The goal was to demonstrate practical knowledge of domain management, vulnerability remediation, and Windows enterprise security controls.

This lab was designed to mirror issues commonly found in business environments and provide actionable solutions to prevent misuse, privilege escalation, and data leaks.

---

## Environment Setup

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

> ✅ **Screenshot:** Active Directory installation and domain promotion wizard showing domain setup as `cyberlab.local`
> ![Screenshot showing domain setup](./screenshots/domain-setup-1.png)
> ![Screenshot showing domain setup](./screenshots/domain-setup-2.png)

> ✅ **Screenshot:** `jdoe@cyberlab.local` created in ADUC
> ![Screenshot showing user setup](./screenshots/user-setup-1.png)

> ✅ **Screenshot:** CLIENT01 joined to domain successfully
> ![Screenshot showing user setup](./screenshots/user-setup-2.png)

---

## Simulated Misconfigurations & Hardenings

### 1. Weak Password Policy

**Issue Simulated:**

* Minimum password length: 4
* Password complexity: Disabled

**Why it matters:** Weak passwords are easy targets for brute-force attacks and credential stuffing.

> ✅ **Screenshot:** Group Policy settings showing weak password configuration
> ![Screenshot showing user setup](./screenshots/password-policy-1.png)

**Hardening Applied:**

* Enabled password complexity
* Increased minimum length to 12
* Set password expiry to 30 days

> ✅ **Screenshot:** Group Policy updated to reflect secure password policy
> ![Screenshot showing user setup](./screenshots/password-policy-2.png)

---

### 2. Excessive Admin Privileges

**Issue Simulated:**

* Regular user `jdoe` was added to the `Domain Admins` group

**Why it matters:** Over-provisioning users increases the attack surface for privilege escalation.

> ✅ **Screenshot:** ADUC showing `jdoe` as a member of Domain Admins
> ![Screenshot showing user setup](./screenshots/domain-admin-1.png)

**Hardening Applied:**

* Removed `jdoe` from Domain Admins
* Principle of least privilege enforced

> ✅ **Screenshot:** Group membership of `jdoe` restricted to default Users group
> ![Screenshot showing user setup](./screenshots/domain-user.png)

---

### 3. Insecure Shared Folder Permissions

**Issue Simulated:**

* Folder on CLIENT01 shared with “Everyone: Full Control”

**Why it matters:** Open access can lead to unauthorized modification or exfiltration of sensitive data.

> ✅ **Screenshot:** Folder sharing settings showing “Everyone” with Full Control
> ![Screenshot showing user setup](./screenshots/sharing-1.png)

**Hardening Applied:**

* Removed Everyone
* Assigned access only to necessary users/groups with minimal privileges

> ✅ **Screenshot:** Modified sharing and NTFS permissions to reflect secure access
> ![Screenshot showing user setup](./screenshots/sharing-2.png)

---

### 4. Lack of Audit Logging

**Issue Simulated:**

* No logon/logoff or privilege use audit policies enabled

**Why it matters:** Without auditing, detecting misuse or breaches becomes difficult

> ✅ **Screenshot:** Local Security Policy showing default (weak) audit settings
> ![Screenshot showing user setup](./screenshots/audit-log-2.png)

**Hardening Applied:**

* Enabled advanced auditing policies via Group Policy
* Policies set for logon events, privilege use, object access, and account management
* Validated logs via Event Viewer

> ✅ **Screenshot:** Event Viewer log showing successful logon event for `jdoe`
> ![Screenshot showing user setup](./screenshots/audit-log-3.png)
> ![Screenshot showing user setup](./screenshots/audit-log-4.png)

---

## Tools & Skills Demonstrated

* Active Directory Domain Services
* Group Policy Management
* Windows Server & Client Hardening
* Access Control Lists (ACLs)
* Event Viewer & Audit Policy Configuration
* User Role Review & Access Minimization

---

## 📌 Conclusion

This lab mirrors real-life scenarios that cybersecurity analysts or IT security personnel face when securing enterprise networks. Each misconfiguration reflects a common vulnerability, and the corresponding hardening step shows my ability to recognize, resolve, and document cybersecurity risks in an Active Directory environment.


## 🔗 Connect

**Kyrian Onyeagusi**
🔗 [LinkedIn](https://www.linkedin.com/in/kyrian-onyeagusi/) | 📧 [Email](mailto:kyrianoc18@gmail.com)
