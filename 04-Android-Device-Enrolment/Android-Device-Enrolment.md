# 04 – Android Device Enrolment

## Overview

Before devices can be managed through Microsoft Intune, they must first be enrolled into the service. Device enrolment establishes a trusted relationship between the endpoint and Microsoft Intune, allowing administrators to deploy applications, configure security policies, enforce compliance requirements and perform ongoing device management.

Microsoft Intune supports several Android Enterprise enrolment scenarios designed to accommodate different ownership models and organisational requirements. Selecting the appropriate enrolment method is essential, as it determines how the device is managed, the level of control available to administrators and how corporate data is separated from personal information.

For this chapter, I enrolled my personal Android smartphone using the **Personally Owned Device with Work Profile** enrolment method. This approach creates a dedicated work profile on the device, allowing corporate applications and data to remain isolated from personal content while preserving the user's privacy.

Throughout this exercise, I used Microsoft Company Portal to register the device, create the Android Enterprise work profile and successfully enrol the device into Microsoft Intune.

---

# Android Enterprise Enrolment Methods

Microsoft Intune supports several Android Enterprise enrolment models, each designed for different organisational requirements.

| Enrolment Method | Typical Scenario |
|------------------|------------------|
| Personally Owned with Work Profile | Employees use their own Android device while organisational data remains isolated within a secure work profile. |
| Corporate-Owned Dedicated Devices | Shared devices used for a single business purpose such as kiosks or digital signage. |
| Corporate-Owned Fully Managed Devices | Organisation-owned devices managed entirely by Microsoft Intune. |
| Corporate-Owned Work Profile | Organisation-owned devices that separate business and personal data through a managed work profile. |

For this laboratory, I selected the **Personally Owned with Work Profile** deployment model because it closely reflects the Bring Your Own Device (BYOD) scenario commonly implemented within enterprise environments.

---

# Installing Microsoft Company Portal

Android Enterprise enrolment begins by installing the Microsoft Company Portal application from the Google Play Store. Company Portal provides the interface required to register the device, authenticate the user account and establish communication between the device and Microsoft Intune.

I installed Microsoft Company Portal directly from the Google Play Store on my Android device.

![Microsoft Company Portal](screenshots/company-portal-google-play.png)

After the installation completed successfully, Company Portal became available on the device and was ready to begin the enrolment process.

![Microsoft Company Portal](screenshots/company-portal-installed.png)

---

# Registering the Device

After launching Company Portal, I signed in using my Microsoft Entra work account associated with my Microsoft Intune tenant.

During the sign-in process, Company Portal validated my credentials and confirmed that my account was authorised to enrol Android devices within the tenant.

![Microsoft Company Portal](screenshots/company-portal-sign-in.png)

Successful authentication initiated the Android Enterprise registration process and prepared the device for work profile creation.

# Creating the Android Enterprise Work Profile

Once authentication was completed, Microsoft Company Portal explained that a separate Android Enterprise work profile would be created on the device.

The work profile provides logical separation between personal and organisational data, allowing business applications, corporate accounts and managed data to remain isolated from personal applications and information. This approach enables organisations to secure corporate resources without requiring full control over the employee's personal device.

Microsoft Company Portal presented information describing the purpose of the work profile before continuing with the enrolment process.

![Microsoft Company Portal](screenshots/android-work-profile-information.png)

After reviewing the information, I continued with the setup process to create the managed work profile.

Android automatically provisioned the work profile, installed the required management components and configured the device for Android Enterprise management.

![Microsoft Company Portal](screenshots/android-work-profile-setup.png)

The enrolment process completed successfully, resulting in a dedicated work profile being created alongside my personal profile. Corporate applications and organisational data are now contained within the managed environment while my personal applications and information remain separate.

---

# Verifying Device Enrolment

After the enrolment process completed, I verified that the device had successfully registered with Microsoft Intune by opening the Microsoft Intune Admin Center.

Navigating to **Devices > Android > Android devices** displayed the newly enrolled smartphone together with key management information, including the ownership type, management authority, compliance state, Android version, assigned user and latest check-in time.

This confirmed that the enrolment process had completed successfully and that the device was actively communicating with Microsoft Intune.

![Microsoft Company Portal](screenshots/android-devices-overview.png)

---

# Device Synchronisation

Once enrolled, Android Enterprise devices periodically synchronise with Microsoft Intune to receive configuration changes, application deployments and policy updates.

Synchronisation occurs automatically at regular intervals, although administrators and users can also manually initiate a synchronisation when immediate updates are required. This ensures that newly assigned applications, configuration profiles and compliance policies are delivered to the device without unnecessary delay.

Although I did not perform a manual synchronisation during this exercise, the successful device check-in shown within the Microsoft Intune Admin Center confirmed that communication between the enrolled device and the Intune service was functioning correctly.

---

# Device Properties and Compliance

Following enrolment, Microsoft Intune begins collecting hardware and management information from the enrolled device. Administrators can review details such as the device model, Android version, ownership type, primary user and management status directly from the Intune Admin Center.

Compliance status is also evaluated after enrolment. Initially, the device is assessed against any compliance policies assigned to the user or device. Since compliance policies are configured later in this repository, this chapter focuses on confirming that the device enrolled successfully and established communication with Microsoft Intune.

The successful check-in and compliant status displayed within the Intune Admin Center confirmed that the device was correctly enrolled and ready for further management tasks, including application deployment, compliance policies and configuration profiles covered in the following chapters.

---

# Key Learnings

- Microsoft Intune supports multiple Android Enterprise enrolment methods to accommodate different ownership models.
- Microsoft Company Portal is required to enrol personally owned Android devices into Microsoft Intune.
- Android Enterprise Work Profiles securely separate organisational data from personal information.
- Successfully enrolled devices automatically establish communication with Microsoft Intune and begin receiving management capabilities.
- Device enrolment forms the foundation for deploying applications, configuration profiles and compliance policies.

---

# Skills Demonstrated

- Android Enterprise administration
- Microsoft Intune device enrolment
- Microsoft Company Portal configuration
- Mobile Device Management (MDM)
- Personally owned (BYOD) device enrolment
- Android Enterprise Work Profile deployment
- Endpoint lifecycle management
- Technical documentation using GitHub and Markdown

---

# Interview Tip

For junior Microsoft Intune and IT Support roles, it is important to understand that enrolling a device into Microsoft Intune does not simply register the device.

The enrolment process establishes a trusted relationship between Microsoft Intune and the endpoint, allowing administrators to deploy applications, enforce compliance policies, configure security settings and manage the device throughout its lifecycle.

Understanding the differences between Android Enterprise enrolment methods and when each should be used demonstrates practical knowledge of modern endpoint management.

---

# Chapter Summary

In this chapter, I successfully enrolled a physical Android smartphone into Microsoft Intune using the **Android Enterprise Personally Owned with Work Profile** enrolment method.

Microsoft Company Portal was installed from the Google Play Store before signing in with my Microsoft Entra account and creating a managed work profile. After the enrolment process completed, I verified that the device had successfully registered with Microsoft Intune and was communicating with the service.

With the Android device successfully enrolled, the environment is now ready for deploying managed applications, configuring compliance policies and applying additional endpoint management settings throughout the remaining chapters of this repository.
