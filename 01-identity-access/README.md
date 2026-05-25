# Azure Identity & Access Management Lab

## Overview 
This lab demonstrates core Azure identity and access management concepts 
by building a complete user, group, and permissions structure from scratch 
in Microsoft Entra ID (Azure AD).

It covers the full AZ-104 Domain 1 scope — creating users, organising 
them into security groups, assigning RBAC roles at subscription level, 
and implementing MFA protection for admin accounts.

## What I built
A complete Azure AD identity setup demonstrating user management, 
group-based access control, RBAC role assignments, and MFA policy.

## What I did
1. Created 3 users with different roles (Developer, Viewer, Admin)
2. Created 3 security groups and assigned users
3. Assigned RBAC roles: Reader / Contributor / User Access Administrator
4. For MFA On this free tier environment,Security Defaults was enabled
  as the Microsoft-recommended equivalent
- Security Defaults enforces MFA for all users automatically
- In a P1/P2 environment, the Conditional Access policy would be:
  - Target: IT-Admins group
  - Apps: All cloud apps
  - Condition: Any location
  - Grant: Require multifactor authentication
  - Mode: Report-only (for testing)

## AZ-104 domains covered
- Manage Azure identities and governance (Domain 1)

## Key concepts learned
- Principle of least privilege
- Group-based access vs individual assignment
- RBAC role hierarchy (Reader → Contributor → Owner)
- MFA enforcement protecting privileged accounts from unauthorised access
- Azure licencing awareness— understanding when Security Defaults 
  vs Conditional Access is appropriate

  ## Tools & services used

- Microsoft Entra ID (Azure AD)
- Azure Role-Based Access Control (RBAC)
- Microsoft Entra Security Defaults
- Azure Portal (portal.azure.com)

## Screeshots 
[Users](screenshots/01-users-list.png)
[Groups](screenshots/02-groups-list.png)
[RBAC](screenshots/03-rbac-assignments.png)
[MFA](screenshots/04-security-defaults.png)
