# Phase 2: Network/System Configurations Documentation

Welcome to the official documentation site for **Phase 2: Network/System Configurations**.  
This documentation is prepared by **Paterne MURENZI (StudentID: 28302)**.

---

## Table of Contents

- [Project Overview](#project-overview)
- [Topology & IP Allocation](#topology--ip-allocation)
- [Virtual Machines Configuration](#virtual-machines-configuration)
- [Centralized Services](#centralized-services)
- [Network Security & Monitoring](#network-security--monitoring)
- [Deliverables](#deliverables)
- [References](#references)

---

## Project Overview

This phase focuses on building a segmented enterprise lab environment to:

- Configure Windows and Linux servers.
- Implement Active Directory and Group Policies.
- Set up DHCP, NAT, and pfSense firewall.
- Deploy Wazuh for monitoring and file integrity.
- Conduct controlled penetration tests using Kali Linux.
- Integrate IDS (Suricata/Snort) and generate actionable alerts.
- Document all configurations, evidences, and commands in a multi-tab site.

---

## Topology & IP Allocation

The lab is designed with multiple LAN segments:

- **LAN1**: Internal servers and Linux clients.
- **LAN2**: Windows clients managed by pfSense DHCP.
- **NAT/Public**: WAN for Internet access and Kali penetration testing.

> A detailed topology diagram and IP allocation table will be included in the `topology.md` page.

---

## Virtual Machines Configuration

| VM Role                           | Hostname            | IP Address                                      | Network Segment | Notes                                   |
|-----------------------------------|---------------------|-------------------------------------------------|-----------------|-----------------------------------------|
| Windows Server (AD+DNS+NTP)       | AD-StudentID        | 192.168.1.2                                     | LAN1            | Domain Controller, GPO management       |
| Linux Server (DHCP + Samba + IDS) | LS-StudentID        | 192.168.1.3                                     | LAN1            | DHCP provider for LAN1, Samba, FTP, SSH |
| Wazuh Server                      | WS-StudentID        | 192.168.1.4                                     | LAN1            | SIEM, FIM, log correlation              |
| Windows Client                    | PC1-StudentID       | DHCP LAN2                                       | LAN2            | Domain member, GPO testing              |
| Windows Client                    | PC2-StudentID       | DHCP LAN2                                       | LAN2            | GPO and software deployment testing     |
| Linux Client                      | LC-StudentID        | DHCP LAN1/LAN2                                  | LAN1/LAN2       | Samba, SSH, DHCP testing                |
| pfSense Firewall                  | PF-StudentID        | LAN1: 192.168.1.1, LAN2: 192.168.2.1, WAN: DHCP | LAN1, LAN2, WAN | Routing, firewall, NAT, OpenVPN, IDS    |
| Kali Linux                        | Kali-StudentID      | DHCP NAT                                        | NAT             | Pentesting and scanning                 |
| Windows VPN Client                | VPNClient-StudentID | DHCP NAT                                        | NAT             | OpenVPN connectivity testing            |

> More details will be provided in their respective sections (`pfsense/`, `ad/`, `linux/`, etc.).

---

## Centralized Services

The lab demonstrates:

- **Active Directory**: OU structure, user accounts, login policies.
- **Group Policy Objects (GPOs)**: Mapped drives, roaming profiles, software deployment, password policies.
- **Linux services**: DHCP for LAN1, Samba file shares, FTP, SSH.
- **Portfolio website**: Hosted on IIS with full name, StudentID, profile picture, and CV.

---

## Network Security & Monitoring

Key security and monitoring implementations:

- **pfSense Firewall**: NAT, DHCP, schedules, firewall rules, ARP monitoring.
- **NTOPng**: Real-time traffic monitoring for LAN1 and LAN2.
- **Wazuh**: File Integrity Monitoring (FIM), event logging, alerts, and dashboards.
- **IDS (Suricata/Snort)**: Network scanning, brute-force detection, log forwarding to Wazuh.
- **Kali Pentest**: Controlled penetration testing with correlation to IDS/Wazuh events.
- **OpenVPN**: Secure remote access for IT OU members.

---

## Deliverables

You are expected to submit:

1. **Documentation site** – multi-tab web pages for all tasks.
2. **Portfolio site** – personal IIS-hosted webpage.
3. **Wazuh evidence package** – alerts, FIM results, and JSON exports.
4. **pfSense configuration backup** – `config.xml` plus evidence of restore.
5. **Video demonstration** – 15–20 minutes covering all tasks with timestamped evidence.

---

## References

- Course Syllabus: INSY 8211 (B) MON
- Virtualization platform: VirtualBox or VMware Workstation
- Wazuh OVA: 4.14.0
- Kali Linux: 2025.3
- pfSense: Latest stable release
- Microsoft Windows Server: 2008 and above
- Ubuntu or RHEL for Linux Server
