# Intune-Autopilot-Tool
Powershell Script with WPF GUI to onboard Devices to Intune through Microsoft GRAPH API

![alt text](https://github.com/Joaogcp/Intune-Autopilot-Tool/blob/main/GUI_Screenshot.jpg?raw=true)

![alt text](https://github.com/Joaogcp/Intune-Autopilot-Tool/blob/main/Workbook_Screenshot.jpg?raw=true)

With this script you can automatically onboard (register) or re-assign Windows Devices onto your Organization Intune, without having to perfom all the related manual tasks such as: Unencrypting the System Disk, Enabling Windows Recovery, Checking and applying a specific Autopilot Profile, Assigning the Device to a specific User.

It relies on an "Azure Application" with all the necessary previleges to perform all the actions needed through Microsoft GRAPH API, so Devices can remotely be onboarded, without needing the presence of an IT account previliged User by the Device premises.

It also checks Hardware and Software to ensure the device being onbaorded is compatible with the latest Windows 11 release.
(TPM Version, SecureBoot, CPU Architecure/Family, Avaliable Memory, OS Version, OS Build)

It logs every step to a local log file located at C:\ProgramData\Autopilot_serialNumber_LOG.txt file and uploads this log file to Azure Storage.
It also uploads all the script actions and outputs to Azure Log Analytics (Workbook_Screenshot.jpg), where with a simple Workbook you can showcase all onboarding attempts by the Tool.

# REQUIREMENTS

ALL NEEDED FIELDS IN THE SCRIPT HAVE "#ChangeMe" STRING SO THEY CAN BE EASILY IDENTIFIED AND ALTERED TO YOUR VALUES, just use Find.

#### - You need to have every User in your Azure AD with the extensionAttribute5 field filled in the GroupTag value (Tag) of the sub-company the User belongs to.
#### - You need to upload the MahApps.Metro DLL files to an Azure Blob storage, so these can be retrived by the script upon execution.
#### - You need to setup an Azure Applicaion with, at least,the following previleges over your Intune and Azure AD:

###### -DeviceManagementConfiguration.Read.All
Application
Read Microsoft Intune device configuration and policies
Yes
Granted for your Company Azure

###### -DeviceManagementManagedDevices.Read.All
Application
Read Microsoft Intune devices
Yes
Granted for your Company Azure

##### -DeviceManagementServiceConfig.ReadWrite.All
Application
Read and write Microsoft Intune configuration
Yes
Granted for your Company Azure

##### -Directory.Read.All
Application
Read directory data
Yes
Granted for your Company Azure
