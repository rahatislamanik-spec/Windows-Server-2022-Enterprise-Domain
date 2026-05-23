# Enterprise Windows Administration
### From the Endpoint to the Domain — A Full-Stack Case Study

**Md Rahat Islam Anik · George Brown College · Cloud Computing & Network Administration (T465) · Fall 2025**

[![Live Case Study](https://img.shields.io/badge/Live%20Case%20Study-View%20Now-0078D4?style=for-the-badge&logo=windows&logoColor=white)](https://rahatislamanik-spec.github.io/Windows-Server-2022-Enterprise-Domain/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-rahatislamanik-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/rahatislamanik)
[![GitHub](https://img.shields.io/badge/GitHub-rahatislamanik--spec-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/rahatislamanik-spec)

---

| 2 Environments Built | 107+ Screenshots Taken | 20 Tasks & Phases | 3 Servers Deployed |
|:---:|:---:|:---:|:---:|

---

## The Setup

No rack. No lab. No x86 hardware.

This project was built entirely on a **MacBook Air (Apple Silicon)** — which meant no PXE booting, no bridged network adapters, and no Hyper-V. Everything that typically "just works" in a proper lab had to be thought through differently. Two separate virtualization platforms were used across two courses: **VMware Fusion** for the Windows 11 client environment, and **UTM** for the full Windows Server 2022 domain.

What came out the other side: a fully documented, end-to-end enterprise Windows stack — from the endpoint to the domain — with 107+ screenshots capturing every configuration step along the way.

---

## Part 1 — Windows 11 Enterprise Workstation Administration

> **Platform:** VMware Fusion · **OS:** Windows 11 · **Machine Name:** `MdRahatIslamAnik-101635860`

This section covers the deployment, configuration, and hardening of a Windows 11 enterprise workstation from scratch inside **VMware Fusion on macOS**. Every task mirrors real-world enterprise IT operations — provisioning, security policy enforcement, local storage management, and file sharing.

### What Was Built

**Task 01 — Provisioning & Naming**
Deployed a fresh Windows 11 VM inside VMware Fusion. Machine named to lab standard (`YourName-StudentID`) during initial setup — a detail enforced across all subsequent screenshots and configurations.

**Task 02 — Local Security Policy**
Configured local Group Policy settings: account lockout thresholds, password complexity requirements, and audit policies. Verified enforcement via `secpol.msc` and event log review.

**Task 03 — PowerShell Network Management**
Used PowerShell to configure network adapter settings, test connectivity, and manage IP configuration — no GUI dependency.

**Task 04 — Storage Spaces**
Created a Storage Space pool using multiple virtual disks. Configured a simple volume and verified resilience settings — simulating enterprise storage consolidation on a workstation.

**Task 05 — File Sharing & NTFS Permissions**
Configured shared folders with explicit share permissions and layered NTFS permissions. Tested access under different user contexts to validate restriction enforcement.

### Environment

| Component | Detail |
|---|---|
| Virtualization | VMware Fusion (macOS host) |
| Operating System | Windows 11 Enterprise |
| Machine Name | `MdRahatIslamAnik-101635860` |
| Host Hardware | MacBook Air (Apple Silicon) |
| Network | NAT (Fusion-managed) |

---

## Part 2 — Windows Server 2022 Enterprise Domain: `anik.local`

> **Platform:** UTM (Apple Silicon) · **Domain:** `anik.local` · **Servers:** DC + File Server + Workstation

This section covers the end-to-end deployment of a Windows Server 2022 enterprise domain inside **UTM on Apple Silicon** — a platform that eliminates PXE booting, bridged adapters, and Hyper-V. Every workaround, every decision, and every verification step is documented with screenshots.

The domain includes two servers, a domain-joined Windows 11 workstation, multi-site DHCP scopes, Group Policy enforced to the workstation level, layered file permissions, and full DNS integration.

### What Was Built

**Active Directory Domain Services**
Deployed a new forest and promoted the primary server to Domain Controller. Configured DNS integration during promotion. Verified replication health and domain functionality post-promotion.

**DHCP — Multi-Site Scopes**
Configured four DHCP scopes across two simulated sites:
- `Toronto Office` — primary user subnet
- `Toronto Lab` — isolated lab segment
- `Montreal Office` — remote site simulation
- `Montreal Lab` — remote lab segment

Created address reservations, verified lease assignment per scope, and confirmed DHCP lease visibility from the workstation.

**Organizational Unit Structure**
Built a logical OU hierarchy reflecting a real two-site organization:

```
anik.local
├── Toronto
├── Montreal
├── Servers
├── Workstations
├── Groups
└── Users
```

**Users & Security Groups**
Created domain users (`toronto.user`, `montreal.user`) and security groups (`Toronto-Users`, `Montreal-Users`). Assigned users to appropriate groups and verified group membership.

**Group Policy**
Created and linked `TOR-UserLockdown-GPO` to the Toronto OU. Configured:
- Domain-wide password policy (complexity, length, expiry)
- Account lockout policy (threshold, duration, observation window)

Verified policy application via `gpupdate /force` and `gpresult /r` on the workstation.

**File Services — CompanyShare**
Deployed `CompanyShare` on the member file server (`CLCT4003-SRV02`). Applied layered permissions:
- Share-level: security group access
- NTFS-level: granular per-group permissions

Mapped Drive Z to the share from the workstation and tested access restriction enforcement across user accounts.

**DNS**
Configured DNS forwarders for external resolution. Verified internal name resolution using DNS Manager and `nslookup`. Confirmed workstation DNS registration.

**Workstation Integration — End-to-End Verification**
Joined `GB-WS-01-ANIK` (Windows 11) to `anik.local`. Verified:
- DHCP lease assigned from correct scope
- GPO applied and active (`gpresult`)
- Drive Z mapped and share accessible
- User logon functioning under domain credentials

### Environment

| Component | Detail |
|---|---|
| Virtualization | UTM on Apple Silicon (M-series MacBook Air) |
| Primary Server | `CLCT4003-1DC` — Domain Controller, DNS, DHCP |
| Member Server | `CLCT4003-SRV02` — File Server |
| Workstation | `GB-WS-01-ANIK` — Windows 11, domain-joined |
| Domain | `anik.local` |
| Network | NAT-only (UTM limitation on Apple Silicon) |
| Host Hardware | MacBook Air (Apple Silicon) |

---

## Skills Demonstrated

`Active Directory Domain Services` · `DHCP` · `DNS` · `Group Policy (GPO)` · `NTFS Permissions` · `Share Permissions` · `Organizational Units` · `Domain Controller Promotion` · `PowerShell` · `Storage Spaces` · `VMware Fusion` · `UTM` · `Windows Server 2022` · `Windows 11 Enterprise` · `File Services` · `Security Groups` · `Apple Silicon Virtualization`

---

## Live Case Study

The full interactive case study — with 107+ screenshots documenting every task — is published at:

**[rahatislamanik-spec.github.io/Windows-Server-2022-Enterprise-Domain](https://rahatislamanik-spec.github.io/Windows-Server-2022-Enterprise-Domain/)**

---

## Author

**Md Rahat Islam Anik**
Cloud Computing & Network Administration · George Brown College · May 2026

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin)](https://linkedin.com/in/rahatislamanik)
[![GitHub](https://img.shields.io/badge/GitHub-Portfolio-181717?style=flat&logo=github)](https://github.com/rahatislamanik-spec)
