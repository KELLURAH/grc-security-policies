# Encryption Standard

**Effective Date:** December 8, 2025 
**Control Owner:** Security or Compliance Lead  
**Target Audience:** All employees, contractors, and long-term vendors with system access  
**Classification:** Internal Use

---

## 1. Purpose

Define encryption requirements to protect data confidentiality and integrity in transit and at rest, aligned with legal, regulatory, and customer obligations.

---

## 2. Scope

These requirements apply to:

- All systems, applications, and databases that store, process, or transmit company data
- All endpoints, servers, cloud services, and third-party services handling company data
- All data classifications unless explicitly exempted

---

## 3. Standard Requirements

### 3.1 Data Classification

- Encryption requirements are based on data classification.
- Restricted and Confidential data must be encrypted at rest and in transit.

### 3.2 Encryption in Transit

- All external network communications must use TLS 1.2 or higher.
- Insecure protocols (e.g., Telnet, FTP, HTTP) are prohibited for production use.
- Certificates must be issued by trusted certificate authorities and managed centrally.

### 3.3 Encryption at Rest

- Restricted and Confidential data must be encrypted at rest using industry-standard algorithms (AES-256 or stronger).
- Full disk encryption is required for laptops, workstations, and mobile devices with company data.
- Cloud storage must use provider-managed encryption or customer-managed keys where available.

### 3.4 Key Management

- Encryption keys must be stored and managed in approved key management systems (KMS/HSM).
- Key access is limited to authorized personnel and services under least privilege.
- Key rotation is required at least annually and on suspected compromise.

### 3.5 Secrets Management

- Secrets (API keys, tokens, passwords, certificates) must be stored in approved secrets management tools.
- Secrets must never be hardcoded in source code or stored in plaintext configuration files.

### 3.6 Backups and Logs

- Backups containing Restricted or Confidential data must be encrypted at rest and in transit.
- Logs containing sensitive data must be encrypted and access-controlled.

### 3.7 Cryptographic Standards

- Approved algorithms: AES-256 for symmetric encryption, RSA-2048 or ECC P-256 for asymmetric encryption, SHA-256 or stronger for hashing.
- Deprecated algorithms (e.g., MD5, SHA-1, DES, 3DES, RC4) are prohibited.

### 3.8 Exceptions

- Exceptions require documented risk assessment, compensating controls, and Security or Compliance approval.
- Exceptions must include a defined remediation timeline.

---

## 4. Roles & Responsibilities

| Role | Responsibility |
|------|----------------|
| Security/Compliance Lead | Owns encryption standard and approves exceptions |
| Engineering / IT | Implement encryption controls and key management |
| System Owners | Ensure systems comply with this standard |
| All Personnel | Follow secure handling and storage practices |

---

## 5. Evidence & Audit Artifacts

- Encryption configuration screenshots or exports
- Key rotation and access logs from KMS/HSM
- Device encryption compliance reports
- TLS configuration reports and certificates
- Backup encryption verification logs

---

## 6. Review and Maintenance

- This standard is reviewed at least annually or upon major changes in technology or regulation.

---

**Document Version:** 1.0  
**Last Updated:** December 8, 2025  
**Next Review:** December 2026
