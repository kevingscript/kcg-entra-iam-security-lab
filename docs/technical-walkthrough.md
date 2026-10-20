# Microsoft Entra ID | Identity & Access Management Security Lab

## 1. Project Overview

This project documents a hands-on Identity and Access Management (IAM) security lab conducted in Microsoft Entra ID. The objective was to develop practical experience managing cloud identities, controlling privileged access, investigating authentication activity, and evaluating identity security configurations.

The lab simulated common IT administration and security operations using dedicated test accounts and security groups. Activities included user and group management, role-based access control (RBAC), Microsoft Authenticator registration, directory audit investigations, and sign-in log analysis.

A key focus was applying the principle of least privilege and distinguishing between configured security controls and verified authentication behavior.

The investigation identified a successful single-factor sign-in despite Microsoft Authenticator being registered and Security Defaults being enabled. This observation was documented as a low-severity finding requiring further validation, rather than evidence of a confirmed security compromise.

The project also assessed the capabilities and limitations of Microsoft Entra ID Free, including restrictions on premium identity protection and Conditional Access features.

### Project Objectives

- Practice cloud identity and security group administration.
- Demonstrate privileged role assignment and revocation.
- Investigate directory changes through Microsoft Entra Audit Logs.
- Register and verify Microsoft Authenticator as an available authentication method.
- Analyze authentication requirements and outcomes using Sign-in Logs.
- Evaluate Security Defaults and identify areas requiring additional validation.
- Document security findings and licensing limitations using evidence-based reporting.

## 2. Lab Environment

### Platform and Licensing

The lab was conducted in a Microsoft Entra ID tenant using the Microsoft Entra ID Free licensing tier. Administrative tasks were performed through the Microsoft Entra admin center.

The environment supported identity administration, security group management, directory role assignments, authentication method registration, and audit and sign-in log investigations.

No Microsoft Entra ID P1 or P2 licenses were available. As a result, premium features such as Conditional Access policies, Privileged Identity Management (PIM), Identity Protection, and Access Reviews were outside the scope of hands-on configuration.

### Test Identities

The lab used dedicated test identities to simulate departmental access requirements.

| Test Identity | Department | Purpose |
|---|---|---|
| Jordan Mitchell | IT | RBAC testing, MFA registration, and authentication investigation |
| Taylor Brooks | Human Resources | Departmental identity and group administration |
| Morgan Ellis | Finance | Departmental identity and group administration |
| Administrative account | Administration | Tenant configuration and security investigation |
| External guest | External | Guest identity management practice |

### Security Groups

Three department-based security groups were used to organize identities and practice group administration.

- `SG-KCG-IT`
- `SG-KCG-HR`
- `SG-KCG-FINANCE`

### Security Configuration

Microsoft Security Defaults were enabled in the tenant.

Microsoft Authenticator was registered as an authentication method for the IT test identity. The lab distinguished successful method registration from evidence of an actual multifactor authentication challenge.

Security monitoring and investigation activities used Microsoft Entra Audit Logs and Sign-in Logs.

### Environment Scope

All administrative and investigative activities were performed within a controlled learning environment using test identities.

The project did not involve a production security incident or confirmed account compromise.

## 3. Identity and Security Group Administration

### Objective

Practice managing cloud identities and organizing user access through department-based security groups in Microsoft Entra ID.

### Identity Management

Created and managed dedicated test identities representing IT, Human Resources, and Finance departments.

The test identities provided a controlled environment for practicing user administration, role assignments, authentication configuration, and security investigations without affecting production users.

An external guest identity was also included to explore identity management beyond internal organizational accounts.

### Security Group Administration

Created and managed three department-based security groups:

- `SG-KCG-IT`
- `SG-KCG-HR`
- `SG-KCG-FINANCE`

These groups provided a foundation for organizing departmental identities and practicing group-based access administration.

### Security Considerations

Department-based security groups help administrators organize access according to business responsibilities.

This lab emphasized the principle of least privilege, where users should receive only the access necessary to perform their assigned tasks.

Group membership alone does not establish that access restrictions are correctly enforced. Effective access control also requires appropriate permissions, resource assignments, and validation.

### Outcome

Established a controlled identity administration environment with departmental test accounts and security groups.

The environment supported subsequent exercises involving privileged role management, authentication methods, and audit investigations.

## 4. Role-Based Access Control (RBAC)

### Objective

Demonstrate the administration of privileged directory roles in Microsoft Entra ID while applying the principle of least privilege.

### Role Assignment

Selected the IT test identity, Jordan Mitchell, and temporarily assigned the built-in **Password Administrator** directory role.

This role provides delegated password management capabilities for supported user accounts, allowing administrators to perform password-related tasks without receiving unrestricted tenant administration privileges.

After assigning the role, reviewed the user's Assigned Roles page to verify that the Password Administrator role was present.

### Role Revocation

After completing the administrative exercise, removed the Password Administrator role from the test identity.

Returned to the user's Assigned Roles page and confirmed that no directory roles remained assigned.

This demonstrated the importance of removing elevated permissions when they are no longer required.

### Audit Verification

Reviewed Microsoft Entra Audit Logs to investigate the privileged role changes.

The audit records confirmed successful role assignment and removal operations. Examined the event details, including the target identity and modified role properties, to understand how Microsoft Entra ID records administrative changes.

