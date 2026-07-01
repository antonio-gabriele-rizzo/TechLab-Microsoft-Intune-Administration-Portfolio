# 01 – Creating the Intune Lab Environment

## Introduction

Microsoft Intune is Microsoft's cloud-based Endpoint Management platform that enables organisations to securely manage, monitor and protect desktops, laptops, tablets and mobile devices from a single administration portal.

As organisations continue adopting cloud-first strategies and remote working, managing devices securely has become a fundamental responsibility for IT Support Engineers, Endpoint Administrators and Microsoft 365 Administrators.

Microsoft Intune allows administrators to:

- Enrol corporate and personal devices
- Deploy applications remotely
- Configure security settings
- Enforce compliance policies
- Protect corporate data
- Monitor managed devices
- Perform remote administrative actions

This chapter documents the complete process of creating a Microsoft Intune laboratory using an existing Microsoft 365 tenant.

Rather than creating a completely new Microsoft environment, the existing **TechLab** Microsoft 365 tenant created during the previous repositories is extended by adding Microsoft Intune Plan 1 Trial.

This approach closely mirrors how Microsoft Intune is introduced within real organisations.

---

# Objectives

After completing this chapter, you should be able to:

- Explain the purpose of Microsoft Intune
- Understand the relationship between Microsoft 365, Microsoft Entra ID and Microsoft Intune
- Verify Microsoft Intune licensing requirements
- Activate Microsoft Intune Plan 1 Trial
- Configure safe renewal settings
- Verify the successful activation of the subscription
- Access the Microsoft Intune Admin Center
- Confirm that the environment is ready for device management

---

# Prerequisites

Before beginning this chapter, ensure you have:

- A Microsoft 365 tenant
- Global Administrator permissions
- Access to Microsoft 365 Admin Center
- Microsoft Entra ID configured
- A supported web browser
- Internet connectivity

The laboratory documented throughout this repository uses the TechLab Microsoft 365 tenant previously created within the Microsoft 365 and Microsoft Entra ID Administration repositories.

---

# What is Microsoft Intune?

Microsoft Intune is Microsoft's cloud-based Unified Endpoint Management (UEM) solution.

It enables administrators to manage users, devices, applications and security policies from a single cloud platform.

Unlike traditional on-premises management solutions, Microsoft Intune operates entirely from Microsoft's cloud infrastructure and integrates tightly with Microsoft Entra ID.

Administrators can use Microsoft Intune to:

- Enrol Windows devices
- Enrol Android devices
- Enrol iPhones and iPads
- Enrol macOS devices
- Deploy applications
- Configure security policies
- Monitor device compliance
- Perform remote administrative actions

Microsoft Intune forms a core component of Microsoft's modern endpoint management strategy.

---

# Microsoft Cloud Architecture

Understanding how Microsoft Intune integrates with other Microsoft cloud services is essential.

Within this portfolio, the following architecture is used:

```text
Microsoft 365 Tenant
        │
        ▼
Microsoft Entra ID
        │
        ▼
Microsoft Intune
        │
 ┌──────┼─────────────┐
 │      │             │
Windows Android     macOS
 │
Applications
Policies
Compliance
Endpoint Security
```

Each platform has a specific responsibility.

**Microsoft 365**

Provides productivity services including:

- Exchange Online
- Teams
- SharePoint
- OneDrive

**Microsoft Entra ID**

Provides:

- Identity Management
- Authentication
- Authorisation
- Administrative Roles

**Microsoft Intune**

Provides:

- Device Management
- Application Management
- Compliance Management
- Endpoint Security

Throughout this repository, these three Microsoft services work together to provide a complete cloud administration laboratory.

---

# Licensing Requirements

Microsoft Intune requires an appropriate subscription before devices can be managed.

Several licensing options are available, including:

- Microsoft Intune Plan 1
- Microsoft Intune Plan 2
- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5

For this laboratory, Microsoft Intune Plan 1 Trial is used.

The trial provides sufficient functionality to explore the Microsoft Intune Admin Center, enrol devices, configure compliance policies and perform endpoint administration.

