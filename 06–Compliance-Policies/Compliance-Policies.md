# 06 – Compliance Policies

## Introduction

Compliance Policies are a fundamental component of Microsoft Intune and play a key role in ensuring that managed devices meet an organisation's security requirements before they are granted access to corporate resources.

Unlike Configuration Profiles, which configure device settings, Compliance Policies evaluate the security posture of a device against predefined requirements. Microsoft Intune continuously assesses enrolled devices and determines whether they are **Compliant** or **Noncompliant** based on the configured policy.

Compliance Policies are commonly used together with Microsoft Entra Conditional Access to restrict access to Microsoft 365 services from devices that fail to meet organisational security standards.

In this chapter, I created an Android Enterprise Compliance Policy for personally owned work profile devices, configured several security requirements, assigned the policy to a Microsoft Entra Security Group and verified that my enrolled Android device successfully evaluated the policy and achieved a **Compliant** status.

---

# Objectives

After completing this chapter, I will be able to:

- Understand the purpose of Microsoft Intune Compliance Policies.
- Create an Android Enterprise Compliance Policy.
- Configure compliance requirements for Android Enterprise devices.
- Define operating system and security requirements.
- Configure password and encryption policies.
- Assign Compliance Policies to Microsoft Entra Security Groups.
- Monitor compliance evaluation results.
- Verify compliance status on managed devices.
- Troubleshoot common compliance policy issues.

---

# Prerequisites

Before starting this chapter, I had already completed:

- Chapter 01 – Creating the Intune Lab Environment
- Chapter 02 – Intune Administration Center Overview
- Chapter 03 – User and Group Preparation
- Chapter 04 – Android Device Enrolment
- Chapter 05 – Deploying Android Applications with Managed Google Play

In addition, the following components were already configured:

- Android Enterprise connector
- Personally owned Android Enterprise device
- Microsoft Company Portal
- Android Test Users Security Group
- Microsoft Intune device enrolment

---

# Understanding Compliance Policies

Compliance Policies determine whether managed devices satisfy an organisation's security requirements.

Unlike Configuration Profiles, which configure device settings, Compliance Policies evaluate the current state of a device against a predefined set of rules. If a device fails to meet one or more requirements, Microsoft Intune marks it as **Noncompliant**.

Typical compliance checks include:

- Operating system version
- Device encryption
- Screen lock requirements
- Device integrity
- Root detection
- Security provider status
- Password requirements

These compliance results can then be used by Conditional Access policies to control access to corporate applications and resources.

To begin creating a Compliance Policy, navigate to:

```text
Microsoft Intune Admin Center

Devices
    └── Compliance
```

Initially, no Compliance Policies existed within my Intune tenant.

![Compliance Policies Overview](screenshots/compliance-policies-overview.png)

---

# Creating an Android Enterprise Compliance Policy

From the Compliance Policies page, I selected **Create policy**.

Microsoft Intune prompted me to choose both the platform and profile type that the policy would target.

For this laboratory, I selected:

- **Platform:** Android Enterprise
- **Profile:** Personally-owned work profile

This profile type matches the Android Enterprise enrolment method used in Chapter 04 and allows compliance settings to be evaluated against personally owned devices that contain a managed work profile.

![Platform Selection](screenshots/create-compliance-policy-platform.png)

---

# Configuring the Policy Basics

The first step of the wizard was defining the policy information.

I configured the following values:

| Setting | Value |
|---------|-------|
| Name | Android Enterprise Compliance Policy |
| Description | Compliance policy for Android Enterprise devices enrolled in the Intune lab environment |

Providing meaningful names and descriptions makes policies easier to identify and maintain within larger Microsoft Intune environments.

![Policy Basics](screenshots/android-compliance-policy-basics.png)

# Configuring Compliance Settings

After completing the policy information, Microsoft Intune presented the **Compliance settings** page.

The available settings are organised into several categories, allowing administrators to configure different aspects of device security independently.

The available categories included:

- Microsoft Defender for Endpoint
- Device Health
- Device Properties
- System Security

Each category focuses on a different area of compliance evaluation and contributes to the overall compliance status of the managed device.

![Compliance Settings Overview](screenshots/android-compliance-settings-overview.png)

---

# Microsoft Defender for Endpoint

The first section allows Microsoft Intune to integrate with **Microsoft Defender for Endpoint**.

When Defender is integrated with Intune, administrators can use the device's risk level as part of the compliance evaluation process. Devices reporting a risk level above an acceptable threshold can automatically be marked as noncompliant.

Because Microsoft Defender for Endpoint was not part of this laboratory environment, I left the default configuration unchanged.

This demonstrates that Compliance Policies can be created independently of Microsoft Defender while still providing valuable security assessments.

