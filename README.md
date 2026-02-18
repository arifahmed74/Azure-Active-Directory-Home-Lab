# Azure Active Directory Home Lab

## Overview

This project documents the creation of a cloud-hosted Active Directory lab environment using Microsoft Azure and Windows Server 2022. The lab simulates core enterprise IT infrastructure and common help desk administrative tasks.

---

## Lab Architecture

```
MacOS Admin Device
        |
        | Remote Desktop (RDP)
        v
Azure Virtual Machine (Windows Server 2022)
        |
        v
Active Directory Domain (itlab.local)
        |
        +-- Organizational Units
        +-- Users
        +-- Security Groups
        +-- Group Policy Objects
```

---

## Technologies Used

* Microsoft Azure
* Windows Server 2022
* Active Directory Domain Services (AD DS)
* DNS Server
* Group Policy Management
* Remote Desktop Protocol (RDP)

---

## Azure Deployment

### Azure Virtual Machine

<img width="1268" height="809" alt="Screenshot 2026-02-18 at 12 41 49 PM" src="https://github.com/user-attachments/assets/6a889517-e11c-43f1-81da-32d2dc8970f5" />


**Description:**
Windows Server 2022 virtual machine deployed using Azure Free Trial subscription.

---

## Domain Controller Configuration

### Server Manager Dashboard
<img width="1221" height="525" alt="dashboard manager" src="https://github.com/user-attachments/assets/f951e58e-b66d-4e48-83eb-f17b43bfc528" />


**Description:**
Server Manager used to install and manage Active Directory Domain Services.

---

### Domain Controller Promotion

<img width="1272" height="717" alt="Screenshot 2026-02-18 at 12 49 23 PM" src="https://github.com/user-attachments/assets/0645df0d-ebb4-438e-9319-bc4b364d7b07" />

**Description:**
Server promoted to Domain Controller creating the `itlab.local` domain.

---

## Active Directory Configuration

### Active Directory Users and Computers
<img width="793" height="596" alt="Screenshot 2026-02-18 at 3 48 58 PM" src="https://github.com/user-attachments/assets/70abf823-c762-42dd-ac46-af5866f46c74" />



**Description:**
Centralized management console for domain users and organizational units.

---

### Organizational Units Structure

<img width="1280" height="712" alt="Screenshot 2026-02-18 at 1 50 24 PM" src="https://github.com/user-attachments/assets/9794b6df-be1f-42dd-8ea1-030ab164b180" />


**Description:**
Department-based OU structure simulating enterprise organization.

---

### User Account Creation

<img width="1280" height="712" alt="Screenshot 2026-02-18 at 1 50 24 PM" src="https://github.com/user-attachments/assets/df075569-e175-415f-b068-186eb4699c01" />


**Description:**
Employee accounts created and managed within Active Directory.

---

### Security Groups

![Security Groups](screenshots/security-groups.png)

**Description:**
Role-based access control using domain security groups.

---

## Group Policy Management

### Group Policy Console

![Group Policy](screenshots/group-policy.png)

**Description:**
Security policies configured to enforce password and account lockout rules.

---

## Administrative Tasks Practiced

* User account provisioning
* Password reset operations
* Account enable/disable
* Security group assignment
* Organizational Unit management
* Policy enforcement using Group Policy

---

## Skills Demonstrated

* Cloud infrastructure deployment (Azure)
* Windows Server administration
* Identity & Access Management
* Active Directory configuration
* IT Help Desk operational workflows

---

## Future Improvements

* Domain-joined workstation deployment
* Microsoft Entra ID hybrid integration
* Intune device management
* PowerShell automation scripts

---

## Author

**Arif Ahmed**
