# Active Directory & Group Policy Home Lab

## Project Overview
This project documents the design, deployment, and testing of a small-scale Active Directory environment using Windows Server and a Windows 11 client. The lab was built to simulate a basic enterprise domain and demonstrate how Active Directory, DNS, and Group Policy interact to control user behavior on domain-joined systems.

The focus of this lab was not just installation, but understanding how domain services function together, how policies are scoped and enforced, and how to troubleshoot common issues such as DNS resolution problems, failed domain joins, and Group Policy restrictions.

---

## Lab Environment
- **Domain Controller:** Windows Server 2022  
- **Client Machine:** Windows 11 (domain-joined)  
- **Virtualization:** QEMU/KVM  
- **Network:** Isolated internal virtual network  
- **Core Services:**  
  - Active Directory Domain Services (AD DS)  
  - DNS Server  
  - Group Policy Management  

The environment was intentionally isolated to replicate an internal corporate network without internet dependency.

---

## Domain Controller Deployment
The Windows Server was configured as the primary domain controller for the `homelab.local` domain. During setup, Active Directory Domain Services and DNS were installed and configured together to ensure proper name resolution across the domain.

A static IP address was assigned to the domain controller to prevent DNS and authentication issues that can occur when a server’s address changes. This ensured that clients could reliably locate the domain controller during login and policy processing.

**Screenshot:** Server Manager dashboard showing AD DS and DNS roles installed.

---

## DNS Configuration and Verification
DNS plays a critical role in Active Directory, so DNS configuration and validation were a major focus of this lab. After domain promotion, forward lookup zones were verified and host (A) records were confirmed for both the domain controller and the Windows 11 client.

Name resolution was tested using ping and domain lookups to ensure the client could correctly resolve `homelab.local` and locate the domain controller. Several DNS-related issues were encountered and resolved during testing, reinforcing how tightly AD depends on DNS.

**Screenshot:** DNS Manager showing forward lookup zone and host records.

---

## Windows 11 Domain Join
The Windows 11 client was configured to use the domain controller as its primary DNS server. After verifying network connectivity and name resolution, the client was successfully joined to the `homelab.local` domain.

Once joined, the system was rebooted and confirmed to be operating as a domain member. This step validated that DNS, network configuration, and Active Directory services were functioning correctly.

**Screenshot:** Windows 11 system properties showing domain membership.

---

## Active Directory Organizational Structure
To simulate real-world administration, multiple Organizational Units (OUs) were created to separate users based on policy requirements. This structure allowed different Group Policies to be applied without affecting all users in the domain.

Two main OUs were used:
- **TestUsers** – users subject to restrictive policies
- **UnrestrictedUsers** – users with standard access for comparison and troubleshooting

User accounts were created and placed into their respective OUs to test policy scope and inheritance behavior.

**Screenshot:** Active Directory Users and Computers showing OUs and user accounts.

---

## Group Policy Design and Implementation
A custom Group Policy Object (GPO) was created and linked specifically to the `TestUsers` OU. This policy applied user-level restrictions, including disabling access to Command Prompt.

The purpose of this configuration was to demonstrate how administrators can limit system access for certain users while leaving others unaffected. The GPO was intentionally scoped to an OU rather than the entire domain to highlight best practices in policy targeting.

**Screenshot:** Group Policy Management showing GPO linked to the TestUsers OU.

---

## Policy Enforcement Testing
Policy behavior was tested by logging into the Windows 11 client with different domain accounts. When a user from the `TestUsers` OU logged in, Command Prompt access was blocked, confirming that the policy was applied successfully.

A second user in the `UnrestrictedUsers` OU was able to access Command Prompt normally, demonstrating that the restriction was isolated to the intended OU and not applied globally.

This comparison reinforced how OU placement and GPO scope directly affect user experience.

**Screenshot:** Command Prompt blocked for restricted user.  
**Screenshot:** Command Prompt working for unrestricted user.

---

## Verification and Troubleshooting
To confirm domain authentication, the `whoami` command was used under an unrestricted account to verify the logged-in user context. Group Policy behavior was validated through direct testing rather than assumptions, emphasizing practical troubleshooting over configuration alone.

Throughout the lab, issues related to DNS resolution, static vs dynamic IP addressing, and Group Policy restrictions were identified and resolved, mirroring real-world enterprise troubleshooting scenarios.

**Screenshot:** whoami output showing domain user context.

---

## Key Skills Demonstrated
- Active Directory domain deployment and administration
- DNS configuration and troubleshooting for AD environments
- Domain joining and client authentication
- Organizational Unit design for policy scoping
- Group Policy creation, linking, and enforcement
- User-level access control using GPOs
- Troubleshooting policy and authentication issues

---

## Lessons Learned
This lab reinforced how critical DNS is to Active Directory functionality and how improper network configuration can prevent domain operations entirely. It also demonstrated the importance of OU design when applying Group Policy, as well as the impact policies can have on end users if applied incorrectly.

Most importantly, the lab provided hands-on experience troubleshooting real issues rather than following a scripted setup, which closely reflects enterprise IT environments.

---

## Future Enhancements
- Implement security group filtering for GPOs
- Add password complexity and account lockout policies
- Introduce a second client machine to test multi-user scenarios
- Add login scripts or drive mappings via Group Policy
- Create documentation for help desk–style troubleshooting workflows