### Security Considerations

Privileged roles should be assigned only when necessary and removed when their intended purpose has been completed.

Temporary role assignment reduces unnecessary exposure to elevated permissions. Audit logging provides supporting evidence that administrative changes occurred and helps investigators reconstruct identity-related activity.

Although Privileged Identity Management (PIM) offers additional capabilities for managing privileged access, it was not available under the tenant's Microsoft Entra ID Free licensing tier.

### Outcome

Successfully assigned and revoked the Password Administrator role, verified the resulting access state, and investigated the associated audit records.

### Supporting Evidence

- [Password Administrator Role Assignment](evidence/KCG-IAM-RBAC-Role-Assignment.png)
- [Password Administrator Role Revocation](evidence/KCG-IAM-RBAC-Role-Revocation.png)
- [Audit Log Modified Properties](evidence/KCG-IAM-Audit-Modified-Properties.png)
- [Audit Log Targets](evidence/KCG-IAM-Audit-Targets.png)

## 5. Microsoft Authenticator and MFA Registration

### Objective

Configure and verify Microsoft Authenticator as an available authentication method for a test identity in Microsoft Entra ID.

### Authentication Method Configuration

Reviewed the Microsoft Entra ID authentication method settings to understand how Microsoft Authenticator is made available to users.

The Microsoft Authenticator authentication method was enabled for all users, with number matching enabled.

This configuration supports the use of Microsoft Authenticator for multifactor authentication when an appropriate authentication challenge is required.

### Authenticator Registration

Registered Microsoft Authenticator for the IT test identity, Jordan Mitchell, using an iPhone 15 Pro Max.

Completed the registration process and returned to the user's Authentication Methods page to verify that Microsoft Authenticator appeared as a usable authentication method.

### Registration Verification

Confirmed the following configuration details:

- **Registered authentication method:** Microsoft Authenticator
- **Registered device:** iPhone 15 Pro Max
- **Default sign-in method:** Microsoft Authenticator notification
- **System-preferred MFA method:** PhoneAppNotification
- **System-preferred MFA feature status:** Enabled

The successful registration confirmed that the test identity had an available Microsoft Authenticator method.

### Security Considerations

Microsoft Authenticator provides an additional authentication method that can support stronger identity security.

However, authentication method registration and MFA enforcement are separate security concepts.

A registered authenticator does not establish that every sign-in requires multifactor authentication or that a particular sign-in successfully completed an MFA challenge.

Actual authentication requirements and results must be evaluated through Microsoft Entra Sign-in Logs.

### Outcome

Successfully registered Microsoft Authenticator for the IT test identity and verified its availability through the Microsoft Entra admin center.

The registered method provided a foundation for subsequent authentication log analysis and MFA enforcement validation.

### Supporting Evidence

- [Microsoft Authenticator Registration](evidence/KCG-IAM-MFA-Authenticator-Registration.png)

## 6. Sign-in Logs and Authentication Investigation

### Objective

Investigate Microsoft Entra ID authentication activity to determine the authentication requirements and results associated with a test user's sign-in.

### Investigation Process

Accessed Microsoft Entra ID Sign-in Logs for the IT test identity, Jordan Mitchell.

Reviewed the available sign-in activity and opened the details of a successful interactive sign-in.

Examined the Basic Info and Authentication Details tabs to understand how the authentication event was processed.

### Authentication Findings

The investigated sign-in displayed the following results:

- **Test identity:** Jordan Mitchell
- **Sign-in status:** Success
- **Authentication requirement:** Single-factor authentication
- **Authentication result:** Successful password authentication
- **Microsoft Authenticator registration:** Confirmed
- **Security Defaults:** Enabled

Although Microsoft Authenticator was registered as an available authentication method, the investigated sign-in did not demonstrate a completed multifactor authentication challenge.

### Security Analysis

This investigation demonstrated the importance of distinguishing authentication method availability from authentication enforcement.

Microsoft Entra ID Security Defaults were enabled, but this does not establish that every successful sign-in must receive an MFA challenge.

The observed single-factor sign-in was therefore documented as an authentication enforcement validation concern rather than evidence of a confirmed security compromise.

Additional controlled sign-in testing would be required to determine whether and when MFA challenges are enforced for the test identity.

### Security Finding

**Finding ID:** KCG-IAM-001

**Title:** MFA Enforcement Requires Validation

**Severity:** Low

**Status:** Open, pending validation

**Observation:** A successful sign-in was recorded with a single-factor authentication requirement despite Microsoft Authenticator being registered and Security Defaults being enabled.

**Potential Risk:** Without validating authentication enforcement, administrators may incorrectly assume that the presence of a registered authentication method guarantees MFA protection for every sign-in.

**Recommended Action:** Conduct a controlled authentication test and review the resulting Microsoft Entra Sign-in Logs to determine whether an MFA challenge was required and successfully completed.

### Outcome

Successfully investigated authentication activity using Microsoft Entra Sign-in Logs.

Identified and documented a single-factor authentication observation requiring additional validation.

The exercise strengthened practical skills in authentication log analysis, security investigation, and evidence-based reporting.

### Supporting Evidence

- [Single-Factor Authentication Sign-in](evidence/KCG-IAM-SignIn-Single-Factor-Authentication.png)
