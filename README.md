Active Directory & Group Policy Home Lab
Overview

In this project, I built and tested an Active Directory home lab to understand how Windows domains and Group Policy are implemented and managed in enterprise environments. The lab consisted of a Windows Server domain controller and a domain-joined Windows 11 client, allowing me to simulate centralized authentication, user management, and policy enforcement.

Environment

Windows Server (Domain Controller)

Active Directory Domain Services (AD DS)

DNS

Windows 11 domain-joined client

Isolated virtual network

Implementation

I deployed a Windows Server system and promoted it to a Domain Controller, creating a new Active Directory domain and configuring DNS for internal name resolution. After validating domain functionality, I joined a Windows 11 client machine to the domain and confirmed authentication using domain credentials.

To simulate an enterprise structure, I created Organizational Units (OUs) and domain user accounts. I then created a custom Group Policy Object (GPO) and linked it to a specific OU to enforce user-level restrictions. These restrictions were applied only to selected users, demonstrating how Group Policy scope and inheritance control user behavior without affecting all domain users.

To further validate policy scoping, I compared restricted and unrestricted domain users on the same client system. Restricted users were prevented from accessing tools such as Command Prompt, while unrestricted users retained full access. Moving users between OUs confirmed that Group Policy enforcement was intentional and correctly scoped.

Skills Demonstrated

Active Directory administration

DNS configuration and troubleshooting

Domain join and authentication

Organizational Unit design

Group Policy creation and scoping

User-level security enforcement

Enterprise troubleshooting practices
