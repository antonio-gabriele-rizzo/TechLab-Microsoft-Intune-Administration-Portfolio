# User and Group Preparation

## Introduction

Before devices can be enrolled into Microsoft Intune, the appropriate users and groups must be prepared.

Microsoft Intune relies on Microsoft Entra ID identities to authenticate users, assign applications, deploy policies and control access to organisational resources.

Preparing users and groups correctly helps simplify administration and ensures applications and policies can be deployed consistently across multiple users and devices.

In this chapter, the user accounts and Security Groups created during the Microsoft Entra ID laboratory are reviewed and prepared for Microsoft Intune device enrolment.

---

# Objectives

After completing this chapter, I will be able to:

- Review existing Microsoft Entra ID users.
- Verify the Microsoft Intune subscription.
- Review existing Security Groups.
- Verify group membership.
- Review administrative roles.
- Confirm that the environment is ready for device enrolment.

---

# Prerequisites

Before starting this chapter, I had already:

- Completed Chapter 01 – Creating the Intune Lab Environment.
- Completed Chapter 02 – Intune Administration Center Overview.
- Activated Microsoft Intune Plan 1 Trial.
- Signed in using a Global Administrator account.

---

# Why Users and Groups Are Important

Microsoft Intune uses Microsoft Entra ID to identify users and devices.

Every enrolled device is linked to a user account, allowing administrators to deploy applications, assign compliance policies and manage configuration profiles.

Rather than assigning policies to individual users, organisations typically assign them to Security Groups. This approach simplifies administration, improves consistency and makes future management significantly easier.

Throughout the remainder of this repository, the existing **IT Support Team** Security Group will be reused when assigning applications and policies.

---

# Viewing Existing Users

Navigate to:

```text
Microsoft Intune Admin Center

Users
    └── All users
```

The **Users** page displays every Microsoft Entra ID account available within the tenant.

From this page it is possible to:

- View user accounts.
- Manage licences.
- Reset passwords.
- Review assigned roles.
- Monitor account information.

The users created during the Microsoft Entra ID laboratory will be reused throughout this repository.

![Users Overview](screenshots/entra-users-overview.png)

---

# Verifying the Microsoft Intune Subscription

Before devices can be enrolled, Microsoft Intune must be available within the Microsoft 365 tenant.

Navigate to:

```text
Microsoft 365 Admin Center

Billing
    └── Your products
```

Review the available subscriptions and confirm that **Microsoft Intune Plan 1** is active.

This confirms that the tenant is licensed for Microsoft Intune administration.

![Microsoft Intune Subscription](screenshots/licences.png)

---

# Reviewing Existing Security Groups

Navigate to:

```text
Microsoft Intune Admin Center

Groups
    └── All groups
```

Security Groups allow administrators to assign applications, compliance policies and configuration profiles to multiple users simultaneously.

Using groups instead of assigning resources individually simplifies administration and improves consistency across the organisation.

Locate the **IT Support Team** Security Group created during the Microsoft Entra ID laboratory.

![Groups Overview](screenshots/entra-groups-overview.png)

---

# Reviewing the IT Support Team Security Group

Open the **IT Support Team** Security Group.

The Overview page displays useful information including:

- Group name.
- Group type.
- Membership type.
- Creation date.
- Number of members.

This existing Security Group will be reused throughout the remaining chapters when deploying applications, assigning compliance policies and configuring device settings.

![IT Support Team Security Group](screenshots/intune-security-group.png)

---

# Reviewing Group Membership

Open the **IT Support Team** Security Group.

Navigate to:

```text
Members
```

The **Members** page displays every user currently assigned to the Security Group.

Reviewing group membership confirms that the correct users will receive any applications, compliance policies and configuration profiles assigned to the group.

For this laboratory, the **Helpdesk User** account is a member of the **IT Support Team** Security Group.

![Group Membership](screenshots/intune-group-membership.png)

---

# Reviewing User Group Membership

Navigate to:

```text
Microsoft Intune Admin Center

Users
    └── Helpdesk User
            └── Groups
```

The **Groups** page displays every Microsoft Entra ID group to which the selected user belongs.

Reviewing group membership is an important administrative task because many Microsoft Intune resources are assigned to Security Groups rather than directly to individual users.

The **Helpdesk User** account is correctly assigned to the **IT Support Team** Security Group.

![User Group Membership](screenshots/entra-user-assigned-groups.png)

---

# Reviewing Administrative Roles

Navigate to:

```text
Microsoft Intune Admin Center

Users
    └── Antonio Gabriele Rizzo
            └── Assigned roles
```

Microsoft Entra ID uses administrative roles to control access to Microsoft cloud services, including Microsoft Intune.

Reviewing assigned roles confirms that the administrator account has the permissions required to manage the Microsoft Intune environment.

![Assigned Roles](screenshots/entra-user-directory-roles.png)

---

# Confirming the Environment Is Ready for Device Enrolment

Navigate to:

```text
Microsoft Intune Admin Center

Users
    └── Antonio Gabriele Rizzo
            └── Overview
```

The **Overview** page provides a summary of the administrator account, including:

- Account status
- Assigned licence
- Assigned role
- Group memberships

Reviewing this information confirms that the laboratory environment has been prepared correctly before beginning device enrolment.

![User Ready for Enrolment](screenshots/intune-user-ready-for-enrolment.png)

---

# Key Learnings

- Microsoft Intune uses Microsoft Entra ID users to identify and manage enrolled devices.
- Security Groups simplify the deployment of applications and policies.
- Group membership should be verified before assigning applications or policies.
- Administrative roles determine which management tasks can be performed.
- Reviewing user information before device enrolment helps prevent configuration issues.
- Preparing users and groups is an essential step before enrolling devices.

---

# Skills Demonstrated

- Microsoft Entra ID user administration
- Security Group administration
- Microsoft Intune licence verification
- Administrative role verification
- User preparation for device enrolment
- Technical documentation using GitHub and Markdown

---

# Interview Tip

For junior Microsoft Intune and IT Support roles, it is important to understand that Microsoft Intune relies on Microsoft Entra ID for identity management.

Users, Security Groups and administrative roles are created in Microsoft Entra ID and are then used throughout Microsoft Intune when deploying applications, assigning policies and managing devices.

Understanding this relationship demonstrates a solid understanding of Microsoft's cloud management platform.

---

# Chapter Summary

In this chapter, the existing Microsoft Entra ID users and Security Groups were reviewed and prepared for Microsoft Intune administration.

The Microsoft Intune subscription was verified, Security Group membership was confirmed, administrative roles were reviewed and the administrator account was validated before device enrolment.

The environment is now fully prepared for the next stage of the laboratory.

In the next chapter, a physical Android device will be enrolled into Microsoft Intune using the Microsoft Company Portal application.
