# Active-Directory-Azure-Lab
# Active Directory Domain Services in Azure

A hands-on project implementing Active Directory Domain Services (AD DS) in Microsoft Azure, demonstrating enterprise-level identity and access management skills.

## 📋 Project Overview

This project simulates a real-world enterprise Active Directory environment deployed in Azure. It covers the complete lifecycle of AD administration including infrastructure setup, domain configuration, user management, organizational structure, and security policy implementation.

## 🎯 Objectives

- Deploy and configure Windows Server 2022 as a Domain Controller in Azure
- Automate bulk user provisioning using PowerShell
- Implement organizational structure with Organizational Units (OUs)
- Configure and enforce Group Policy Objects (GPOs)
- Manage user accounts and perform password resets
- Implement role-based access control (RBAC) using security groups

## 🏗️ Architecture

```
Azure Cloud Environment
├── Resource Group
│   └── Virtual Network
│       └── Windows Server 2022 VM (Domain Controller)
│           ├── Active Directory Domain Services
│           ├── Organizational Units (4)
│           ├── User Accounts (Bulk Created)
│           ├── Security Groups
│           └── Group Policy Objects
```

## 🛠️ Technologies Used

- **Cloud Platform:** Microsoft Azure
- **Operating System:** Windows Server 2022
- **Directory Services:** Active Directory Domain Services (AD DS)
- **Scripting:** PowerShell
- **Networking:** Azure Virtual Network, DNS

## 📝 Implementation Steps

### 1. Azure Infrastructure Setup

**Created Azure Resources:**
- Resource Group for project organization
- Virtual Network (VNet) with appropriate subnet configuration
- Network Security Group (NSG) with RDP access rules

### 2. Domain Controller Deployment

**Deployed Windows Server 2022 VM:**
- Configured static private IP address
- Installed Active Directory Domain Services role
- Promoted server to Domain Controller
- Configured DNS settings for the domain

### 3. Bulk User Creation with PowerShell

**Automated user provisioning:**
- Created PowerShell script to read from `names.txt` file
- Generated usernames using naming convention (first initial + last name)
- Created 100+ user accounts efficiently

```powershell
# Example of bulk user creation
Import-Module ActiveDirectory
New-ADUser -Name "John Smith" -SamAccountName "jsmith" ...
```
<img width="1512" height="982" alt="Screenshot 2026-02-26 at 11 44 45 PM" src="https://github.com/user-attachments/assets/382d56e5-a5da-4fef-8c46-f1f072d5f46a" />


### 4. Organizational Structure

**Created 4 Organizational Units (OUs):**
- 🏢 **Management** - Executive and senior leadership accounts
- 💻 **IT** - IT department and technical staff
- 📊 **Sales** - Sales team members
- 👥 **HR** - Human Resources personnel

**Purpose:** Organize users logically for easier management and targeted Group Policy application

### 5. User Account Management

**Practiced common helpdesk tasks:**
- Password reset procedures for locked-out users
- Account unlock operations
- User property modifications
- Account enable/disable operations

<img width="1512" height="982" alt="Screenshot 2026-02-27 at 12 25 29 AM" src="https://github.com/user-attachments/assets/24f4655d-81fa-4314-9a73-7da9ce4c5eab" />


### 6. Group Policy Configuration

**Implemented security policies:**

**Password Policy GPO:**
- Minimum password length: 9 characters
- Password complexity requirements: Enabled
- Password history: 5 passwords remembered
- Maximum password age: 90 days
- Minimum password age: 30 day

<img width="1512" height="982" alt="Screenshot 2026-02-27 at 12 09 04 AM" src="https://github.com/user-attachments/assets/f629e557-b4a9-4744-b116-4e1cee9fdfab" />

**Account Lockout Policy GPO:**
- Account lockout threshold: 3 invalid attempts
- Account lockout duration: 10 minutes
- Reset account lockout counter after: 10 minutes

<img width="1512" height="982" alt="Screenshot 2026-02-27 at 12 10 40 AM" src="https://github.com/user-attachments/assets/995845b9-f11f-4c06-b72a-50d388befb16" />


**Applied GPOs to specific OUs** to demonstrate targeted policy enforcement

### 7. File Share Permissions & Security Groups

**Implemented Role-Based Access Control:**
- Created shared folder with sample images from the internet
- Created security group for authorized access
- Configured NTFS permissions to restrict access
- Added specific users to the security group
- Tested access control with different user accounts

**Demonstrated:**
- Security group creation and management
- NTFS permissions configuration
- Principle of least privilege access

<img width="1512" height="982" alt="Screenshot 2026-02-27 at 12 33 58 AM" src="https://github.com/user-attachments/assets/e34a18ec-504f-4e1e-9f0c-e556ce8ef384" />


## 💡 Skills Demonstrated

### Technical Skills
- ✅ Azure resource deployment and management
- ✅ Windows Server administration
- ✅ Active Directory Domain Services configuration
- ✅ PowerShell scripting and automation
- ✅ Group Policy Object creation and management
- ✅ User and group management
- ✅ File system security and permissions
- ✅ DNS configuration

### IT Support Skills
- ✅ Password reset procedures
- ✅ Account troubleshooting
- ✅ Access control management
- ✅ Security policy implementation
- ✅ Documentation and logging

## 📊 Key Achievements

- 🚀 Reduced user provisioning time by **95%** through PowerShell automation
- 🔐 Implemented enterprise-grade password and lockout policies
- 📁 Configured granular file access controls using security groups
- 🎯 Organized 100+ users across 4 departmental OUs
- 📝 Created audit logs for user creation and policy changes


