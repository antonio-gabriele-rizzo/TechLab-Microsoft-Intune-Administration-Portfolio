# 07 – Configuration Profiles

## Introduction

Configuration Profiles are one of the core management features within Microsoft Intune and allow administrators to configure device settings remotely without requiring manual configuration by end users.

Unlike Compliance Policies, which determine whether a device meets an organisation's security requirements, Configuration Profiles actively configure operating system features and management settings on enrolled devices. These profiles enable organisations to standardise device configurations, improve security, simplify administration and ensure a consistent user experience across managed endpoints.

Microsoft Intune supports a wide range of Configuration Profile types, including device restrictions, Wi-Fi profiles, VPN configurations, certificates, email settings, endpoint protection and custom policies. The available settings vary depending on the operating system and enrolment method being used.

In this chapter, I created an Android Enterprise Device Restrictions Configuration Profile for a Personally-Owned Work Profile device. Rather than applying unnecessary restrictions that could interfere with later laboratory exercises, I intentionally retained the default configuration while demonstrating the complete deployment workflow, including profile creation, assignment and verification.

---

# Objectives

After completing this chapter, I will be able to:

- Understand the purpose of Microsoft Intune Configuration Profiles.
- Differentiate between Configuration Profiles and Compliance Policies.
- Create an Android Enterprise Configuration Profile.
- Select the appropriate profile platform and template.
- Configure a Device Restrictions profile.
- Assign Configuration Profiles using Microsoft Entra Security Groups.
- Verify successful profile deployment within Microsoft Intune.
- Understand when Device Restrictions should and should not be configured.

---

# Prerequisites

Before starting this chapter, I had already completed:

- Chapter 01 – Creating the Intune Lab Environment
- Chapter 02 – Intune Administration Center Overview
- Chapter 03 – User and Group Preparation
- Chapter 04 – Android Device Enrolment
- Chapter 05 – Deploying Android Applications with Managed Google Play
- Chapter 06 – Compliance Policies

In addition, the following components were already configured:

- Microsoft Intune tenant
- Android Enterprise connector
- Personally-Owned Android Enterprise device
- Microsoft Company Portal
- Android Test Users Security Group
- Successful Android Enterprise enrolment
- Managed Google Play integration

---

# Understanding Configuration Profiles

Configuration Profiles allow administrators to configure device settings remotely through Microsoft Intune.

Whereas Compliance Policies evaluate whether a device satisfies predefined security requirements, Configuration Profiles actively apply configuration settings to managed devices. These settings are downloaded during the device's next check-in and are enforced by the operating system where supported.

Common Configuration Profile scenarios include:

- Device restrictions
- Password configuration
- Wi-Fi deployment
- VPN configuration
- Email configuration
- Certificates
- Kiosk mode
- Endpoint protection settings

Configuration Profiles are frequently used alongside Compliance Policies to build a complete endpoint management solution. A Configuration Profile configures the device, while a Compliance Policy evaluates whether the device meets the organisation's security requirements.

For this laboratory, I selected the **Device Restrictions** template for an Android Enterprise Personally-Owned Work Profile device. This template provides administrators with numerous options for controlling work profile behaviour, although many settings are only applicable to Fully Managed or Corporate-Owned Android Enterprise devices.

---

To begin creating a Configuration Profile, navigate to:

```text
Microsoft Intune Admin Center

Devices
    └── Configuration
```

Initially, no Configuration Profiles existed within my Intune tenant.

![Configuration Profiles Overview](screenshots/configuration-profiles-overview.png)

---

# Creating an Android Enterprise Configuration Profile

From the Configuration Profiles page, I selected **Create** to launch the Configuration Profile wizard.

Microsoft Intune first required me to choose the platform that the profile would target.

For this laboratory, I selected:

- **Platform:** Android Enterprise

Selecting the correct platform is important because Microsoft Intune only displays templates and settings that are supported by the selected operating system and enrolment type.

Since my enrolled test device uses Android Enterprise Personally-Owned Work Profile, Android Enterprise was the appropriate platform for this deployment.

![Platform Selection](screenshots/create-configuration-profile-platform.png)

---

The next step required selecting the profile template.

Microsoft Intune provides several profile types for Android Enterprise devices depending on the enrolment method being used.

For this laboratory, I selected:

- **Profile type:** Personally-Owned Work Profile
- **Template:** Device Restrictions

