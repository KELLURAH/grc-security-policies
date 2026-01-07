# Zero Trust for Remote Working - GRC Policy for SMBs and Startups

**Effective Date:** January 2026  
**Policy Owner:** Security & Compliance Team  
**Target Audience:** Remote and hybrid workforce  
**Classification:** Internal Use

---

## Executive Summary

This Zero Trust for Remote Working policy establishes the security framework for organizations with distributed workforces. Zero Trust operates on the principle of "never trust, always verify" — treating every access request as a potential threat regardless of source, location, or authentication history.

For resource-constrained SMBs and startups, this policy provides a practical, phased approach to implementing zero trust principles without requiring enterprise-scale infrastructure.

---

## 1. Policy Purpose & Scope

### 1.1 Purpose

- Protect organizational data and systems from remote access threats
- Establish baseline security controls for distributed work environments
- Reduce attack surface and lateral movement capabilities
- Ensure compliance with industry regulations and frameworks (ISO 27001, SOC 2, NIST)

### 1.2 Scope

This policy applies to:

- All employees working remotely or in hybrid arrangements
- Contractors and third-party vendors accessing company systems
- All devices connecting to company networks (laptops, mobile devices, IoT)
- All applications and cloud services accessed remotely
- Personally-owned devices (BYOD) on corporate networks

**Exclusions:**

- Physical office-only personnel (minimum baseline controls apply)
- Public-facing, unauthenticated services

---

## 2. Core Zero Trust Principles

### 2.1 Never Trust, Always Verify

- Every access request must be authenticated and authorized
- No implicit trust based on network location, previous authentication, or device type
- Continuous verification throughout the session

### 2.2 Least Privilege Access

- Grant minimum permissions required to perform job functions
- Implement role-based access control (RBAC)
- Regular access reviews (quarterly minimum)
- Immediate revocation upon role change or separation

### 2.3 Assume Breach Mentality

- Design controls assuming devices may be compromised
- Implement micro-segmentation to limit lateral movement
- Enable comprehensive audit logging and monitoring
- Maintain rapid incident response procedures

### 2.4 Verify Explicitly

- Use all available data (user identity, device, location, behavior)
- Implement multi-factor authentication (MFA) universally
- Validate device security posture before access
- Monitor for anomalous behavior patterns

---

## 3. Authentication & Identity Management

### 3.1 Multi-Factor Authentication (MFA)

**Requirement:** MFA is mandatory for all remote access

- **Factors accepted:**
  - Something you know (password)
  - Something you have (hardware token, smartphone, security key)
  - Something you are (biometrics)

- **Implementation minimum:**
  - MFA for VPN/remote desktop access
  - MFA for email and cloud applications
  - MFA for administrative/privileged accounts (2+ factors minimum)

- **Best practices:**
  - Encourage hardware security keys for high-risk accounts
  - Use authenticator apps (Microsoft Authenticator, Google Authenticator) as minimum
  - Implement passwordless authentication where possible

### 3.2 Password Management

- Minimum 14 characters for local/non-cloud accounts
- Minimum 12 characters if cloud-based MFA is enforced
- Password managers required for team access to shared accounts
- No password reuse across systems
- Change passwords upon any suspected compromise
- Temporary passwords for all new hires, expired quarterly

### 3.3 Privileged Account Management (PAM)

- Segregate privileged accounts from standard user accounts
- Require separate credentials for administrative access
- Log all privileged session activity
- Implement just-in-time (JIT) access elevation for SMBs/startups
- Regular privilege access reviews (monthly minimum)

### 3.4 Identity Verification for Offboarding

- Disable all access immediately upon separation
- Revoke physical credentials, tokens, and digital accounts
- Audit for account misuse within 24 hours of termination
- Recover company devices and data within 48 hours

---

## 4. Device Security & Compliance

### 4.1 Device Inventory & Registration

All devices accessing company resources must be:

- Registered in a Mobile Device Management (MDM) system or inventory
- Assigned to a specific user or team
- Tracked for compliance status

**Supported Devices:**

- Company-issued laptops/desktops (Windows 10+, macOS 12+, Ubuntu 20.04+)
- Company-managed mobile devices (iOS 15+, Android 12+)
- BYOD devices meeting minimum security standards

### 4.2 Device Security Posture Requirements

**Operating System:**

- Current OS version (within 1 major version)
- Security patches applied within 30 days of release
- Automatic updates enabled
- End-of-life operating systems prohibited

**Endpoint Protection:**

- Antivirus/anti-malware software installed and current
- Windows Defender, Avast, or approved equivalent
- Real-time threat scanning enabled
- Quarantine/removal of detected threats

**Encryption:**

- Full-disk encryption enabled (BitLocker, FileVault, LUKS)
- AES-256 or equivalent minimum
- Verified via MDM before access granted

**Firewall & Network:**

- Personal firewall enabled on all devices
- Windows Defender Firewall (Windows) or equivalent
- Block unauthorized inbound connections
- Monitor outbound connections for anomalies