---

# Creating the Microsoft Intune Trial

Microsoft Intune can be activated directly from Microsoft's licensing portal.

For this laboratory, an existing Microsoft 365 tenant was reused rather than creating a new organisation.

This reflects the most common deployment scenario within enterprise environments.

Navigate to Microsoft's Microsoft Intune Trial page.

![Microsoft Intune Trial Sign-up](screenshots/intune-trial-signup-page.png)

---

# Using an Existing Microsoft 365 Tenant

Sign in using the existing Global Administrator account created during the Microsoft 365 portfolio.

The TechLab tenant is automatically recognised by Microsoft.

![Existing Microsoft 365 Tenant](screenshots/intune-existing-tenant-account.png)

Using the existing tenant allows Microsoft Intune to integrate immediately with Microsoft Entra ID and Microsoft 365 services already configured within the laboratory.

---

# Selecting Microsoft Intune Plan 1 Trial

After authentication, Microsoft displays the available subscription options.

By default, the commercial subscription may be selected.

Open the subscription list and select:

```text
Microsoft Intune Plan 1 (Trial)
```

Verify that:

- Trial subscription selected
- £0.00 due today
- 25 trial licences included

![Microsoft Intune Trial Selected](screenshots/intune-trial-selection.png)

---

# Configuring Renewal Settings

Before activating the trial, review the renewal settings.

For this laboratory the following configuration was used:

| Setting | Value |
|---------|-------|
| Licence Quantity | 1 |
| Subscription Length | 1 Month |
| Billing Frequency | Monthly |

These settings minimise the financial commitment should automatic renewal occur.

After the trial was activated, recurring billing was configured to cancel automatically when the trial expires.

![Renewal Settings](screenshots/intune-trial-renewal-settings.png)

---

# Activating the Microsoft Intune Trial

After reviewing the renewal settings, select **Start Free Trial** to begin the Microsoft Intune Plan 1 Trial.

Microsoft provisions the subscription and adds it to the existing Microsoft 365 tenant.

Once the activation has completed successfully, Microsoft displays a confirmation page indicating that the Microsoft Intune Plan 1 Trial has been added to the organisation.

This confirms that the subscription has been successfully provisioned.

![Microsoft Intune Trial Activated](screenshots/intune-trial-activated.png)

---

# Verifying the Subscription

After activation, return to the Microsoft 365 Admin Center.

Navigate to:

```text
Billing
    └── Your Products
```

Verify that **Microsoft Intune Plan 1** now appears alongside the existing Microsoft 365 subscriptions.

Within this laboratory, the following subscriptions were available:

- Microsoft 365 Business Basic
- Microsoft Entra ID Free
- Microsoft Intune Plan 1 Trial

This confirms that Microsoft Intune has been successfully added to the existing TechLab tenant.

![Products Overview](screenshots/intune-products-overview.png)

---

# Opening Microsoft Intune Admin Center

Once Microsoft Intune has been successfully added to the tenant, the Microsoft Intune Admin Center becomes available.

From the Microsoft 365 Admin Center:

```text
Show all

Admin Centers

Microsoft Intune
```

Alternatively, browse directly to:

```text
https://intune.microsoft.com
```

Sign in using your Global Administrator account.

Depending on Microsoft's provisioning process, the Microsoft Intune Admin Center may take several minutes to appear after the trial has been activated.

Refresh the Microsoft 365 Admin Center if necessary.

![Microsoft Intune Admin Center Home](screenshots/intune-admin-center-home.png)

The successful appearance of the Microsoft Intune Admin Center confirms that the tenant is fully provisioned and ready for endpoint administration.

---

# Accessing Microsoft Intune Admin Center

After the subscription has been provisioned, Microsoft Intune becomes available within the Microsoft 365 Admin Center.

Navigate to:

```text
Show All

Admin Centers

Microsoft Intune
```

Alternatively, Microsoft Intune can be accessed directly by visiting:

```text
https://intune.microsoft.com
```