The Device Restrictions template allows administrators to configure operating system behaviour within the managed work profile without affecting the user's personal profile. This separation is one of the key security advantages of Android Enterprise Personally-Owned Work Profile deployments, allowing organisations to manage corporate data while respecting user privacy.

![Template Selection](screenshots/configuration-profile-template-selection.png)

---

# Configuring the Profile Basics

After selecting the template, Microsoft Intune prompted me to provide the profile information.

I configured the following values:

| Setting | Value |
|---------|-------|
| Name | Android Work Profile Device Restrictions |
| Description | Configuration profile for Android Enterprise personally owned work profile devices in the Intune lab environment. |

Providing meaningful names and descriptions makes Configuration Profiles easier to identify, maintain and troubleshoot, particularly within production environments where organisations may manage hundreds of policies across multiple operating systems.

Using consistent naming conventions also helps administrators quickly distinguish Configuration Profiles from Compliance Policies, Endpoint Security policies and application deployments.

![Profile Basics](screenshots/configuration-profile-basics.png)

---

# Understanding Device Restrictions

# Understanding Device Restrictions

Device Restrictions are one of the most commonly used Configuration Profile templates within Microsoft Intune. They allow administrators to control how managed devices behave by enabling, disabling or enforcing specific operating system features.

The available settings vary depending on both the operating system and the enrolment method. This is particularly important when managing Android Enterprise devices because Microsoft Intune supports several different Android deployment models, each providing a different level of administrative control.

The three most common Android Enterprise enrolment methods are:

| Enrolment Type | Typical Device Ownership | Level of Administrative Control |
|---------------|--------------------------|---------------------------------|
| Personally-Owned Work Profile | Bring Your Own Device (BYOD) | Work profile only |
| Corporate-Owned Work Profile | Company-owned device | Work profile with additional management capabilities |
| Fully Managed | Company-owned device | Full device management |

For **Personally-Owned Work Profile** devices, Microsoft Intune only manages the corporate work profile. The user's personal applications, photographs, messages and personal settings remain outside the organisation's control.

This separation provides an important balance between organisational security and user privacy. Employees can use their own devices for work while organisations retain full control over corporate applications and data without accessing personal information.

Because of this design, many Device Restriction settings that are available for Fully Managed Android Enterprise devices are either unavailable or not applicable to Personally-Owned Work Profile devices.

During this laboratory, I carefully reviewed the available Device Restriction categories before deciding whether any additional configuration was appropriate.

Although Microsoft Intune provides a large number of configuration options, many of them were intended for deployment scenarios that differed from my laboratory environment. Examples included restrictions relating to device-wide hardware features, operating system functionality and corporate-owned device management.

Since my objective was to demonstrate Configuration Profile deployment using an Android Enterprise Personally-Owned Work Profile device, enabling unnecessary restrictions would not have reflected a realistic deployment scenario. It could also have introduced unnecessary complications for later chapters within this project.

For these reasons, I intentionally retained the default Device Restriction settings.

This decision reflects an important principle of endpoint administration: administrators should configure only those settings that satisfy a genuine business, operational or security requirement. Applying unnecessary restrictions increases administrative complexity, makes troubleshooting more difficult and may negatively affect the end-user experience without providing any meaningful benefit.

In production environments, Device Restrictions are typically introduced gradually as organisational requirements evolve, rather than enabling every available option simply because it exists.

---

# Assigning the Configuration Profile

After reviewing the available settings, I continued to the assignment stage.

Rather than assigning the Configuration Profile directly to an individual user, I targeted the **Android Test Users** Microsoft Entra Security Group that I created earlier in this project.

Using Security Groups provides a scalable administration model because future users automatically receive assigned policies simply by becoming members of the appropriate group. This approach also reduces ongoing administrative effort and aligns with Microsoft Intune best practices.

For this laboratory, I configured the following assignment:

| Assignment | Value |
|------------|-------|
| Included groups | Android Test Users |

No exclusion groups were configured because the laboratory environment contains only a single test user.

![Configuration Profile Assignments](screenshots/configuration-profile-assignments.png)

---

# Creating the Configuration Profile

After confirming the assignment, I selected **Create** to deploy the Configuration Profile.

Microsoft Intune processed the request and created the policy within the tenant.

Returning to the Configuration Profiles page confirmed that the new profile had been successfully created.

The Configuration Profiles list provides administrators with a central overview of deployed policies together with useful management information, including:

- Policy name
- Platform
- Profile type
- Last modified date
- Scope tags

From this page, administrators can also edit, duplicate, delete and monitor existing Configuration Profiles.

