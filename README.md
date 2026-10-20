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
