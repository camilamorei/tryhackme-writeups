
# OWASP Top 10 2025: Application Design Flaws

## Overview

This room explores four categories from the OWASP Top 10 2025 related to security architecture, configuration, cryptography, and application design.

The categories covered are:

- A02: Security Misconfigurations
- A03: Software Supply Chain Failures
- A04: Cryptographic Failures
- A06: Insecure Design

## Task 1: Introduction

The room introduces common security weaknesses caused by insecure configurations, vulnerable dependencies, incorrect cryptographic practices, and flawed application architecture.

## Task 2: A02 Security Misconfigurations

Security misconfigurations occur when systems or applications are deployed with unsafe defaults, exposed services, or incorrect permissions.

Common examples include:

- Default credentials left unchanged.
- Exposed administrative interfaces and endpoints.
- Incorrect cloud storage permissions.
- Missing authentication or authorisation.
- Verbose error messages that reveal internal details.
- Outdated software and insecure configurations.

### Challenge

The application exposes a User Management API on port 5002. Investigating the API can reveal information exposed through improper configuration and verbose errors.

### Answer

Flag: `THM{V3RB0S3_3RR0R_L34K}`

## Task 3: A03 Software Supply Chain Failures

Software supply chain failures occur when an application depends on vulnerable, compromised, outdated, or unverified third-party components.

Common examples include:

- Using outdated libraries and dependencies.
- Installing unverified software updates.
- Insecure build and deployment pipelines.
- Missing dependency monitoring.
- Using third-party components without verifying their integrity.

### Challenge

The application on port 5003 imports an outdated component named `lib/vulnerable_utils.py`. Investigating the dependency helps identify weaknesses introduced by vulnerable software components.

### Answer

Flag: `THM{SUPPLY_CH41N_VULN3R4B1L1TY}`

## Task 4: A04 Cryptographic Failures

Cryptographic failures occur when sensitive information is not adequately protected due to weak algorithms, hard-coded secrets, or incorrect encryption practices.

Common examples include:

- Using deprecated cryptographic algorithms.
- Hard-coding encryption keys.
- Poor key management and rotation.
- Transmitting sensitive information without encryption.
- Using invalid TLS certificates.

### Challenge

The application on port 5004 contains a cryptographic weakness. The objective is to identify the key needed to decrypt a file and retrieve the flag.

### Answer

Flag: `THM{CRYPTO_FAILURE_H4RDCOD3D_K3Y}`

## Task 5: A06 Insecure Design

Insecure Design occurs when security weaknesses originate from flawed requirements, assumptions, workflows, or architecture.

Common examples include:

- Missing threat modelling.
- Weak business logic controls.
- Inadequate authentication and authorisation.
- Excessive privileges granted to users or services.
- Trusting client-side restrictions instead of enforcing server-side controls.
- AI systems that accept untrusted input without proper validation.

### Challenge

The application on port 5005 assumes that users can access it only through mobile devices. Testing the application outside that expected environment helps identify weaknesses in this assumption.

### Answer

Flag: `THM{1NS3CUR3_D35IGN_4SSUMPT10N}`

## Task 6: Conclusion

Security design failures often result from weak foundations established during development and deployment.

Key lessons:

- Security Misconfigurations: Use secure defaults, restrict exposed services, and audit permissions.
- Software Supply Chain Failures: Verify dependencies, monitor vulnerabilities, and secure build pipelines.
- Cryptographic Failures: Use modern cryptographic algorithms and protect encryption keys.
- Insecure Design: Define security requirements early, perform threat modelling, and enforce security controls on the server.

Security must be considered throughout the software development lifecycle rather than added only after an application has been built.

## Key Terms

- Security Misconfiguration: An unsafe system or application configuration.
- Software Supply Chain: The components, libraries, tools, and processes used to build and distribute software.
- Cryptographic Failure: A weakness in the protection of sensitive information through cryptography.
- Insecure Design: A weakness caused by flawed application architecture or business logic.
- Threat Modelling: Identifying potential threats and designing controls to reduce risk.
- Least Privilege: Granting only the permissions required for a task.
- Dependency Management: Tracking, verifying, and maintaining external software components.

## Status

Completed
