# Intune Administration Center Overview

## Introduction

The Microsoft Intune Admin Center is the central portal used to manage devices, applications, security policies and endpoint compliance within an organisation.

Before administrators can enrol devices or deploy security policies, they must become familiar with the layout of the portal and understand where the main administrative tasks are performed.

This chapter introduces the Microsoft Intune Admin Center and explains the purpose of its main management areas. No configuration changes are performed during this chapter. The objective is simply to become familiar with the interface before beginning hands-on administration in the following chapters.

---

# Objectives

After completing this chapter, you should be able to:

- Navigate the Microsoft Intune Admin Center
- Understand the purpose of the main administrative areas
- Locate device management features
- Locate user and group management
- Locate application management
- Locate Endpoint Security
- Locate reporting features
- Locate Tenant Administration

---

# Prerequisites

Before starting this chapter, ensure you have:

- Microsoft Intune Plan 1 Trial activated
- Access to the Microsoft Intune Admin Center
- Global Administrator permissions

---

# Opening Microsoft Intune Admin Center

Microsoft Intune can be accessed directly by opening:

```text
https://intune.microsoft.com
```

Alternatively, from the Microsoft 365 Admin Center navigate to:

```text
Show all
    └── Admin centers
            └── Microsoft Intune
```

After signing in, the Microsoft Intune Admin Center Home page is displayed.

This page acts as the starting point for all Microsoft Intune administration tasks.

![Microsoft Intune Admin Center](screenshots/intune-admin-center-home.png)

---

# Dashboard

The Dashboard provides an overview of the Microsoft Intune environment.

It allows administrators to quickly understand the current state of the tenant without navigating through multiple menus.

From the Dashboard administrators can obtain information about:

- Devices
- Compliance
- Applications
- Endpoint Security
- Tenant health

As additional devices are enrolled later in this repository, the Dashboard will begin displaying useful management information.

![Dashboard Overview](screenshots/intune-dashboard-overview.png)

---

# Devices

The **Devices** section is one of the most frequently used areas within Microsoft Intune.

Once computers or mobile devices have been enrolled, administrators use this section to monitor their status and perform management tasks remotely.

From this page administrators can:

- View enrolled devices
- Review hardware information
- Check compliance status
- Deploy configuration profiles
- Perform remote management actions

Microsoft Intune supports multiple operating systems including:

- Windows
- Android
- iOS/iPadOS
- macOS
- Linux

At this stage of the laboratory no devices are displayed because device enrolment is performed later in **Chapter 04 – Android Device Enrollment**.

![Devices Overview](screenshots/intune-devices-overview.png)

---

# Users

The **Users** section displays Microsoft Entra ID users that can access organisational resources.

Although user accounts are created within Microsoft Entra ID, Microsoft Intune uses those identities to manage enrolled devices.

Administrators commonly use this section to:

- View users
- Review assigned licences
- View managed devices
- Troubleshoot user issues

In the next chapter, users will be prepared for Microsoft Intune by assigning the required licences and permissions.

![Users Overview](screenshots/intune-users-overview.png)

---

# Groups

Groups simplify administration by allowing applications and policies to be assigned to multiple users or devices simultaneously.

Instead of configuring each user individually, administrators assign resources to groups, making management much easier.

Microsoft Intune supports:

- User Groups
- Device Groups

Throughout this repository, groups will be used when deploying applications and assigning compliance policies.

![Groups Overview](screenshots/intune-groups-overview.png)

---

# Apps

The **Apps** section is used to deploy and manage applications across enrolled devices.

One of the main advantages of Microsoft Intune is that applications can be installed remotely without requiring physical access to a user's device. This saves time for IT departments and ensures users receive the software they need in a consistent and secure manner.

From this area administrators can:

- Add applications
- Assign required applications
- Publish available applications
- Monitor installation status
- Remove applications when required

Common applications managed through Microsoft Intune include:

- Microsoft Edge
- Microsoft Outlook
- Microsoft Teams
- Microsoft Authenticator

Application deployment is covered in detail in **Chapter 07 – Application Deployment**.

![Apps Overview](screenshots/intune-apps-overview.png)

---

# Endpoint Security

The **Endpoint Security** section allows administrators to configure security policies that help protect managed devices.

Rather than configuring each device manually, administrators can deploy security settings to many devices simultaneously.

Examples include:

- Microsoft Defender Antivirus
- Firewall policies
- Disk encryption
- Security Baselines

Using centrally managed security policies helps organisations maintain a consistent security standard across all managed devices.

Endpoint Security will be explored further in **Chapter 09 – Endpoint Security**.

![Endpoint Security Overview](screenshots/intune-endpoint-security-overview.png)

---

# Reports

Monitoring devices is an important part of endpoint management.

The **Reports** section provides administrators with information about the overall health of the Microsoft Intune environment.

Reports can be used to review:

- Device compliance
- Device inventory
- Application deployment
- Policy status
- Device enrolment

These reports help administrators quickly identify devices that require attention and verify that deployments have completed successfully.

As additional devices are enrolled throughout this repository, the Reports section will become increasingly useful.

![Reports Overview](screenshots/intune-reports-overview.png)

---

# Tenant Administration

The **Tenant Administration** section contains settings that affect the Microsoft Intune environment as a whole.

Unlike the previous sections, which focus on managing users or devices, Tenant Administration is used to configure global settings for the organisation.

Examples include:

- Tenant-wide settings
- Connectors
- Customisation
- Organisational preferences
- Administrative configuration

Most of these settings are configured during the initial deployment of Microsoft Intune and are reviewed only occasionally afterwards.

![Tenant Administration Overview](screenshots/intune-tenant-administration-overview.png)

---

# Key Learnings

By completing this chapter you have learned how to:

- Navigate the Microsoft Intune Admin Center
- Understand the purpose of each major administrative area
- Identify where devices, users and groups are managed
- Locate application management
- Locate Endpoint Security
- Locate reporting features
- Locate Tenant Administration

This knowledge provides the foundation required for the practical configuration tasks performed in the following chapters.

---

# Skills Developed

By completing this chapter, the following skills were developed:

- Microsoft Intune navigation
- Endpoint management fundamentals
- Administrative portal familiarity
- Microsoft Intune administration
- Technical documentation

---

# Interview Tip

For junior IT Support and Microsoft Intune Administrator roles, you are not expected to know every feature available within Microsoft Intune.

However, you should be able to explain:

- What Microsoft Intune is.
- The purpose of the main areas of the Admin Center.
- Where administrators manage devices.
- Where applications are deployed.
- Where security policies are configured.
- Where reports can be viewed.

Understanding the structure of the Admin Center demonstrates that you are comfortable navigating the platform and know where common administrative tasks are performed.

---

# Chapter Summary

In this chapter you explored the Microsoft Intune Admin Center and became familiar with the main administrative areas used by administrators.

The following sections were introduced:

- Dashboard
- Devices
- Users
- Groups
- Apps
- Endpoint Security
- Reports
- Tenant Administration

Although no configuration changes were made, this chapter provides the foundation for the remainder of the repository.

In the next chapter, users and groups will be prepared for device enrolment by assigning the required licences and reviewing the administrative structure used within Microsoft Intune.
