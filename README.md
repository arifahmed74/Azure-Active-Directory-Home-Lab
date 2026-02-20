# Azure Active Directory Home Lab (Enterprise Identity & Administration)

## Overview

This project documents the design and deployment of a cloud-hosted Active Directory lab environment using **Microsoft Azure** and **Windows Server 2022**.
The lab simulates a real-world enterprise IT environment and demonstrates common **Help Desk** and **Junior System Administrator** responsibilities including identity management, security policy enforcement, and automation using PowerShell.

---

## Lab Objectives

* Deploy cloud infrastructure using Microsoft Azure
* Configure Active Directory Domain Services (AD DS)
* Promote Windows Server to Domain Controller
* Implement Organizational Units and security groups
* Enforce enterprise password and lockout policies
* Perform common IT administrative workflows
* Automate user provisioning with PowerShell

---

## Lab Architecture

```
Admin Device (macOS)
        |
        | Remote Desktop (RDP)
        v
Azure Virtual Machine
(Windows Server 2022)
        |
        v
Active Directory Domain
itlab.local
        |
        +-- Organizational Units
        |      ├── Company
        |      ├── IT
        |      ├── HR
        |      └── Finance
        |
        +-- Domain Users
        +-- Security Groups
        +-- Group Policy Objects
        +-- PowerShell Automation
```

---

## Technologies Used

* Microsoft Azure (Free Trial)
* Windows Server 2022
* Active Directory Domain Services
* DNS Server
* Group Policy Management
* PowerShell
* Remote Desktop Protocol (RDP)

---

## Azure Deployment

### Azure Virtual Machine

<img width="1268" height="809" alt="Screenshot 2026-02-18 at 12 41 49 PM" src="https://github.com/user-attachments/assets/6a889517-e11c-43f1-81da-32d2dc8970f5" />

**Description:**
A Windows Server 2022 virtual machine was deployed in Microsoft Azure to host enterprise directory services.

---

## Domain Controller Configuration

### Server Manager Dashboard

<img width="1221" height="525" alt="dashboard manager" src="https://github.com/user-attachments/assets/f951e58e-b66d-4e48-83eb-f17b43bfc528" />


**Description:**
Server Manager was used to install Active Directory Domain Services and manage server roles.

---

### Domain Controller Promotion

<img width="1272" height="717" alt="Screenshot 2026-02-18 at 12 49 23 PM" src="https://github.com/user-attachments/assets/0645df0d-ebb4-438e-9319-bc4b364d7b07" />

**Description:**
The server was promoted to a Domain Controller, creating the **itlab.local** domain and configuring DNS services.

---

## Active Directory Configuration

### Active Directory Users and Computers

<img width="793" height="596" alt="Screenshot 2026-02-18 at 3 48 58 PM" src="https://github.com/user-attachments/assets/70abf823-c762-42dd-ac46-af5866f46c74" />

**Description:**
Primary administrative console used for identity and access management.

---

### Organizational Units Structure

<img width="1280" height="712" alt="Screenshot 2026-02-18 at 1 50 24 PM" src="https://github.com/user-attachments/assets/9794b6df-be1f-42dd-8ea1-030ab164b180" />

**Description:**
Department-based OU structure implemented to simulate enterprise organization and delegation.

---

### User Account Management
<img width="1280" height="712" alt="Screenshot 2026-02-18 at 1 50 24 PM" src="https://github.com/user-attachments/assets/df075569-e175-415f-b068-186eb4699c01" />

**Description:**
User accounts provisioned and managed within Active Directory.

---

## Security Groups (Role-Based Access Control)

### Security Groups
<img width="769" height="543" alt="creating IT support object group" src="https://github.com/user-attachments/assets/c6df9222-f551-4a68-a678-e5638547db23" />
<img width="807" height="575" alt="it group created" src="https://github.com/user-attachments/assets/ab5b66b6-a3f9-442b-9d9d-049c78c638a7" />
<img width="747" height="532" alt="addeding members in IT Support group" src="https://github.com/user-attachments/assets/91630720-9ef9-4fce-b254-c893b0d3308e" />
<img width="779" height="564" alt="adding shr into HR" src="https://github.com/user-attachments/assets/37ccf557-6e9f-4659-bbf9-d9acd2a23714" />
<img width="747" height="532" alt="addeding members in IT Support group" src="https://github.com/user-attachments/assets/9ab2a104-4df5-4eb6-a959-d811af047c5b" />

**Description:**
Role-Based Access Control (RBAC) implemented using domain security groups:

* IT-Support
* HR-Users
* Finance-Users

Permissions are assigned to groups rather than individual users, reflecting enterprise best practices.

---

## Group Policy Management