![Microsoft Defender for Endpoint Settings](screenshots/android-compliance-microsoft-defender.png)

---

# Configuring Device Health

The **Device Health** section evaluates the security posture of Android Enterprise devices.

For this laboratory, I configured several settings that reflect common organisational security requirements.

| Setting | Value |
|---------|-------|
| Rooted devices | Block |
| Device Threat Level | Not configured |
| Google Play Services is configured | Require |
| Up-to-date security provider | Require |
| Play Integrity Verdict | Not configured |

![Device Health Settings](screenshots/android-compliance-device-health.png)

Blocking rooted devices helps prevent compromised devices from accessing corporate resources because rooting bypasses many of Android's built-in security protections.

Requiring Google Play Services and an up-to-date security provider helps ensure that Android Enterprise devices continue to receive the services and security components required for reliable device management.

The Device Threat Level and Play Integrity settings were left unconfigured because they depend on additional Microsoft security integrations that were outside the scope of this laboratory.

---

# Configuring Device Properties

The **Device Properties** section allows administrators to define supported operating system versions.

For this policy, I configured a minimum supported Android version while leaving the maximum version unrestricted.

| Setting | Value |
|---------|-------|
| Minimum OS version | 12.0 |
| Maximum OS version | Not configured |

![Device Properties](screenshots/android-compliance-device-properties.png)

Defining a minimum operating system version helps ensure that managed devices continue to receive modern security updates and remain compatible with current Android Enterprise features.

Leaving the maximum operating system version unrestricted allows devices to continue receiving newer Android releases without requiring administrators to update the policy each time Google releases a new version.

# Configuring System Security

The **System Security** section contains the largest collection of compliance settings and is responsible for evaluating several important security controls on managed Android Enterprise devices.

These settings help ensure that enrolled devices meet the organisation's minimum security requirements before they are considered compliant.

For this laboratory, I configured the following settings.

| Setting | Value |
|---------|-------|
| Require encryption of data storage on device | Require |
| Block apps from unknown sources | Block |
| Company Portal app runtime integrity | Require |
| Block USB debugging on device | Block |
| Minimum security patch level | Not configured |
| Require a password to unlock mobile devices | Require |

![System Security Settings](screenshots/android-compliance-system-security-device.png)

These settings enforce several security best practices.

Requiring device encryption protects organisational data by ensuring that information stored on the device cannot be accessed without proper authentication.

Blocking applications from unknown sources reduces the risk of users installing software from untrusted locations outside the Google Play ecosystem.

Requiring Company Portal app runtime integrity helps verify that the Company Portal application has not been tampered with, ensuring reliable communication between the managed device and Microsoft Intune.

Blocking USB debugging helps prevent unauthorised access to the device through Android Developer Options, reducing the risk of local attacks against managed endpoints.

Finally, requiring a device password ensures that users authenticate before accessing both personal and corporate data stored on the device.

---

# Configuring Password Requirements

In addition to enforcing a device password, Microsoft Intune allows administrators to configure password policies for different Android versions.

The policy also supports separate password requirements for the Android Enterprise work profile, allowing organisations to protect corporate data independently from the user's personal profile.

For this laboratory, I left the advanced password settings at their default values while requiring users to unlock both the device and the work profile with a password.

The available options included:

- Password expiration
- Password history
- Maximum inactivity before requiring authentication
- Password complexity for Android 12 and later
- Password type for Android 11 and earlier

Leaving these settings at their defaults keeps the policy straightforward while still demonstrating how password requirements can be managed through Microsoft Intune.

![Password Policy Settings](screenshots/android-compliance-password-policy.png)

---

# Configuring Actions for Noncompliance

After defining the compliance requirements, Microsoft Intune requires administrators to specify what should happen when a device fails the compliance evaluation.

By default, Microsoft Intune immediately marks devices as **Noncompliant** when they no longer satisfy the configured requirements.

For this laboratory, I retained the default action.

| Action | Schedule |
|---------|----------|
| Mark device noncompliant | Immediately (0 days) |

Microsoft Intune also provides additional actions, including:

- Sending an email notification to the end user.
- Sending a push notification.
- Remotely locking the device.
- Adding the device to a retire list.

These options are commonly used within production environments but were intentionally left unconfigured in this laboratory to keep the deployment simple.

![Actions for Noncompliance](screenshots/android-compliance-actions-for-noncompliance.png)

---

# Assigning the Compliance Policy

After completing the policy configuration, the next step was assigning it to the appropriate users.

Rather than assigning the policy directly to individual accounts, I targeted the **Android Test Users** Microsoft Entra Security Group created in the previous chapter.

