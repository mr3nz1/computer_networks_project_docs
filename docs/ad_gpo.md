# Task 2 — Active Directory & Group Policy (Windows Server)

This section documents the setup and configuration of **Windows Server Active Directory** and Group Policies for the
Phase 2 lab.

---

## 1. Windows Server Installation & Promotion

- Installed Windows Server (2008–2022 recommended).
- Promoted to **Domain Controller** for domain: `StudentID.f25`.

**Evidence:**  
![DC Promotion](images/Task 2/domain_controller_evidence.png "Domain Controller promotion screenshot")

---

## 2. Organizational Units (OUs) & User Accounts

**OUs Created:**

- IT
- HR
- Students
- Finance

**Example Users:**

| OU       | Sample Users       |
|----------|--------------------|
| IT       | IT1, IT2           |
| HR       | HR1, HR2           |
| Students | Student1, Student2 |
| Finance  | Fin1, Fin2         |

**Naming Convention:** `OU + sequential number`

**Evidence:**  
![ADUC OUs & Users](images/Task 2/ous_and_users.png "ADUC showing OUs and users")

---

## 3. IIS & Portfolio Website

- Installed IIS on the DC.
- Hosted a portfolio website with:
    - Full name
    - StudentID
    - Profile picture
    - Professional summary
    - Education & experience
    - Skills & certificates
    - Contact info

**Evidence:**  
![Portfolio Website](images/Task 2/portfolio_website.png "Portfolio website screenshot")

---

## 4. NTP Configuration

- Configured **NTP** on the DC.
- Pushed NTP client settings via GPO to all domain systems.

**Evidence:**  
![NTP GPO](images/Task 2/ntp.png "NTP settings via GPO")

---

## 5. Roaming Profiles & Mapped Drives

- Configured **roaming profiles** and **mapped drives** via GPO.
- Example paths:

**Evidence:**  
![NTP GPO](images/Task 2/roaming_folders.png "NTP settings via GPO")
![NTP GPO](images/Task 2/roaming-folder.png "NTP settings via GPO")
![NTP GPO](images/Task 2/shared.png "NTP settings via GPO")
![NTP GPO](images/Task 2/mapped_drives.png "NTP settings via GPO")