Seeing the newly created profile listed confirmed that Microsoft Intune had successfully stored the configuration.

![Configuration Profiles List](screenshots/configuration-profiles-list.png)

---

# Verifying the Configuration Profile

To verify the deployment, I opened the newly created Configuration Profile.

The overview page displayed important information relating to the policy, including:

- Device and user check-in status
- Policy properties
- Platform
- Profile type
- Assigned scope tags

Reviewing the profile immediately after creation is a good administrative practice because it confirms that the policy has been created correctly before relying on it within a production environment.

This verification also provides an opportunity to confirm that the correct template, platform and descriptive information have been saved.

![Configuration Profile Overview](screenshots/configuration-profile-overview.png)

---

# Monitoring Deployment

Unlike the Compliance Policy created in the previous chapter, this Configuration Profile intentionally retained the default Device Restrictions.

As a result, Microsoft Intune had no custom configuration settings to deploy to the enrolled Android Enterprise device.

Although the profile itself was successfully created and assigned, the monitoring pages did not generate deployment statistics during the laboratory session because there were no configuration changes requiring evaluation by the managed work profile.

This behaviour differs from Compliance Policies, where Microsoft Intune actively evaluates device compliance against defined security requirements and produces compliance reports.

Understanding this distinction is important because successful policy creation does not necessarily result in immediate deployment statistics. The information displayed within the monitoring pages depends on both the profile content and the device's evaluation process during subsequent synchronisation.

---

# Key Learnings

- Configuration Profiles actively configure managed devices, whereas Compliance Policies evaluate whether devices meet organisational security requirements.
- Microsoft Intune provides different Configuration Profile templates depending on the operating system and enrolment method.
- Android Enterprise Personally-Owned Work Profile devices support a subset of Device Restriction settings when compared with Fully Managed or Corporate-Owned devices.
- Microsoft Entra Security Groups provide an efficient and scalable method for assigning Configuration Profiles.
- Not every available policy setting should be configured. Administrators should apply only those settings that support genuine operational or security requirements.
- Verifying newly created policies within Microsoft Intune helps confirm successful deployment before relying on them in production environments.

---

# Skills Demonstrated

Throughout this chapter, I demonstrated the following practical Microsoft Intune administration skills:

- Microsoft Intune Configuration Profile administration.
- Android Enterprise device management.
- Device Restrictions policy deployment.
- Microsoft Entra Security Group assignments.
- Mobile Device Management (MDM).
- Policy verification and administration.
- Android Enterprise Personally-Owned Work Profile management.
- Technical documentation using GitHub and Markdown.

---

# Interview Tip

A common interview question for IT Support, Service Desk and Junior Endpoint Administrator roles is:

> **"What is the difference between a Configuration Profile and a Compliance Policy in Microsoft Intune?"**

A good answer is:

- A **Configuration Profile** applies settings **to** a managed device. Examples include Wi-Fi profiles, VPN settings, certificates, device restrictions and password configuration.
- A **Compliance Policy** checks whether a managed device **meets** the organisation's security requirements. Examples include encryption status, operating system version, password requirements and root detection.
- A device can successfully receive Configuration Profiles while still being reported as **Noncompliant** if it fails one or more compliance checks.
- Compliance results are commonly used together with Microsoft Entra Conditional Access policies to control access to Microsoft 365 and other corporate resources.

Understanding the distinction between these two policy types demonstrates a solid understanding of modern endpoint management and is frequently assessed during Microsoft Intune interviews.

---

# Chapter Summary

In this chapter, I created my first Android Enterprise Configuration Profile using Microsoft Intune.

I selected the appropriate Android Enterprise platform and Device Restrictions template, configured the profile information and assigned the policy to the **Android Test Users** Microsoft Entra Security Group.

Rather than enabling unnecessary restrictions, I deliberately retained the default Device Restriction settings because the enrolled device uses an Android Enterprise Personally-Owned Work Profile. This approach reflects a realistic administrative decision, ensuring that only appropriate settings are deployed while preserving the device for future laboratory exercises.

Finally, I verified that the Configuration Profile had been successfully created within Microsoft Intune and confirmed that the deployment was ready for use.

This exercise demonstrated the complete lifecycle of creating and deploying a Microsoft Intune Configuration Profile while reinforcing the importance of selecting the correct policy type, assigning it through Microsoft Entra Security Groups and understanding the capabilities and limitations of Android Enterprise Personally-Owned Work Profile devices.
