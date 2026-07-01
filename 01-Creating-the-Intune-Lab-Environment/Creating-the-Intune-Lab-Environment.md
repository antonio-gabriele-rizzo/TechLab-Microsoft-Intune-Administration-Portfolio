# Creating the Intune Lab Environment

## Introduction

Microsoft Intune is Microsoft's cloud-based endpoint management solution that enables organisations to manage and secure Windows, macOS, Android and iOS devices from a single administration portal.

In this chapter, a Microsoft Intune laboratory is created by adding a **Microsoft Intune Plan 1 Trial** to the existing **TechLab Microsoft 365** tenant that was configured in the previous Microsoft 365 and Microsoft Entra ID repositories.

This environment will be used throughout the remainder of this portfolio.

---

# Objectives

By completing this chapter, I will learn how to:

- Understand the purpose of Microsoft Intune
- Verify the licensing requirements
- Activate Microsoft Intune Plan 1 Trial
- Use an existing Microsoft 365 tenant
- Verify the subscription
- Access the Microsoft Intune Admin Center

---

# Prerequisites

Before starting this chapter, ensure you have:

- A Microsoft 365 tenant
- Global Administrator permissions
- Microsoft Entra ID configured
- Internet connection
- A supported web browser

---

# What is Microsoft Intune?

Microsoft Intune is Microsoft's cloud-based **Mobile Device Management (MDM)** and **Mobile Application Management (MAM)** solution.

It allows administrators to:

- Enrol devices
- Deploy applications
- Configure security policies
- Create compliance policies
- Perform remote device management
- Monitor managed devices

Microsoft Intune integrates directly with Microsoft Entra ID and Microsoft 365 to provide a modern cloud-based endpoint management solution.

---

# Microsoft Cloud Architecture

The TechLab environment uses the following Microsoft cloud architecture:

```text
Microsoft 365
      │
      ▼
Microsoft Entra ID
      │
      ▼
Microsoft Intune
      │
 ┌────┴────┐
 │         │
Windows  Android
```

Microsoft 365 provides productivity services.

Microsoft Entra ID manages identities and authentication.

Microsoft Intune manages devices.

---

# Licensing Requirements

Microsoft Intune requires an appropriate Microsoft licence before devices can be enrolled and managed.

Microsoft Intune can be licensed either as a standalone product or as part of selected Microsoft 365 subscriptions.

Common licensing options include:

- Microsoft Intune Plan 1
- Microsoft Intune Plan 2 *(advanced add-on features)*
- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5

For this laboratory, **Microsoft Intune Plan 1 Trial** was used.

The trial provides everything required to build a practical Microsoft Intune laboratory and complete every exercise in this repository.

---

# Creating the Microsoft Intune Trial

Open the Microsoft Intune Trial page.

Sign in using your existing Microsoft 365 Global Administrator account.

![Microsoft Intune Trial Sign-up](screenshots/intune-trial-signup-page.png)

---

# Using an Existing Microsoft 365 Tenant

After signing in, Microsoft detects the existing TechLab tenant.

Using the existing tenant allows Microsoft Intune to integrate immediately with Microsoft Entra ID and Microsoft 365.

![Existing Microsoft 365 Tenant](screenshots/intune-existing-tenant-account.png)

---

# Selecting Microsoft Intune Plan 1 Trial

Microsoft displays the available subscription options.

Select:

```text
Microsoft Intune Plan 1 (Trial)
```

This enables the core Microsoft Intune features throughout this laboratory.

![Microsoft Intune Plan 1 Trial](screenshots/intune-trial-selection.png)

---

# Configuring Renewal Settings

Before activating the trial, review the renewal settings.

For this laboratory, the following configuration was used:

| Setting | Value |
|---------|-------|
| Licence Quantity | 1 |
| Subscription Length | 1 Month |
| Billing Frequency | Monthly |

After the trial was activated, recurring billing was configured to cancel automatically when the trial expires.

![Renewal Settings](screenshots/intune-trial-renewal-settings.png)

---

# Activating the Trial

Select **Start Free Trial**.

After a few moments Microsoft confirms that the Microsoft Intune Plan 1 Trial has been successfully added to the tenant.

![Microsoft Intune Trial Activated](screenshots/intune-trial-activated.png)

---

# Verifying the Subscription

Return to the Microsoft 365 Admin Center.

Navigate to:

```text
Billing
    └── Your products
```

Verify that **Microsoft Intune Plan 1 Trial** appears in the list of subscriptions.

![Products Overview](screenshots/intune-products-overview.png)

---

# Opening Microsoft Intune Admin Center

Microsoft Intune can be accessed using either of the following methods.

### Method 1

```text
https://admin.microsoft.com
```

Navigate to:

```text
Show all
    └── Admin centers
            └── Microsoft Intune
```

### Method 2

Open the Microsoft Intune Admin Center directly:

```text
https://intune.microsoft.com
```

Once provisioning has completed, the Microsoft Intune Admin Center opens successfully.

> **Note**
>
> During this laboratory, Microsoft Intune required a few minutes to complete the provisioning process before appearing in the Admin Centers list.

![Microsoft Intune Admin Center](screenshots/intune-admin-center-home.png)

---

# Key Learnings

- Microsoft Intune provides cloud-based endpoint management for Windows, macOS, Android and iOS devices.
- Microsoft Intune integrates directly with Microsoft Entra ID and Microsoft 365.
- Microsoft Intune requires an appropriate licence before devices can be enrolled and managed.
- Microsoft Intune Plan 1 provides the core endpoint management features required for this laboratory.
- A Microsoft Intune trial can be added to an existing Microsoft 365 tenant.
- The Microsoft Intune Admin Center becomes available once the trial has been successfully provisioned.
- The Microsoft Intune Admin Center is the primary portal used to manage organisational devices.

---

# Skills Demonstrated

- Microsoft Intune fundamentals
- Microsoft 365 administration
- Microsoft Entra ID integration
- Licensing administration
- Microsoft cloud administration
- Technical documentation using GitHub and Markdown
---

# Chapter Summary

In this chapter a Microsoft Intune laboratory environment was successfully created using the existing **TechLab** Microsoft 365 tenant.

The following tasks were completed:

- Activated Microsoft Intune Plan 1 Trial
- Verified the subscription
- Accessed the Microsoft Intune Admin Center
- Prepared the environment for the remaining chapters

The next chapter introduces the Microsoft Intune Admin Center and explores the main administrative areas used to manage users, devices, applications and security.
