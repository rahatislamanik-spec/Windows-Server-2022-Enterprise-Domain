# Evidence Map

This map connects each portfolio task or phase to the screenshot evidence used in the live case study.

> Public evidence note: screenshots have been redacted where public identifiers, lab account details, hostnames, IP addresses, or domain-specific values were visible. Redaction preserves the workflow evidence while reducing privacy exposure.

| Area | Case study item | Screenshot files | Evidence focus |
|---|---|---:|---|
| Windows 11 endpoint | Task 01 - Install Windows 11 on VMware Fusion | `001-005` | VM provisioning, OS install, lab naming verification |
| Windows 11 endpoint | Task 02 - Provisioning package with Windows Configuration Designer | `006-014` | WCD package creation, account provisioning, package application |
| Windows 11 endpoint | Task 03 - Local Security Policy and UAC secure desktop | `015-025` | Local policy settings, UAC prompt behavior, secure desktop verification |
| Windows 11 endpoint | Task 04 - Start menu pinning and layout export | `026-031` | App pinning, PowerShell export, XML verification |
| Windows 11 endpoint | Task 05 - PowerShell network configuration | `032-036` | Adapter discovery, static IP assignment, IP verification |
| Windows 11 endpoint | Task 06 - Storage Spaces mirror pool | `037-041` | Disk selection, 2-way mirror setup, storage pool validation |
| Windows 11 endpoint | Task 07 - File Share folder on storage volume | `042-045` | Folder creation and location verification |
| Windows 11 endpoint | Task 08 - Share and NTFS permissions | `046-053` | Share permissions, NTFS permissions, UNC path validation |
| Windows 11 endpoint | Task 09 - Microsoft Whiteboard deployment | `054-060` | Microsoft Store install and application launch verification |
| Windows 11 endpoint | Task 10 - File History retention | `061-064` | Backup target selection, retention setting, backup status |
| Windows Server domain | Phase 01 - Windows Server 2022 VM provisioning | `065-071` | UTM resources, Server 2022 install, first login |
| Windows Server domain | Phase 02 - Active Directory Domain Services | `072-085` | AD DS role install, new forest, DNS/GC options, promotion verification |
| Windows Server domain | Phase 03 - DHCP multi-site scopes | `086-093` | DHCP role install, primary lab scope, simulated site scopes, multi-scope visibility |
| Windows Server domain | Phase 04 - SRV02 domain join | `094-109` | Member server install, rename, domain join, static network settings |
| Windows Server domain | Phase 05 - OUs, users, and security groups | `110-126` | OU hierarchy, user creation, group membership |
| Windows Server domain | Phase 06 - Group Policy | `127-139` | GPO creation, account and lockout policy, gpupdate/gpresult verification, lab targeting limitations |
| Windows Server domain | Phase 07 - CompanyShare permissions | `140-146` | Share setup, group permissions, mapped drive, access testing |
| Windows Server domain | Phase 08 - DNS configuration | `147-150` | DNS Manager, forwarder configuration, lookup-zone review |
| Windows Server domain | Phase 09 - Workstation integration | `151-158` | DNS/client network setup, domain join, DHCP/GPO end-to-end verification |

Screenshot files are stored in `assets/screenshots/` using the `screenshot-###.jpg` naming pattern.

## Scope Notes

| Topic | Clarification |
|---|---|
| Production readiness | This is a simulated lab, not a production deployment. |
| Domain controller design | Single-domain-controller lab; no high availability or restore validation is claimed. |
| Multi-site networking | DHCP scopes simulate site segmentation; no physical routed sites were deployed. |
| DNS forwarding | External lookup validation was constrained by UTM NAT behavior on Apple Silicon. |
| Group Policy targeting | Lab policy application was validated; production user restrictions would require correct user OU linking or loopback processing depending on the design. |
