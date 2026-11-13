IT SUPPORT HOME LAB: ACTIVE DIRECTORY + HELP DESK TICKETING
===========================================================

A small virtualized Windows domain built to practice day-to-day IT support
work: account management, domain-joined workstations, DNS/DHCP, remote
administration tools, and a working help desk ticketing system.

Built: November 2026
Lab use only. Evaluation software, no real user data, no production systems.


WHAT THIS LAB IS
----------------
A two-user company ("corp.lab") running entirely in VirtualBox on one PC.
It is deliberately small, but it is organized the way a larger environment
would be (groups instead of per-user permissions, a separate IT account,
delegated rights, a naming structure that can grow), so adding people,
computers, or departments later is simple.


WHAT I BUILT
------------
- Windows Server 2025 (Server Core) domain controller: Active Directory
  Domain Services, DNS, and DHCP, administered with PowerShell and SConfig.
- Windows 11 Pro workstations joined to the domain: one for the IT technician
  and one for a staff user.
- Active Directory structure: OUs, security groups, user accounts, and
  delegated password-reset permissions for the IT-Helpdesk group.
- RSAT (Remote Server Administration Tools) on the IT workstation to manage
  the domain without logging into the server.
- Ubuntu Server running osTicket 1.18.1 (Apache + MariaDB) as the help desk,
  reachable by name at http://osticket.corp.lab/.
- An isolated lab network (VirtualBox host-only) plus a NAT adapter for
  updates.


SKILLS PRACTICED
----------------
- Active Directory: users, groups, OUs, delegation of control, least privilege
- Windows Server administration from the command line (PowerShell, SConfig)
- DNS and DHCP: scope design, client DNS configuration, name resolution
- Domain join and workstation setup (Windows 11 Pro)
- Troubleshooting: network, DNS, setup errors, web server reachability
- Linux web server basics (Apache, MariaDB, firewall check, DocumentRoot)
- Help desk ticketing: osTicket configuration, ticket workflow
- Documentation: build guide, troubleshooting log, knowledge base articles


STATUS
------
[x] Windows Server 2025 (Server Core) installed, static IP configured
[x] AD DS, DNS, and DHCP roles installed; forest corp.lab created
[x] DHCP scope serving clients on the lab network
[x] OU structure, security groups, and user accounts created
[x] Windows 11 Pro workstations (IT tech + staff) joined to the domain
[x] RSAT installed; AD Users and Computers used from the IT workstation
[x] Delegated password-reset rights for the IT-Helpdesk group
[x] osTicket 1.18.1 on Ubuntu Server, reachable at http://osticket.corp.lab/
[ ] Account lockout policy and unlock workflow
[ ] Shared folder and mapped drive via Group Policy
[ ] Additional Group Policy objects (restrictions, password policy)
[X] Ubuntu server joined to the domain (realmd/SSSD)
[ ] 10+ tickets worked end to end in osTicket (see 05-ticket-log.txt)
[ ] Ubuntu server hosting NAS and Navidrome 

- Windows Server and Windows 11 Enterprise/Pro guests use Microsoft
  evaluation media where applicable. Evaluation periods expire and the VMs
  need to be rebuilt or re-licensed.
- No passwords, keys, or personal data are stored in this repository.