and signing in using an administrative account.

> **Note**
>
> Immediately after activating the trial, Microsoft Intune may not appear in the list of available Admin Centers.
>
> During the creation of this laboratory, Microsoft required several minutes to complete the provisioning process before the Microsoft Intune Admin Center became available.
>
> Refreshing the Microsoft 365 Admin Center after a short period displayed the Microsoft Intune entry automatically.

---

# Microsoft Intune Admin Center

Once provisioning has completed successfully, Microsoft Intune becomes available as a dedicated administration portal.

The Microsoft Intune Admin Center serves as the central location for managing:

- Managed devices
- Applications
- Compliance policies
- Configuration profiles
- Endpoint Security
- Reports
- Tenant Administration

The Overview page provides administrators with a high-level summary of the environment and quick access to the most commonly used management areas.

This portal will be used extensively throughout the remaining chapters of this repository.

![Microsoft Intune Admin Center Home](screenshots/intune-admin-center-home.png)

From this point onwards, all endpoint administration tasks will be performed from within the Microsoft Intune Admin Center.

---

# What Was Configured

During this chapter, the following tasks were completed successfully:

- Microsoft Intune Plan 1 Trial activated
- Existing Microsoft 365 tenant reused
- Existing Microsoft Entra ID tenant reused
- Renewal settings reviewed
- Automatic renewal configured to cancel on expiration
- Subscription verified
- Microsoft Intune Admin Center successfully provisioned
- Laboratory environment prepared for endpoint management

---

# Best Practices

When creating a Microsoft Intune laboratory:

- Use an existing Microsoft 365 tenant whenever possible.
- Verify licensing before attempting device enrolment.
- Review renewal settings before activating any trial subscription.
- Disable automatic renewal if the laboratory is intended only for learning.
- Verify that the Microsoft Intune Admin Center has been provisioned before beginning administration tasks.
- Document each administrative action for future reference.

---

# Real-World Scenario

A medium-sized organisation decides to introduce Microsoft Intune to centrally manage employee laptops and mobile devices.

Instead of creating a new Microsoft tenant, the IT department extends its existing Microsoft 365 environment by adding the Microsoft Intune Plan.

Once activated, administrators configure security policies, enrol employee devices, deploy Microsoft applications and monitor compliance through the Microsoft Intune Admin Center.

This laboratory follows the same deployment approach commonly used in enterprise environments.

---

# Key Takeaways

- Microsoft Intune is Microsoft's cloud-based endpoint management platform.
- Microsoft Intune integrates directly with Microsoft Entra ID and Microsoft 365.
- Microsoft Intune Plan 1 Trial provides sufficient functionality for building a practical learning environment.
- Existing Microsoft 365 tenants can be extended with Microsoft Intune rather than creating a new organisation.
- The Microsoft Intune Admin Center is the primary portal used to manage devices, applications and endpoint security.
- Provisioning may take several minutes before the Microsoft Intune Admin Center becomes available.

---

# Skills Developed

By completing this chapter, the following skills were developed:

- Microsoft Intune Fundamentals
- Tenant Provisioning
- Microsoft Cloud Administration
- Licensing Administration
- Microsoft 365 Integration
- Microsoft Entra ID Integration
- Endpoint Management Fundamentals
- Technical Documentation
- GitHub Portfolio Development

---

# Chapter Summary

In this chapter, a complete Microsoft Intune laboratory environment was created using an existing Microsoft 365 tenant.

The following tasks were successfully completed:

- Reviewed Microsoft Intune licensing requirements
- Activated Microsoft Intune Plan 1 Trial
- Configured safe renewal settings
- Verified the successful activation of the subscription
- Confirmed the subscription within Microsoft 365 Admin Center
- Accessed the Microsoft Intune Admin Center
- Prepared the TechLab environment for endpoint management

The laboratory is now fully configured and ready for the remaining chapters of this repository.

The next chapter introduces the Microsoft Intune Admin Center and provides an overview of its navigation, administrative capabilities and core management areas.
