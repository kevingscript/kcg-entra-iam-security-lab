# Microsoft Entra ID | Identity & Access Management Security Lab

**KCG Technology | Cybersecurity Portfolio Project #002**

## Project Overview

This project documents a hands-on Identity and Access Management (IAM) security lab conducted in Microsoft Entra ID. The objective was to gain practical experience administering cloud identities, managing privileged access, investigating authentication activity, and evaluating identity security controls.

Using a controlled environment with dedicated test accounts and security groups, I performed identity administration, role-based access control (RBAC), Microsoft Authenticator registration, directory audit investigations, and sign-in log analysis.

A key part of this project involved investigating a successful single-factor sign-in despite Microsoft Authenticator being registered and Security Defaults being enabled. I documented the observation as a low-severity security finding requiring further validation, rather than assuming a security compromise had occurred.

The lab also explored the capabilities and limitations of Microsoft Entra ID Free, including the licensing requirements for advanced identity security features.

**Project Status:** Completed lab exercises; MFA enforcement validation remains open.

**Platform:** Microsoft Entra ID Free

**Documentation:** [View Technical Walkthrough](docs/technical-walkthrough.md)

## Technologies & Skills

- Microsoft Entra ID
- Identity and Access Management (IAM)
- Role-Based Access Control (RBAC)
- Microsoft Authenticator
- Multifactor Authentication (MFA)
- Microsoft Entra Audit Logs
- Microsoft Entra Sign-in Logs
- Security Defaults
- Principle of Least Privilege
- Security Investigation and Documentation

## Project Highlights

- Created and managed test identities representing IT, Human Resources, and Finance departments.
- Organized departmental identities using Microsoft Entra security groups.
- Assigned and revoked the Password Administrator directory role to demonstrate least-privilege access management.
- Investigated administrative changes using Microsoft Entra Audit Logs.
- Registered and verified Microsoft Authenticator for a test identity.
- Analyzed authentication activity and identified a successful single-factor sign-in requiring further MFA enforcement validation.
- Verified that Security Defaults were enabled and assessed Microsoft Entra ID Free licensing limitations.
- Documented security finding **KCG-IAM-001**, including the observation, potential risk, recommended action, and validation status.

## Supporting Evidence

The following screenshots document the identity administration, privileged access management, authentication investigation, and security assessment activities completed during this lab.

| Evidence | Description |
|---|---|
| [RBAC Role Assignment](docs/evidence/KCG-IAM-RBAC-Role-Assignment.png) | Password Administrator role assigned to the test identity. |
| [RBAC Role Revocation](docs/evidence/KCG-IAM-RBAC-Role-Revocation.png) | Verification that the privileged directory role was removed. |
| [Audit Log Modified Properties](docs/evidence/KCG-IAM-Audit-Modified-Properties.png) | Audit record details showing role-related properties. |
| [Audit Log Targets](docs/evidence/KCG-IAM-Audit-Targets.png) | Target identity and role information associated with the audit event. |
| [Microsoft Authenticator Registration](docs/evidence/KCG-IAM-MFA-Authenticator-Registration.png) | Registered authentication method and default sign-in configuration. |
| [Single-Factor Authentication Investigation](docs/evidence/KCG-IAM-SignIn-Single-Factor-Authentication.png) | Successful sign-in recorded with a single-factor authentication requirement. |
| [Security Defaults Configuration](docs/evidence/KCG-IAM-Security-Defaults-Enabled.png) | Confirmation that Microsoft Entra Security Defaults were enabled. |
| [Licensing Assessment](docs/evidence/KCG-IAM-Licensing-Assessment.png) | Tenant licensing information used to assess premium feature availability. |