### 4.3 Device Access Control

- Devices failing compliance checks must remediate or lose access
- Automatic device lock after 15 minutes of inactivity
- Mandatory password/biometric unlock requirement
- Remote wipe capability for lost/stolen devices

---

## 5. Network Access & VPN Requirements

### 5.1 VPN for Remote Access

**Requirement:** All remote access to on-premises systems must use a VPN

- **VPN Protocol:** IKEv2, OpenVPN, or WireGuard minimum
- **Encryption:** AES-256 or ChaCha20-Poly1305
- **Authentication:** Client certificate + MFA
- **Logging:** All VPN connections logged with timestamps and user identity

### 5.2 VPN Policies

- Split tunneling strictly prohibited (all traffic through VPN)
- Regular security audits of VPN infrastructure (annual minimum)
- VPN software kept current with latest patches
- Idle timeout after 30 minutes of inactivity

### 5.3 Network Segmentation (Micro-segmentation)

- Separate networks/VLANs for: production, development, guest, IoT
- Restrict lateral movement between segments
- Implement firewall rules between segments
- Default-deny approach (whitelist approved traffic only)

### 5.4 Zero Trust Network Access (Cloud-Native Alternative)

For startups leveraging cloud-only architecture:

- Implement Zero Trust Network Access solutions (Cloudflare Zero Trust, Tailscale)
- Replace traditional VPN with service-based access control
- Continuous device posture verification before access
- Automatic policy enforcement based on user context

---

## 6. Application & Data Access

### 6.1 Application Whitelisting

- Only approved applications permitted to run
- Block unauthorized execution of scripts and binaries
- Maintain centralized approved applications list
- Quarterly review of installed applications

### 6.2 Data Access Controls

**Classification Levels:**

- **Public:** No restrictions
- **Internal:** Requires authentication
- **Confidential:** Requires authentication + authorization + encryption in transit
- **Restricted:** Requires authentication + authorization + encryption at rest/transit + audit logging

**Access Control Implementation:**

- Apply principle of least privilege to all data repositories
- Implement role-based access control (RBAC)
- Enforce attribute-based access control (ABAC) for sensitive data
- Require re-authentication for sensitive data access

### 6.3 Sensitive Data Access

- Sensitive data access (PII, financial, health data) requires additional verification
- Implement session-based access tokens with short expiration (1 hour maximum)
- Disable clipboard functionality for sensitive systems
- Prohibit data exfiltration tools (USB drives on sensitive systems)
- Monitor and log all access to sensitive data

### 6.4 Shadow IT Prevention

- Maintain approved cloud applications list
- Block access to unapproved cloud services
- Deploy Cloud Access Security Broker (CASB) if budget allows
- Regular audit of application usage

---

## 7. Continuous Monitoring & Verification

### 7.1 Behavioral Analytics & Anomaly Detection

- Monitor for unusual access patterns (time, location, data volume)
- Alert on impossible travel scenarios (access from two locations too quickly)
- Track failed authentication attempts (>5 failures = immediate investigation)
- Monitor for privilege escalation attempts

### 7.2 Logging & Audit Trails

**Minimum logging requirements:**

- Authentication events (success, failure, MFA)
- Administrative/privileged access
- Data access and modifications
- VPN connections and disconnections
- Device enrollment/compliance changes
- Security events and alerts

**Log retention:**

- Minimum 90 days online
- 1 year archived storage
- Tamper protection enabled
- Central logging with synchronized timestamps

### 7.3 Threat Detection & Response

- Real-time alerts for critical security events
- Automated response for high-confidence threats
- Manual investigation for suspicious activities
- Incident response procedures (documented and tested)
- Post-incident reviews to prevent recurrence

### 7.4 Metrics & KPIs

- MFA adoption rate (target: 100% of remote users)
- Device compliance rate (target: 95%+)
- Time to detect anomalies (target: <1 hour)
- Time to respond to incidents (target: <4 hours for critical)
- Unauthorized access attempts (target: 0 successful)

---

## 8. Implementation Roadmap for SMBs & Startups

### Phase 1: Foundation (Months 1-3)

**Priority:** Essential baseline controls

- [ ] Implement MFA for all remote users
- [ ] Deploy MDM/device management solution
- [ ] Establish VPN access requirement
- [ ] Create device security baselines
- [ ] Implement basic logging and monitoring

**Tools (budget-friendly):**

- Okta, Azure AD, or Auth0 (identity)
- Jamf, Intune, or Kandji (device management)
- OpenVPN or WireGuard (VPN)
- CloudFlare Zero Trust (optional, advanced)

### Phase 2: Enhancement (Months 4-6)

**Priority:** Strengthen baseline controls

- [ ] Implement RBAC for applications and data
- [ ] Enable disk encryption enforcement
- [ ] Deploy antivirus/endpoint detection
- [ ] Establish application whitelisting
- [ ] Implement behavioral monitoring

**Tools:**