Using Security Groups provides a scalable administration model because future users can receive the Compliance Policy automatically simply by becoming members of the assigned group.

This approach also aligns with Microsoft best practices for managing Microsoft Intune deployments.

![Compliance Policy Assignment](screenshots/android-compliance-assignments.png)

---

# Reviewing and Creating the Policy

Before creating the Compliance Policy, Microsoft Intune presented a summary of the configuration.

The review page allowed me to verify:

- Policy name
- Platform
- Profile type
- Compliance settings
- Assignment configuration

Reviewing the configuration before deployment helps reduce administrative errors and provides an opportunity to confirm that all required security settings have been configured correctly.

After confirming the settings, I selected **Create** to deploy the Compliance Policy.

![Review and Create](screenshots/android-compliance-review-create.png)

# Verifying Policy Deployment

After the policy was created, Microsoft Intune returned to the Compliance Policies list, where the newly created policy was visible alongside its platform and deployment information.

Seeing the policy listed confirmed that it had been successfully created and stored within the Intune tenant, making it available for compliance evaluation against assigned devices.

![Compliance Policies List](screenshots/android-compliance-policies-list.png)

---

# Monitoring Compliance Evaluation

Microsoft Intune automatically evaluates assigned devices during their next check-in.

To accelerate the evaluation process, I manually synchronised my enrolled Android Enterprise device using the Microsoft Company Portal application. After the device checked in, Microsoft Intune processed the Compliance Policy and evaluated the device against the configured security requirements.

Returning to the policy's monitoring page showed that one managed device had successfully completed the evaluation.

The report confirmed:

- **Compliant:** 1
- **Noncompliant:** 0
- **Others:** 0
- **Total devices evaluated:** 1

This verified that the Compliance Policy had been successfully assigned, processed and evaluated by Microsoft Intune.

![Compliance Report](screenshots/android-compliance-report.png)

---

# Verifying Device Compliance

Finally, I verified the compliance status from the **All devices** page within Microsoft Intune.

The enrolled Android Enterprise device displayed a **Compliant** status together with additional management information, including:

- Device ownership
- Operating system
- Android version
- Primary user
- Last check-in time

This final verification confirmed that the device satisfied every configured compliance requirement and that Microsoft Intune recognised it as compliant.

Successful compliance evaluation demonstrates that the policy configuration, group assignment and device synchronisation were all functioning correctly.

![Android Device Compliant](screenshots/android-device-compliant.png)

---

# Key Learnings

- Compliance Policies evaluate device security rather than configure device settings.
- Android Enterprise Compliance Policies can enforce security requirements such as encryption, password protection and operating system versions.
- Microsoft Intune continuously evaluates managed devices during scheduled check-ins.
- Microsoft Entra Security Groups provide an efficient method for assigning Compliance Policies to multiple users.
- Compliance reports allow administrators to monitor the health and security posture of managed devices.
- Manual synchronisation using Microsoft Company Portal can accelerate compliance evaluation after deploying new policies.

---

# Skills Demonstrated

- Microsoft Intune Compliance Policy administration
- Android Enterprise device compliance
- Microsoft Entra Security Group assignments
- Mobile Device Management (MDM)
- Endpoint compliance monitoring
- Security policy configuration
- Compliance reporting and verification
- Technical documentation using GitHub and Markdown

---

# Interview Tip

One of the most important concepts to understand when working with Microsoft Intune is the difference between **device management** and **device compliance**.

Enrolling a device into Microsoft Intune allows administrators to manage it by deploying applications, configuration profiles and security settings. A Compliance Policy, however, determines whether the device satisfies the organisation's security requirements.

A device can therefore be fully managed by Microsoft Intune while still being marked as **Noncompliant** if it fails one or more compliance checks. This distinction is particularly important when Microsoft Entra Conditional Access policies are configured to allow access only from compliant devices.

Understanding this relationship demonstrates a solid grasp of modern endpoint management and is frequently discussed during interviews for IT Support, Service Desk and Endpoint Administrator roles.

---

# Chapter Summary

In this chapter, I created an Android Enterprise Compliance Policy for personally owned work profile devices using Microsoft Intune.

I configured compliance requirements covering device health, supported operating system versions, encryption, password protection and additional system security controls. After defining the policy, I assigned it to the **Android Test Users** Microsoft Entra Security Group and reviewed the configuration before deployment.

Finally, I synchronised my enrolled Android Enterprise device, monitored the compliance evaluation process and verified that the device was successfully reported as **Compliant** within Microsoft Intune.

This exercise demonstrated the complete lifecycle of a Compliance Policy—from creation and assignment through to evaluation and verification—and highlighted how Microsoft Intune helps organisations maintain secure and compliant managed devices.
