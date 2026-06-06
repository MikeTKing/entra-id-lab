# entra-id-lab
# Microsoft Entra ID Administration Lab
### Bald Tech — Identity & Access Management Project

![Azure](https://img.shields.io/badge/Microsoft_Entra_ID-0078D4?style=for-the-badge&logo=microsoft-azure&logoColor=white)
![MFA](https://img.shields.io/badge/MFA-Enabled-green?style=for-the-badge)
![Conditional Access](https://img.shields.io/badge/Conditional_Access-Configured-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Lab_Status-Active-brightgreen?style=for-the-badge)

---

## Overview

This lab simulates a real-world Microsoft Entra ID (formerly Azure Active Directory) environment for a fictional company, **Bald Tech**. The goal is to demonstrate hands-on identity and access management skills applicable to IT Support, Sysadmin, and Cloud Engineering roles.

All configurations were performed in a live Azure tenant using the Microsoft Entra admin center at [entra.microsoft.com](https://entra.microsoft.com).

---

## Environment

| Detail | Value |
|---|---|
| Tenant | BaldTech792.onmicrosoft.com |
| Admin Account | MICHAELKING@BaldTech792.onmicrosoft.com |
| Admin Roles | Global Administrator, User Administrator |
| Entra ID License | P2 (Free Trial — activated for lab) |
| Region | United States |
| Lab Date | June 2026 |

---

## Objectives

- Create and manage user accounts in Microsoft Entra ID
- Organize users into security groups by department
- Assign administrative roles using least-privilege principles
- Configure a Conditional Access policy to enforce MFA
- Enable per-user MFA for all non-admin accounts
- Capture audit logs as proof of all administrative activity

---

## Users Created

| Display Name | Username | Department |
|---|---|---|
| Bob Johnson | bjohnson@BaldTech792.onmicrosoft.com | HR |
| Josh Smith | jsmith@BaldTech792.onmicrosoft.com | IT |
| Lisa Chen | lchen@BaldTech792.onmicrosoft.com | Finance |
| Mark Davis | mdavis@BaldTech792.onmicrosoft.com | Management |
| Michael King | MICHAELKING@BaldTech792.onmicrosoft.com | IT Admin |

---

## Security Groups

| Group Name | Type | Membership | Purpose |
|---|---|---|---|
| IT-Admins | Security | Assigned | IT department administrators |
| HR-Team | Security | Assigned | Human Resources staff |
| Finance-Team | Security | Assigned | Finance department staff |

---

## Role Assignments

| User | Role | Scope |
|---|---|---|
| Michael King | Global Administrator | Directory-wide |
| Michael King | User Administrator | Directory-wide |
| Josh Smith | Helpdesk Administrator | Directory-wide |

> **Note:** Role assignments follow the principle of least privilege — each user is granted only the permissions required for their function.

---

## Conditional Access Policy

**Policy Name:** Require MFA for All Users

| Setting | Value |
|---|---|
| Users | All users |
| Exclusions | Admin account (Michael King) |
| Target Resources | All cloud apps |
| Access Control | Require multifactor authentication |
| Policy State | Report-only |

> **Why Report-only?** This is Microsoft's recommended best practice when first deploying a Conditional Access policy. Report-only mode logs what *would* have been enforced without impacting user sign-ins, allowing admins to validate the policy scope before enabling it fully.

---

## MFA Configuration

Per-user MFA was enabled for all standard (non-admin) accounts via the Microsoft Entra MFA portal.

| User | MFA Status |
|---|---|
| Bob Johnson | Enabled |
| Josh Smith | Enabled |
| Lisa Chen | Enabled |
| Mark Davis | Enabled |
| Michael King | Disabled (admin exclusion — enforced via Conditional Access) |

---

## Audit Log Summary

All administrative actions were captured in the Entra ID Audit Logs, confirming successful execution of every task in this lab.

| Activity | Category | Service | Status |
|---|---|---|---|
| Add user | UserManagement | Core Directory | Success |
| Add group (x3) | GroupManagement | Core Directory | Success |
| Add member to group | GroupManagement | Core Directory | Success |
| Add member to role (x2) | RoleManagement | Core Directory | Success |
| Add conditional access policy | Policy | Conditional Access | Success |
| Update per-user MFA | UserManagement | Authentication Methods | Success |

> The audit log serves as an immutable record of all changes made to the tenant, which is essential for compliance and security investigations in enterprise environments.

---

## Screenshots

| Screenshot | Description |
|---|---|
| `screenshots/entra-id/users-list.png` | All Contoso users in Entra ID |
| `screenshots/entra-id/groups-list.png` | IT-Admins, HR-Team, Finance-Team security groups |
| `screenshots/entra-id/role-assignments.png` | Michael King assigned roles |
| `screenshots/entra-id/josh-smith-helpdesk-role.png` | Josh Smith Helpdesk Administrator assignment |
| `screenshots/entra-id/conditional-access-policy.png` | Require MFA for All Users policy — Report-only |
| `screenshots/entra-id/mfa-users-enabled.png` | Per-user MFA enabled for all standard accounts |
| `screenshots/entra-id/audit-logs.png` | Full audit log of all lab activity |

---

## Skills Demonstrated

- **Identity & Access Management (IAM)** — user lifecycle, group management, role-based access control
- **Zero Trust Security** — MFA enforcement via Conditional Access
- **Least Privilege Principle** — scoped role assignments, admin account MFA exclusion via policy
- **Compliance & Auditing** — audit log review and documentation
- **Microsoft Entra ID / Azure AD** — hands-on tenant administration
- **Enterprise Security Policy** — Conditional Access policy design and report-only deployment

---

## Tools Used

- Microsoft Entra Admin Center ([entra.microsoft.com](https://entra.microsoft.com))
- Microsoft Entra ID P2 (Free Trial)
- Azure Portal ([portal.azure.com](https://portal.azure.com))

---

## Related Projects

- [Azure Cloud Monitoring & Alerting](../azure-monitoring)
- [Azure Security Infrastructure](../azure-security)
- [Azure Cost Visibility Dashboard](../azure-cost-dashboard)
- [osTicket on Azure](../osticket-azure)

---

## Author

**Michael King**
[GitHub: MikeTKing](https://github.com/MikeTKing) | [LinkedIn](https://linkedin.com/in/michael-king-724247366)
