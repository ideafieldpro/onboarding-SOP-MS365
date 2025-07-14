# Onboarding SOP—Microsoft 365 & Entra ID

This repository houses a **Standard Operating Procedure (SOP)** template structure for all SOPs and an example process for onboarding new users in Microsoft 365 and Entra ID. It demonstrates:

- Foundational IT operations skills
- Process documentation best practices
- Security- and compliance-conscious user provisioning

---

## 🔧 Contents

- [SOP Template Structure](https://github.com/ideafieldpro/onboarding-SOP-MS365/edit/main/README.md#-sop-template-structure)
- [Flow of the onboarding process](https://github.com/ideafieldpro/onboarding-SOP-MS365/edit/main/README.md#-onboarding-flow-diagram)
- [Example SOP documentation](https://github.com/ideafieldpro/onboarding-SOP-MS365/edit/main/README.md#-standard-operating-procedure-sop-onboarding-a-new-user-in-microsoft-365-and-entra-id)
- [Troubleshooting](https://github.com/ideafieldpro/onboarding-SOP-MS365/edit/main/README.md#%EF%B8%8F-troubleshooting-scenarios)

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

---

## 🛠️ Troubleshooting Scenarios

Real-world issues encountered during device onboarding and how they were resolved.

---

### 🔐 1. User Unable to Log In — No Password Set

**Problem**  
After creating a new Microsoft 365 user, the Windows 10 VM asked for the user's password. However, the user never set one and could not log in.

**Cause**  
By default, Microsoft 365 cloud-only users are assigned random temporary passwords if one isn’t set manually.

**Solution**
1. Go to [https://admin.microsoft.com](https://admin.microsoft.com)
2. Navigate to **Users > Active Users > [User]**
3. Click **Reset password**
4. Set a known password and uncheck “Require user to change password at next login” (for test use)
5. Use the email and new password to sign in on the Windows 10 device
![brave_70FQH7bG8X](https://github.com/user-attachments/assets/b94603d1-79d0-4246-826b-b61f72894484)

---

### 🔒 2. Blocked During MFA Registration

**Problem**  
During sign-in, user is prompted to set up additional security info but sees an error:

> _"Your sign-in was blocked. Your organization requires this information to be set from specific locations or devices."_

**Cause**  
A Conditional Access policy in Entra ID restricts MFA registration to known/trusted devices or locations.

**Solution**
1. Go to [https://entra.microsoft.com](https://entra.microsoft.com)
2. Navigate to **Protection > Conditional Access**
3. Locate and **disable or modify** the MFA registration policy
   - OR exclude the test user
   - OR allow registration from **Any location**
4. Retry MFA registration or complete it on a trusted device
<img width="1878" height="1015" alt="brave_Oembsi5BJq" src="https://github.com/user-attachments/assets/f094b71f-f981-4001-bd9c-fb7f43a132e3" />

---

### 📧 3. Outlook Desktop Says "Account Not Supported"

**Problem**  
After device onboarding, Outlook on the Windows 10 VM shows:

> _"This account is not supported. Your account does not have permissions to access the new Outlook on Windows."_

**Cause**
- The "New Outlook" preview UI has limited support for certain Microsoft 365 accounts
- Exchange Online might not be enabled in the license
- Microsoft 365 Business Basic only supports Outlook Web

**Solutions**
✅ **Check if Mailbox is Working**
- Login at [https://outlook.office.com](https://outlook.office.com)  
- If mail loads, the issue is Outlook, not the mailbox

✅ **Switch to Classic Outlook**
- Disable "New Outlook" in the Outlook UI toggle
- Restart and re-add the account

✅ **Check License in Admin Center**
- Confirm user has Microsoft 365 license with **Exchange Online** and **Outlook desktop** services enabled

