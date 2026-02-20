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

![Security Groups](screenshots/security-groups.png)

**Description:**
Role-Based Access Control (RBAC) implemented using domain security groups:

* IT-Support
* HR-Users
* Finance-Users

Permissions are assigned to groups rather than individual users, reflecting enterprise best practices.

---

## Group Policy Management

### Group Policy Console

![Group Policy](screenshots/group-policy.png)

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

### Automated User Provisioning

![PowerShell Automation](screenshots/powershell-automation.png)

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

