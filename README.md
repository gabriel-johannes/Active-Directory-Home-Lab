# 🖥️ Active Directory Home Lab

![Windows Server](https://img.shields.io/badge/-Windows_Server-0078D6?&style=for-the-badge&logo=Windows&logoColor=white)
![Active Directory](https://img.shields.io/badge/-Active_Directory-003366?&style=for-the-badge&logo=Microsoft&logoColor=white)
![VirtualBox](https://img.shields.io/badge/-VirtualBox-183A61?&style=for-the-badge&logo=VirtualBox&logoColor=white)
![Status](https://img.shields.io/badge/Status-Active-brightgreen?&style=for-the-badge)

## 📌 Objective

This project documents the setup and configuration of a fully functional **Active Directory home lab** using virtualization. The lab simulates a real enterprise environment and covers AD DS installation, user/group management, Group Policy configuration, domain joining, and security hardening — skills directly applicable to IT support, sysadmin, and cybersecurity roles.

---

## 🧪 Lab Environment

| Component          | Details                              |
|--------------------|--------------------------------------|
| Hypervisor         | VirtualBox / VMware                  |
| Domain Controller  | Windows Server 2019/2022             |
| Client Machine     | Windows 10/11                        |
| Domain Name        | lab.local *(or your domain name)*    |
| Network            | Internal NAT Network                 |

---

## 🗺️ Lab Topology

```
┌─────────────────────────────────────┐
│           VirtualBox / VMware       │
│                                     │
│   ┌─────────────────┐               │
│   │  Windows Server │  DC01         │
│   │  AD DS / DNS    │  192.168.1.10 │
│   └────────┬────────┘               │
│            │  Internal Network      │
│   ┌────────┴────────┐               │
│   │  Windows 10/11  │  CLIENT01     │
│   │  Domain Member  │  192.168.1.20 │
│   └─────────────────┘               │
└─────────────────────────────────────┘
```

---

## ⚙️ Steps Completed

### 1. Installing & Configuring AD DS
- Deployed Windows Server and promoted it to a Domain Controller
- Configured DNS and created a new Active Directory forest
- Set up static IP addressing for the domain controller

### 2. Creating Users, Groups & Organisational Units (OUs)
- Created Organisational Units (OUs) to mirror a real company structure (e.g. IT, HR, Finance)
- Created user accounts and assigned them to appropriate OUs and security groups
- Configured account policies (password length, complexity, lockout thresholds)

### 3. Group Policy (GPO) Configuration
- Created and linked GPOs to specific OUs
- Enforced password policies and account lockout policies domain-wide
- Configured desktop restrictions and software deployment via GPO
- Used `gpupdate /force` and `gpresult` to verify policy application

### 4. Joining Machines to the Domain
- Configured client machine network settings to point to the DC for DNS
- Joined Windows 10/11 client to the domain
- Verified domain membership and tested user login from client machine

### 5. AD Security & Hardening
- Disabled default Administrator account and renamed it
- Audited privileged group membership (Domain Admins, Enterprise Admins)
- Configured audit policies to log logon events and account changes
- Applied principle of least privilege to user accounts

---

## 📂 Repository Structure

```
Active-Directory-Home-Lab/
│
├── README.md
├── screenshots/
│   ├── ad-ds-installation.png
│   ├── ou-structure.png
│   ├── gpo-configuration.png
│   └── domain-join.png
└── configs/
    └── gpo-notes.md       ← document your GPO settings here
```

---

## 📸 Screenshots

> *(Add screenshots of your lab to the `/screenshots` folder and reference them here)*

| Step                        | Screenshot |
|-----------------------------|------------|
| AD DS Installation          | *(add screenshot)* |
| OU & User Structure         | *(add screenshot)* |
| GPO Configuration           | *(add screenshot)* |
| Client Domain Join          | *(add screenshot)* |
| Security Hardening Settings | *(add screenshot)* |

---

## 🧠 Skills Demonstrated

- Windows Server administration and AD DS deployment
- Identity and access management (IAM) using Active Directory
- Group Policy configuration and enforcement
- Domain environment setup and client management
- Security hardening of Active Directory environments
- Virtualisation using VirtualBox/VMware

---

## 📚 References

- [Microsoft AD DS Documentation](https://learn.microsoft.com/en-us/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)
- [Group Policy Reference](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/dn385267(v=ws.11))

---

*Part of my cybersecurity portfolio — Gabriel Johannes | NUST Honours in Communication Networks*
