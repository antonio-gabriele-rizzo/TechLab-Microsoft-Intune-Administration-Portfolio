# 07 – Configuration Profiles

## Overview

Configuration Profiles are one of the core management features available in Microsoft Intune. They allow administrators to configure device settings remotely without requiring manual configuration by the end user. Configuration Profiles can be used to enforce organisational standards, improve security, and ensure a consistent user experience across managed devices.

Unlike Compliance Policies, which evaluate whether a device meets defined security requirements, Configuration Profiles actively apply settings to managed devices. These settings can include password requirements, device restrictions, Wi-Fi profiles, VPN configurations, certificates, email settings, and many other operating system features.

For this lab environment, I created an Android Enterprise Device Restrictions profile targeting Personally-Owned Work Profile (BYOD) devices. Since the objective of the lab was to demonstrate the deployment process rather than enforce restrictive controls, I intentionally retained the default configuration settings. This ensured the enrolled Android device remained fully usable for subsequent chapters while still demonstrating the complete profile creation and assignment workflow.

---

# Objectives

During this chapter I will:

- Create a new Android Enterprise Configuration Profile.
- Select the appropriate platform and profile template.
- Configure the profile details.
- Assign the profile to the Android Test Users group.
- Deploy the configuration profile through Microsoft Intune.
- Verify that the profile has been successfully created.

---

# Creating an Android Enterprise Configuration Profile

From the Microsoft Intune admin centre, I navigated to:

**Devices → Configuration**

This section provides a central location for managing device configuration profiles across all supported operating systems.

At this stage of the project, no Android configuration profiles had been created. This provided a clean starting point for deploying a new Device Restrictions profile.

![Configuration Profiles Overview](images/configuration-profiles-overview.png)

---

Selecting **Create** launched the Configuration Profile wizard.

The first step required selecting the target platform. Since my lab device is enrolled using Android Enterprise Personally-Owned Work Profile, I selected:

- **Platform:** Android Enterprise

Choosing the correct platform ensures that only policies supported by the enrolled device type are available during profile creation.

![Platform Selection](images/create-configuration-profile-platform.png)

---

The next step required selecting the profile type.

Microsoft Intune provides multiple profile templates depending on the chosen platform. For Android Enterprise Personally-Owned Work Profile devices, I selected:

- **Profile type:** Device restrictions

Device Restrictions profiles allow administrators to configure operating system features and behavioural settings that are supported by Android Enterprise.

![Template Selection](images/configuration-profile-template-selection.png)

---

# Configuring the Profile

After selecting the template, I configured the basic profile information.

I entered the following values:

| Setting | Value |
|----------|-------|
| Name | Android Work Profile Device Restrictions |
| Description | Configuration profile for Android Enterprise personally owned work profile devices in the Intune lab environment. |

Providing clear names and descriptions makes policy administration significantly easier, particularly within larger environments where many similar configuration profiles may exist.

![Profile Basics](images/configuration-profile-basics.png)

---

# Assigning the Configuration Profile

Once the basic profile information had been configured, I proceeded to the assignment stage.

To ensure the profile was deployed only to the intended test environment, I assigned it to the **Android Test Users** security group that I created earlier in the project.

Using group-based assignments is considered best practice because it provides a scalable and manageable deployment model. Rather than targeting individual users or devices, administrators can simply manage group membership, allowing policies to be applied automatically as users join or leave the group.

For this lab, the assignment configuration was:

| Assignment | Value |
|------------|-------|
| Included groups | Android Test Users |

No exclusion groups were configured because this isolated lab environment only contains test resources.

![Profile Assignments](images/configuration-profile-assignments.png)

---

After reviewing the assignment, I selected **Create** to deploy the configuration profile.

Microsoft Intune processed the request and created the policy, making it available within the Configuration Profiles list.

Returning to the Configuration page confirmed that the new profile had been successfully created.

The profile list displays key administrative information including:

- Policy name
- Target platform
- Policy type
- Last modified date
- Scope tags

This provides administrators with a central overview of all deployed configuration profiles within the tenant.

![Configuration Profiles List](images/configuration-profiles-list.png)

---

# Verifying the Configuration Profile

After the profile had been created, I opened it to verify that Microsoft Intune had stored the configuration correctly.

The profile overview displayed:

- Device configuration profile name
- Device and user check-in status
- Platform information
- Profile type
- Profile properties

This verification step is an important part of any deployment process. Rather than assuming the policy has been created successfully, reviewing the profile confirms that the correct platform, profile type and descriptive information have been saved before relying on the policy in a production environment.

![Configuration Profile Overview](images/configuration-profile-overview.png)

---

# Lab Observations

During testing, I intentionally left all Device Restriction settings at their default values.

This decision was made because the enrolled device uses an **Android Enterprise Personally-Owned Work Profile (BYOD)** deployment model. Many available restriction settings are designed primarily for Fully Managed or Corporate-Owned Android Enterprise devices and either do not apply to Personally-Owned Work Profiles or would unnecessarily interfere with later chapters in this project.

By retaining the default configuration, I demonstrated the complete policy creation and deployment process while preserving a functional test device for future Intune exercises.

Immediately after deployment, the reporting dashboard did not display processed device status information. Since no custom restriction settings were configured, the profile contained only the default configuration, resulting in no observable configuration changes being applied during the lab session. This behaviour is consistent with the objective of demonstrating profile deployment rather than enforcing device restrictions.

---

# Skills Demonstrated

Throughout this exercise I demonstrated the ability to:

- Create Android Enterprise Configuration Profiles.
- Select the appropriate profile platform and template.
- Configure policy metadata using meaningful naming conventions.
- Deploy configuration profiles using Azure AD security groups.
- Verify successful profile creation within Microsoft Intune.
- Understand the difference between Configuration Profiles and Compliance Policies.
- Apply configuration management principles appropriate for Android Enterprise Personally-Owned Work Profile devices.

---

# Conclusion

In this chapter I successfully created and deployed my first Microsoft Intune Configuration Profile for Android Enterprise Personally-Owned Work Profile devices.

Although no custom device restrictions were configured, the exercise demonstrated the complete administrative workflow required to deploy configuration profiles using Microsoft Intune. This included selecting the appropriate platform and template, configuring policy information, assigning the profile to a security group, deploying the policy and verifying its creation within the Intune Admin Center.

This provides the foundation for more advanced device management scenarios that will be explored in the following chapters, including Endpoint Security, Device Management and policy troubleshooting.
