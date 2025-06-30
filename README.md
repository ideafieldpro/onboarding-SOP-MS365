# Onboarding SOP—Microsoft 365 & Entra ID

This repository houses a **Standard Operating Procedure (SOP)** template structure for all SOPs and an example process for onboarding new users in Microsoft 365 and Entra ID. It demonstrates:

- Foundational IT operations skills
- Process documentation best practices
- Security- and compliance-conscious user provisioning

---

## 🔧 Contents

- SOP Template Structure
- Flow diagram of the onboarding process
- Example SOP documentation

---

## 📗 Highlights

- Clear, step-by-step guidance aligned with enterprise workflows  
- Includes troubleshooting tips for common issues  
- Change history is versioned for transparency

---

## ✅ Usage

Feel free to review or adapt for your own M365 environments.  

---

## 📋 SOP Template Structure

Every SOP you write should follow a consistent structure:

1. Title
2. Purpose
3. Scope
4. Prerequisites
5. Roles & Responsibilities
6. Step-by-Step Instructions
7. Troubleshooting & Tips
8. Change History

---

## 🪜 Onboarding Flow Diagram

> Log in > Create user > Assign roles > Enable MFA > Add to groups > Configure > Configure device access (Intune)

---


# 🧾 Standard Operating Procedure (SOP): Onboarding a New User in Microsoft 365 and Entra ID

## 🗂️ Purpose

This SOP outlines the steps for onboarding a new employee by provisioning a Microsoft 365 account, assigning licenses, configuring security, and ensuring access to core services.

---

## 📌 Scope

Applies to all IT administrators responsible for account creation and user provisioning in Microsoft 365 and Entra ID (Azure AD) environments.

---

## ✅ Prerequisites

- Admin access to **Microsoft 365 Admin Center** and **Entra ID**
- A valid Microsoft 365 license available for assignment
- New hire information:
  - Full name
  - Email alias
  - Department/role
  - Group/team memberships

---

## 👥 Roles & Responsibilities

| Role                     | Responsibility                                     |
|--------------------------|----------------------------------------------------|
| IT Service Desk Engineer | Execute the onboarding process                     |
| HR                       | Provide accurate new hire details                  |
| Security Admin           | Enforce access policies and MFA requirements       |

---

## 🧪 Step-by-Step Instructions

### 1. Log In
- Access the **Microsoft 365 Admin Center**: https://admin.microsoft.com  
- Authenticate using your admin credentials.

---

### 2. Create a New User
- Navigate to `Users > Active users > Add a user`
- Fill in:
  - First name / Last name
  - Display name
  - Username (e.g., j.doe@company.onmicrosoft.com)
- Choose to **auto-generate a password** or set a secure custom password.
- Enable the option to require a password change on first sign-in.

---

### 3. Assign Licenses
- Select the appropriate Microsoft 365 license (e.g., E3 or E5).
- Enable key services:
  - Outlook
  - OneDrive
  - Teams
  - SharePoint

---

### 4. Assign Roles (Optional)
- Under “Roles,” assign:
  - Standard user (default)  
  - Admin roles if applicable (e.g., Helpdesk Admin, User Admin)

---

### 5. Enable MFA
- Open **Entra ID portal**: https://entra.microsoft.com  
- Go to `Users > Select user > Authentication methods`
- Require user to **register for multi-factor authentication**.

---

### 6. Add User to Groups
- Still in Entra ID:
  - Navigate to `Groups > Add to group`
  - Add the user to security groups (e.g., Marketing, IT Support)
  - Add to Microsoft Teams via Teams Admin Center or app

---

### 7. Configure Device Access (Optional)
- If using **Intune**:
  - Open [Endpoint Manager](https://endpoint.microsoft.com)
  - Assign device compliance or configuration policies
  - Add user to device groups or auto-enrollment scope

---

### 8. Finalize and Notify
- Email HR or the user with:
  - Login instructions
  - Temporary password
  - MFA setup steps
- Document the account creation in your internal asset/inventory system.

---

## 🧯 Troubleshooting & Tips

| Issue                        | Resolution                                      |
|-----------------------------|-------------------------------------------------|
| User can’t sign in          | Check license assignment, reset password        |
| MFA not triggering          | Reconfigure authentication methods in Entra     |
| Missing Teams access        | Add to team manually or confirm sync delay      |
| Can't assign license        | Check license availability and domain status    |

---

## 🧾 Change History

| Date       | Author           | Notes                |
|------------|------------------|----------------------|
| 2025-06-28 | Craig Sheffield  | Initial documentation |