- Microsoft Defender or CrowdStrike (endpoint protection)
- Absolute Software or Prey (device tracking)
- Splunk (light) or ELK Stack (centralized logging)

### Phase 3: Maturity (Months 7-12)

**Priority:** Advanced controls and automation

- [ ] Implement micro-segmentation
- [ ] Deploy behavioral analytics
- [ ] Enable passwordless authentication
- [ ] Automate incident response
- [ ] Achieve continuous compliance monitoring

**Tools:**

- CloudFlare Zero Trust or Zscaler (advanced access)
- Suricata or Zeek (network monitoring)
- Automation via Terraform/Ansible

---

## 9. Compliance Alignment

### 9.1 Regulatory Mappings

This policy supports compliance with:

- **ISO 27001:2022** - Access Control (A.8), Cryptography (A.10)
- **SOC 2 Type II** - Logical Access Controls
- **NIST 800-53** - AC-2 (Account Management), IA-2 (Authentication)
- **GDPR** - Technical and organizational measures for data protection
- **CCPA** - Reasonable security measures

### 9.2 Evidence Collection

- Maintain documentation of MFA deployment
- Retain logs of device compliance status
- Document access control configurations
- Collect penetration test/security audit results
- Track policy acknowledgments from employees

---

## 10. Roles & Responsibilities

| Role | Responsibility |
|------|-----------------|
| **Security Lead** | Policy ownership, incident response, risk assessment |
| **IT Administrator** | Implementation, device management, access control |
| **Manager** | Enforce policy with team, onboarding/offboarding |
| **Employee** | Follow policy, protect credentials, report suspicious activity |
| **Contractor/Vendor** | Comply with policy terms, sign data processing agreements |

---

## 11. Policy Exceptions & Waivers

**Exception Process:**

1. Submit written request with business justification
2. Risk assessment by Security Lead
3. Approval by Executive/Manager (based on risk level)
4. Document exception with expiration date (maximum 6 months)
5. Quarterly review of active exceptions

**Types of Exceptions:**

- Legacy system requiring alternative access method
- Temporary contractor with limited access needs
- Research/testing requiring relaxed controls

**Prohibited (no exceptions):**

- Disabling MFA for standard users
- Removing encryption from company data
- Sharing credentials or authentication factors
- Removing audit logging

---

## 12. Incident Response

### 12.1 Suspected Breach Procedure

1. Isolate affected device immediately
2. Preserve logs and forensic evidence
3. Notify Security Lead within 1 hour
4. Assess scope (other compromised accounts/data)
5. Implement containment measures
6. Notify affected users and regulators if required

### 12.2 Compromised Credentials

- Reset password immediately
- Force re-authentication on all sessions
- Review access logs for unauthorized activity
- Reset MFA tokens if compromised
- Monitor account for 30 days post-incident

### 12.3 Lost or Stolen Device

- Immediately revoke access credentials
- Initiate remote wipe if MDM-capable
- Contact vendor if hardware security keys are lost
- Review access logs before device loss
- Replace device and re-provision

---

## 13. Training & Awareness

**All remote workers must complete:**

- Initial zero trust security training (annually minimum)
- MFA and password management training
- Phishing and social engineering awareness
- Device security best practices
- Data handling procedures for their role

**Documentation provided:**

- Quick-start guide for remote access
- Device setup guide with security checklists
- Incident reporting procedures
- FAQ and troubleshooting guide

---

## 14. Review & Maintenance

- **Policy Review:** Annually (January)
- **Control Effectiveness:** Quarterly assessments
- **Threat Landscape Review:** Semi-annual updates
- **Audit Frequency:** Annual external, monthly internal
- **Update Triggers:** 
  - Major security incident or breach
  - Significant change in threat landscape
  - New technology adoption
  - Regulatory requirement changes

---

## 15. Acknowledgment

All employees and contractors must acknowledge receipt and understanding of this policy. Acknowledgments must be retained for audit purposes.

**[Acknowledgment form attached separately]**

---

## Appendix A: Definitions

- **Authentication:** Verification of user identity
- **Authorization:** Determining what authenticated user can access
- **Micro-segmentation:** Dividing network into isolated zones
- **Least Privilege:** Granting only minimum necessary access
- **Device Posture:** Security status of a device (patched, encrypted, etc.)
- **Zero Trust:** Security model assuming no implicit trust
- **MFA:** Multi-Factor Authentication using 2+ verification methods

---

## Appendix B: Quick Reference Checklist

**Remote Worker Startup Checklist:**

- [ ] Enable MFA on all accounts
- [ ] Set up VPN client and test connection
- [ ] Enable full-disk encryption
- [ ] Install and enable antivirus software
- [ ] Enable firewall
- [ ] Register device in MDM system
- [ ] Review and acknowledge security policy
- [ ] Configure password manager
- [ ] Set automatic screen lock (15 minutes)
- [ ] Disable USB external drives (if sensitive data access)
- [ ] Install latest OS and application patches

---

**Document Version:** 1.0  
**Last Updated:** January 7, 2026  
**Next Review:** January 2027

