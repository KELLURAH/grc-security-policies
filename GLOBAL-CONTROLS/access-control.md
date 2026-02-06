# Access Control Controls

**Effective Date:** February 6, 2026  
**Control Owner:** IT or Security Lead  
**Target Audience:** All employees, contractors, and long-term vendors with system access  
**Classification:** Internal Use

---

## 1. Purpose

Ensure that access to company systems, data, and facilities is granted based on business necessity and that unauthorized access is prevented.

---

## 2. Scope

These controls apply to:

- All systems, applications, networks, and data owned or managed by the company
- All personnel, contractors, and third-party vendors with access to company logical or physical assets
- All authentication methods and identity provider (IdP) configurations

---

## 3. Control Objectives

- Implement the principle of Least Privilege (PoLP) and Need-to-Know
- Ensure accountability by uniquely identifying users and tracking actions
- Maintain a lifecycle approach to access (Provisioning -> Review -> Termination)
- Protect against unauthorized access and credential theft

---

## 4. Control Requirements

### 4.1 Access Provisioning and Approval

- Access to systems and data is granted only after a formal request and documented approval from the asset owner or designated manager.
- Access rights are granted based on predefined roles or job functions (RBAC).

### 4.2 Onboarding and Offboarding

- New personnel receive access only to systems required for their specific role.
- Access is revoked within 24 hours of employee termination or contractor offboarding.
- Transfers require a review of existing access to ensure it remains appropriate for the new role.

### 4.3 Identification and Authentication

- Every user must have a unique identifier (Username/ID).
- Shared or group accounts are prohibited unless a specific business justification is approved and documented.
- Passwords (where used) must meet complexity requirements and be managed via an approved password manager.

### 4.4 Multi-Factor Authentication (MFA)

- MFA is mandatory for all access to production environments, remote access (VPN/SSO), and sensitive applications (e.g., HRIS, Finance, Email).
- Phishing-resistant MFA (e.g., FIDO2/WebAuthn) is preferred for high-risk accounts.

### 4.5 Least Privilege and Role-Based Access Control (RBAC)

- Users are granted the minimum level of access required to perform their job duties.
- Administrative or "Superuser" access is restricted to a limited number of authorized personnel.

### 4.6 Privileged Access Management (PAM)

- Privileged access is separated from standard user access.
- Activities performed with privileged accounts are logged and monitored.
- Just-in-Time (JIT) access elevation is used where technically feasible.

### 4.7 Periodic Access Reviews

- User access rights are reviewed at least quarterly (for high-risk systems) or semi-annually (for standard systems).
- Inactive accounts (e.g., 90 days without login) are automatically disabled or removed.
- Review results are documented, and inappropriate access is removed within 5 business days of discovery.

### 4.8 Remote Access

- Remote access must occur through secure, encrypted channels (VPN, Zero Trust Network Access/ZTNA).
- Device health checks (e.g., endpoint security status) are performed prior to granting remote access.

### 4.9 Physical Access Control

- Physical access to offices, server rooms, and data centers is restricted using badge readers, biometric scanners, or locks.
- Visitors are logged and escorted by authorized personnel at all times.

### 4.10 Exceptions

- Any deviation from these controls requires an approved exception request documented in the [Security Exception Request Form](../TEMPLATES/exception-request-form.md).

---

## 5. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| Security/IT Lead | Owns access control infrastructure (IdP, SSO, VPN) |
| Asset Owner | Approves access to specific applications or data sets |
| People Operations (HR) | Triggers onboarding and offboarding workflows |
| All Personnel | Protect credentials and report unauthorized access |

---
