# Intune-Autopilot-Tool
Powershell Script with WPF GUI to onboard Devices to Intune through Microsoft GRAPH API

With this script you can automatically onboard (register) or re-assign Windows Devices onto your Organization Intune, without having to perfom all the manual tasks like, unencrypting the Disk, enabling Windows Recovery, checking and applying a specific Autopilot Profile, assigning the Device to a specific User.

It relies on a "Azure Application" with all the necessary previleges to perform all the actions needed, so Devices can remotely be onboarded, without the presence of an IT account previliged User.

It also checks Hardware and Software to ensure the device being onbaorded is compatible with the latest Windows 11 release.
(TPM Version, SecureBoot, CPU Architecure/Family, avaliable Memory, OS Version, OS Build)

It logs every step to a local log file located at C:\ProgramData\Autopilot_serialNumber_LOG.txt file and uploads this log file to Azure Storage.
It also uploads all the script actions and outputs to Azure Log Analytics, where with a simple Workbook you can showcase all onboarding attempts by the Tool.
