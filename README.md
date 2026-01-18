# Active Directory & Group Policy Home Lab

## Overview
In this project, I built and tested an Active Directory home lab to understand how Windows domains and Group Policy are implemented and managed in enterprise environments. The lab consists of a Windows Server domain controller and a domain-joined Windows 11 client, allowing me to simulate centralized authentication, user management, and policy enforcement.

## Environment
- Windows Server (Domain Controller)
- Active Directory Domain Services (AD DS)
- DNS
- Windows 11 domain-joined client
- Isolated virtual network

## Implementation
I deployed a Windows Server system and promoted it to a Domain Controller, configuring Active Directory Domain Services (AD DS) and DNS for internal name resolution. After validating domain functionality, I joined a Windows 11 client machine to the domain and confirmed authentication using domain credentials.

To simulate a real enterprise structure, I created Organizational Units (OUs) and domain user accounts. I then created a custom Group Policy Object (GPO) and linked it to a specific OU to enforce user-level restrictions. These restrictions were validated by logging in as a restricted domain user and confirming that administrative tools such as Command Prompt were blocked.

To further demonstrate proper Group Policy scoping, I created an additional OU for unrestricted users and tested policy behavior by logging in with different domain accounts on the same Windows 11 system. This confirmed that policies applied only to users in the targeted OU and were removed when users were moved outside of it.

## Technical Tasks Completed
- Deployed a Windows Server system as an Active Directory Domain Controller
- Installed and configured Active Directory Domain Services (AD DS) and DNS
- Created a new Active Directory domain and verified internal name resolution
- Joined a Windows 11 client machine to the domain
- Created Organizational Units (OUs) for restricted and unrestricted users
- Created and managed domain user accounts
- Built and linked a custom Group Policy Object (GPO) to a specific OU
- Applied user-level restrictions using Group Policy
- Verified Group Policy enforcement by testing restricted vs unrestricted users
- Troubleshot DNS, domain join, and Group Policy application issues

## Skills Demonstrated
- Active Directory administration
- Group Policy management and scoping
- DNS configuration and troubleshooting
- Domain authentication and authorization
- User and access control management
- Enterprise IT troubleshooting practices

## Screenshots
Screenshots documenting the lab setup and results can be found in the `screenshots/` folder, including:
- Domain Controller configuration
- Active Directory Users and Organizational Units
- DNS forward lookup zone
- Windows 11 domain join confirmation
- Group Policy linked to the restricted OU
- Command Prompt blocked for restricted users
- Command Prompt allowed for unrestricted users

## Key Takeaways
This lab reinforced how Group Policy impacts end users and demonstrated how Organizational Units and policy scoping are used to selectively enforce security controls in enterprise environments. It also highlighted the importance of DNS and proper network configuration for Active Directory functionality.