### Group Policy Console
<img width="785" height="562" alt="group mgmt editor policies " src="https://github.com/user-attachments/assets/de0e1312-6ebe-489a-8f3a-d52076362f17" />
<img width="759" height="548" alt="new gpo company security policy" src="https://github.com/user-attachments/assets/103fca1a-3354-47cd-8cc4-6238c011f1ba" />
<img width="785" height="562" alt="min password length" src="https://github.com/user-attachments/assets/33b34cd5-284c-4756-950b-8d32eba9d575" />
<img width="798" height="569" alt="password complexity " src="https://github.com/user-attachments/assets/446eac3d-9dda-423e-9bf2-709021633fd0" />
<img width="791" height="581" alt="account lockout threshold " src="https://github.com/user-attachments/assets/99df84a7-e27b-4bda-bec7-1036955d2e0b" />
<img width="783" height="557" alt="account lockout duration" src="https://github.com/user-attachments/assets/6c55e7c3-e77c-4d60-b70f-dae86850f6cb" />
<img width="787" height="561" alt="account policy , password polcies " src="https://github.com/user-attachments/assets/53977600-e230-4cba-bb64-379d79b900b4" />
<img width="788" height="564" alt="min password age" src="https://github.com/user-attachments/assets/fb2a6987-7137-4921-81f4-2b69d490b586" />
<img width="788" height="569" alt="reset acount lockout counter" src="https://github.com/user-attachments/assets/ad071af9-6b0b-4b1e-893d-e1bb043d3792" />
<img width="749" height="533" alt="reset password" src="https://github.com/user-attachments/assets/dc5bd361-fb78-4452-92bc-2a15d17be7fb" />
<img width="977" height="507" alt="GPU update" src="https://github.com/user-attachments/assets/f039b124-48c0-4da9-ba09-25c4ce0fc0b6" />

**Description:**
Group Policy Management Console used to enforce centralized security configurations.

### Security Policies Implemented

* Minimum password length: **8 characters**
* Password complexity: **Enabled**
* Account lockout threshold: **5 failed attempts**
* Lockout duration: **15 minutes**
* Automatic policy enforcement across the domain

---

## PowerShell Automation
<img width="788" height="596" alt="scripts folfer in c drive" src="https://github.com/user-attachments/assets/6f396b9d-f4f2-4e4c-8154-6a82ca5ac012" />
<img width="972" height="542" alt="scriptfile notepad" src="https://github.com/user-attachments/assets/e4c61a70-4e26-4ae6-80f3-f46c4f44d406" />
<img width="1041" height="519" alt="notepad users for script" src="https://github.com/user-attachments/assets/e1f8e548-8b31-4852-af21-02800a06a661" />
<img width="975" height="507" alt="user created via script" src="https://github.com/user-attachments/assets/5e2bf183-2e4e-46c8-bce2-0cdc7ec34220" />
<img width="758" height="523" alt="users added after script was succesful" src="https://github.com/user-attachments/assets/6c3eebb8-fe82-40a0-8008-1dd2b7d85f05" />

### Automated User Provisioning


**Description:**
Developed a PowerShell script to automate Active Directory user creation using CSV input.

#### Features

* Bulk user provisioning
* Secure password assignment
* Automatic OU placement
* Enabled accounts upon creation
* Error handling and execution feedback

#### Example Workflow

1. HR provides employee spreadsheet (CSV)
2. Script imports user data
3. Accounts created automatically in Active Directory

This simulates real enterprise onboarding processes.

---

## Administrative Tasks Practiced

### Identity Administration

* User account provisioning
* Password reset operations
* Account enable/disable
* Organizational Unit management
* Security group assignment

### Security Administration

* Policy enforcement via Group Policy
* Password complexity validation
* Account lockout configuration

### Automation & Troubleshooting

* PowerShell scripting
* Distinguished Name (OU path) troubleshooting
* Script execution policy configuration
* Bulk account deployment

---

## Skills Demonstrated

* Cloud infrastructure deployment (Azure)
* Windows Server administration
* Active Directory configuration
* Identity & Access Management (IAM)
* Role-Based Access Control (RBAC)
* Enterprise security policy enforcement
* PowerShell automation
* IT Help Desk operational workflows

---

## Key Learning Outcomes

This lab demonstrates hands-on experience with enterprise identity systems and simulates responsibilities commonly performed by:

* IT Help Desk Technicians
* Systems Administrators
* IT Support Engineers
* Junior Cloud Administrators

---

## Future Improvements

* Domain-joined workstation deployment
* Hybrid Microsoft Entra ID integration
* Microsoft Intune device management
* PowerShell automation expansion
* Monitoring and logging integration

---

## Author

**Arif Ahmed**

Bachelor’s Degree – Computer Science & Information Technology
Cybersecurity & Digital Forensics Concentration

---

## Repository Purpose

This repository serves as a portfolio project demonstrating practical, hands-on IT administration skills using enterprise technologies in a cloud-hosted lab environment.

