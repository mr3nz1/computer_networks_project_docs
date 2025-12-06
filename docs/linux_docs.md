# Task 3 — Linux Documentation Server (Apache/Nginx + DHCP for LAN1)

This section documents the setup of the **Linux Documentation Server** for the Phase 2 lab environment.

---

## 1. Linux Server Installation

- Installed **Ubuntu Server** (or Red Hat) on `LS-StudentID`.
- Configured hostname: `LS-StudentID`.
- Installed necessary packages: `apache2` or `nginx`, `isc-dhcp-server`, `wget`, `curl`.

**Evidence:**  
![Linux Server Installation](images/linux-install.png "Ubuntu Server installation screenshot")

---

## 2. Documentation Website Setup

- Hosted multi-tab documentation site under `/var/www/StudentID_docs/`.
- Virtual host configuration:

```bash
sudo nano /etc/apache2/sites-available/studentid-docs.f25.conf
