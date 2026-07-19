# Creating the Intune Lab Environment

## Introduction

Microsoft Intune is Microsoft's cloud-based endpoint management solution that enables organisations to manage, secure and monitor devices from a centralised administration platform. It integrates with Microsoft Entra ID and Microsoft 365, allowing administrators to apply security policies, deploy applications, manage device compliance and protect organisational data across Windows, macOS, Android and iOS devices.

In this chapter, I prepared the Microsoft Intune laboratory that will be used throughout this repository. Rather than creating a separate Microsoft 365 tenant, I extended my existing TechLab365 Microsoft 365 environment by activating a Microsoft Intune Plan 1 Trial licence. This approach allowed me to continue building on the Microsoft Entra ID configuration that had already been documented in my previous repositories while providing a realistic environment for managing enterprise devices.

During the preparation of the laboratory, I also encountered an unexpected prerequisite when configuring Android Enterprise. This required me to configure Managed Google Play before Android devices could be enrolled successfully. Documenting this experience ensures that anyone reproducing the laboratory understands the complete preparation process before device enrolment begins.

---

# Learning Objectives

By completing this chapter I learned how to:

- Understand the role of Microsoft Intune within Microsoft 365
- Identify the licensing requirements for Microsoft Intune
- Activate Microsoft Intune Plan 1 Trial
- Verify that the subscription had been provisioned successfully
- Access the Microsoft Intune Admin Center
- Configure Managed Google Play for Android Enterprise
- Verify that the environment was ready for device enrolment

---

# Prerequisites

Before beginning this laboratory, I ensured that the following requirements had already been completed:

- Microsoft 365 Business tenant
- Microsoft Entra ID configured
- Global Administrator permissions
- Internet connectivity
- Modern web browser
- Microsoft Intune Plan 1 Trial availability

As this laboratory builds upon the work completed in my previous Microsoft 365 and Microsoft Entra ID repositories, the tenant was already configured with the necessary administrative accounts and licensing.

---

# Understanding Microsoft Intune

Microsoft Intune is Microsoft's cloud-based endpoint management platform that provides Mobile Device Management (MDM) and Mobile Application Management (MAM) capabilities.

Using Microsoft Intune, organisations can:

- Enrol corporate and personal devices
- Deploy applications remotely
- Configure device settings
- Apply compliance policies
- Protect organisational data
- Manage security baselines
- Monitor managed devices
- Perform remote administrative actions

Unlike traditional on-premises device management solutions, Microsoft Intune operates entirely from Microsoft's cloud infrastructure, allowing devices to be managed securely regardless of their physical location.

---

# Microsoft Cloud Integration

Microsoft Intune is closely integrated with other Microsoft cloud services.

```text
+------------------------------------------------------+
|                  Microsoft 365                       |
+------------------------------------------------------+
                         │
                         ▼
+------------------------------------------------------+
|               Microsoft Entra ID                     |
| Authentication • Identity • Conditional Access       |
+------------------------------------------------------+
                         │
                         ▼
+------------------------------------------------------+
|                 Microsoft Intune                     |
| MDM • MAM • Compliance • Configuration               |
+------------------------------------------------------+
                         │
        ┌────────────────┼────────────────┐
        ▼                ▼                ▼
     Windows         Android           iOS/iPadOS
```

Microsoft 365 provides productivity services.

Microsoft Entra ID provides identity and authentication services.

Microsoft Intune provides endpoint management by combining identity, licensing and security policies into a single cloud-based management platform.

---

# Licensing Requirements

Microsoft Intune requires an appropriate licence before endpoint management features become available.

Several Microsoft subscriptions include Microsoft Intune, including:

- Microsoft 365 Business Premium
- Microsoft 365 E3
- Microsoft 365 E5
- Enterprise Mobility + Security (EMS)
- Microsoft Intune Plan 1

For this laboratory, I activated the **Microsoft Intune Plan 1 Trial**, as it provides all of the functionality required to complete every exercise within this repository without requiring an Enterprise subscription.

Using the trial licence also allowed me to evaluate the platform while maintaining a realistic enterprise deployment scenario.

