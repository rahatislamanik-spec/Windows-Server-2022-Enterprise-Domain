# anik.local — Windows Server 2022 Enterprise Domain

I built this on a MacBook Air.

No rack. No lab. No x86 hardware. Just UTM, Apple Silicon, and a NAT-only network — which meant no PXE booting, no bridged adapters, no Hyper-V. Everything that usually "just works" in a proper lab had to be thought through differently.

What came out the other side: a fully functional Windows Server 2022 domain — `anik.local` — with two servers, a domain-joined workstation, multi-site DHCP scopes for Toronto and Montreal, Group Policy enforced down to the workstation, NTFS permissions layered on top of share permissions, and 107 screenshots documenting every step.

The platform fought me. The domain still works.

---

**Live case study →** https://rahatislamanik-spec.github.io/Windows-Server-2022-Enterprise-Domain/

---

### What's inside

- **Active Directory Domain Services** — new forest, domain controller promotion, DNS integration
- **DHCP** — multi-site scopes (Toronto Office, Toronto Lab, Montreal Office, Montreal Lab), reservations, lease verification
- **Organizational Units** — Toronto, Montreal, Servers, Workstations, Groups, Users hierarchy
- **Users & Security Groups** — toronto.user, montreal.user, Toronto-Users, Montreal-Users
- **Group Policy** — TOR-UserLockdown-GPO, domain password policy, account lockout, gpupdate /force, gpresult verification
- **File Services** — CompanyShare, layered NTFS + share permissions, Drive Z mapping, access restriction testing
- **DNS** — DNS Manager, forwarder configuration, resolution testing
- **Workstation Integration** — domain join, DHCP lease, GPO application, end-to-end verification

### Environment

| Component | Detail |
|---|---|
| Virtualization | UTM on Apple Silicon (M-series MacBook Air) |
| Primary Server | CLCT4003-1DC — Domain Controller, DNS, DHCP |
| Member Server | CLCT4003-SRV02 — File Server |
| Workstation | Windows 11 — GB-WS-01-ANIK |
| Domain | anik.local |
| Network | NAT-only (UTM limitation on Apple Silicon) |

---

*Md Rahat Islam Anik · [linkedin.com/in/rahatislamanik](https://linkedin.com/in/rahatislamanik) · [github.com/rahatislamanik-spec](https://github.com/rahatislamanik-spec)*
