Active Directory & Group Policy Home Lab
Project Description

In this project, I built and tested an Active Directory home lab to understand how Windows domains and Group Policy are used in enterprise environments. I deployed a Windows Server system and promoted it to a Domain Controller, configuring Active Directory Domain Services (AD DS) and DNS to support centralized authentication and management.

After the domain was created, I joined a Windows 11 client to the domain and verified connectivity and authentication using domain credentials. This required troubleshooting DNS resolution, static IP configuration, and domain communication to ensure the client could properly locate the Domain Controller.

I then created Organizational Units (OUs) and domain user accounts to simulate a real enterprise structure. A custom Group Policy Object (GPO) was created and linked to a specific OU to enforce user-level restrictions. These restrictions were validated by logging in as a restricted domain user and confirming that administrative tools such as Command Prompt were blocked.

To further demonstrate proper Group Policy scoping, I created an additional OU for unrestricted users and tested policy behavior by logging in with different domain accounts on the same Windows 11 system. This confirmed that policies applied only to users in the targeted OU and were removed when users were moved outside of it.

Technical Tasks Completed

• Deployed a Windows Server system as an Active Directory Domain Controller
• Installed and configured Active Directory Domain Services (AD DS) and DNS
• Created a new Active Directory domain and verified internal name resolution
• Joined a Windows 11 client machine to the domain
• Created Organizational Units (OUs) to separate restricted and unrestricted users
• Created and managed domain user accounts
• Built and linked a custom Group Policy Object (GPO) to a specific OU
• Applied user-level restrictions using Group Policy
• Verified Group Policy enforcement by testing restricted vs unrestricted users
• Troubleshot DNS, domain join, and Group Policy application issues