---

# Activating Microsoft Intune Plan 1 Trial

To prepare the laboratory, I activated Microsoft Intune Plan 1 Trial from within the Microsoft 365 Admin Centre.

Rather than creating a separate Microsoft tenant, I chose to extend the existing TechLab365 tenant that had already been configured during the Microsoft 365 administration project.

Using the existing tenant offered several advantages:

- Existing users were already configured.
- Microsoft Entra ID had already been configured.
- Administrative permissions were already available.
- Future laboratories could continue using the same environment.
- Device management could integrate directly with the existing cloud identity infrastructure.

Once the trial had been activated, Microsoft automatically provisioned the Microsoft Intune service within the tenant.

Provisioning completed successfully without requiring any manual intervention.

---

# Verifying the Subscription

After activation, I verified that Microsoft Intune had been added successfully by opening:

**Microsoft 365 Admin Centre**

**Billing → Your products**

The Microsoft Intune Plan 1 Trial licence was listed successfully, confirming that the service had been provisioned correctly.

Verifying the subscription before continuing ensured that the remaining configuration tasks could be completed without licensing issues.

---

# Accessing the Microsoft Intune Admin Center

With the subscription successfully activated, I accessed the Microsoft Intune Admin Center.

The administration portal loaded successfully and displayed the available management workloads, including:

- Devices
- Apps
- Endpoint Security
- Reports
- Users
- Groups
- Tenant Administration

This confirmed that the Microsoft Intune service had been provisioned correctly and that the tenant was ready for further configuration.

---

# Configuring Managed Google Play

Although Microsoft Intune had been configured successfully, I discovered an additional prerequisite before Android Enterprise devices could be enrolled.

Microsoft Intune requires a connection to **Managed Google Play** before Android Enterprise management becomes available.

Initially, I attempted to configure Managed Google Play by using the tenant's default **onmicrosoft.com** account. During testing, I discovered that this approach was unsuitable because the Android Enterprise registration process required a Google account capable of completing the Managed Google Play association.

To resolve the issue, I repeated the registration by using my **TechLab365 organisational email address**.

Using the TechLab365 account allowed the Managed Google Play connection to be created successfully.

Once the registration had completed, Microsoft Intune established a trusted connection with Google's Android Enterprise services, allowing Android Enterprise enrolment to become available within the tenant.

Although this step had not originally been included in my laboratory planning, documenting it became important because Android device enrolment cannot proceed without it.

Including this prerequisite within the environment preparation ensures that future deployments can be reproduced successfully without encountering the same issue.

---

# Lessons Learned

Preparing the laboratory demonstrated that successful endpoint management depends upon completing several prerequisite configuration tasks before device enrolment begins.

During this chapter I learned that:

- Microsoft Intune integrates directly with Microsoft Entra ID.
- Appropriate licensing must be available before device management features become accessible.
- Microsoft Intune services require time to provision after activation.
- Managed Google Play is mandatory for Android Enterprise management.
- Real-world deployments often reveal additional prerequisites that may not be obvious during the planning stage.
- Documenting unexpected issues improves both troubleshooting and future deployments.

---

# Skills Demonstrated

During this chapter I demonstrated the following technical skills:

- Microsoft 365 administration
- Microsoft Intune deployment
- Microsoft Entra ID integration
- Cloud service provisioning
- Licence management
- Managed Google Play configuration
- Android Enterprise preparation
- Technical troubleshooting
- Technical documentation

---

# Chapter Summary

In this chapter, I successfully prepared the Microsoft Intune laboratory environment that will be used throughout the remainder of this repository.

The following tasks were completed successfully:

- Activated Microsoft Intune Plan 1 Trial
- Verified the Microsoft Intune subscription
- Confirmed successful service provisioning
- Accessed the Microsoft Intune Admin Center
- Configured Managed Google Play
- Verified Android Enterprise readiness
- Prepared the tenant for device enrolment

The laboratory environment was now fully prepared, providing the foundation for the remaining chapters, where users, groups, devices, compliance policies, configuration profiles, applications and security features will be configured and managed using Microsoft Intune.
