
# Security Principles

## Overview

This room introduces fundamental information security principles, including the CIA triad, the DAD triad, security models, Defence-in-Depth, Zero Trust, and the differences between vulnerabilities, threats, and risks.

## Learning Objectives

- Understand the CIA triad and the DAD triad.
- Learn about authenticity, nonrepudiation, and the Parkerian Hexad.
- Understand Defence-in-Depth.
- Explore ISO/IEC 19249 architectural and design principles.
- Compare Zero Trust with Trust but Verify.
- Distinguish between vulnerabilities, threats, and risks.
- Understand the Shared Responsibility Model in cloud security.

## Task 1: Introduction

Perfect security is impossible. Security controls should be selected according to the assets being protected and the capabilities of potential adversaries.

The objective is to reduce the likelihood and impact of successful attacks by implementing appropriate security measures.

## Task 2: CIA Triad

The CIA triad consists of three fundamental security principles.

### Confidentiality

Confidentiality ensures that information is accessible only to authorized individuals and systems.

Examples include access controls, encryption, and authentication.

### Integrity

Integrity ensures that information remains accurate and complete and that unauthorized modifications can be detected.

Examples include cryptographic hashes, digital signatures, and file integrity monitoring.

### Availability

Availability ensures that systems and information remain accessible when needed.

Examples include backups, redundant infrastructure, and protection against denial-of-service attacks.

### Beyond CIA

Authenticity ensures that information or a message comes from the claimed source.

Nonrepudiation provides evidence that supports the validity of an action or transaction and helps prevent a party from denying their involvement.

### Parkerian Hexad

The Parkerian Hexad expands the traditional CIA triad into six security elements:

1. Availability
2. Utility
3. Integrity
4. Authenticity
5. Confidentiality
6. Possession

Utility concerns whether information is useful and accessible in a meaningful form.

Possession concerns control over information or the medium on which it is stored.

### Task 2 Answer

Flag: `THM{CIA_TRIAD}`

## Task 3: DAD Triad

The DAD triad describes three types of security attacks that oppose the CIA triad.

### Disclosure

Disclosure occurs when confidential information is exposed to unauthorized parties. It compromises confidentiality.

### Alteration

Alteration occurs when information is modified without authorization. It compromises integrity.

### Destruction or Denial

Destruction or denial occurs when information or services are destroyed or made unavailable. It compromises availability.

### CIA and DAD Relationship

| Security Principle | Opposing Attack |
|---|---|
| Confidentiality | Disclosure |
| Integrity | Alteration |
| Availability | Destruction or Denial |

### Task 3 Answers

1. Customer records accessed and published online: `Disclosure`
2. Main and backup power supplies disabled, shutting down the network: `Destruction/Denial`

## Task 4: Security Models

Security models provide formal concepts and rules for enforcing security policies.

The Bell-LaPadula model focuses on confidentiality in systems that handle information at different classification levels.

Security models help define how information can be accessed and how security policies should be enforced.

### Task 4 Answer

Flag: `THM{SECURITY_MODELS}`

## Task 5: Defence-in-Depth

Defence-in-Depth uses multiple layers of security to protect systems and information.

Instead of relying on a single security control, organizations combine measures such as physical security, authentication, firewalls, endpoint protection, network segmentation, and monitoring.

If one control fails, additional controls may prevent or limit an attack.

## Task 6: ISO/IEC 19249

ISO/IEC 19249:2017 describes architectural and design principles for secure products, systems, and applications.

### Architectural Principles

1. Domain Separation

   Groups related components into separate security domains with appropriate security attributes.

2. Layering

   Organizes a system into layers so that security policies can be applied and validated at different levels.

3. Encapsulation

   Restricts direct access to internal implementation details and provides controlled interfaces for interacting with data and components.

4. Redundancy

   Provides alternative components or resources to improve availability and help maintain integrity.

5. Virtualization

   Uses virtual environments to isolate workloads and establish additional security boundaries.

### Design Principles

1. Least Privilege

   Grants users and processes only the permissions required to perform their tasks.

2. Attack Surface Minimisation

   Reduces potential entry points by disabling unnecessary services, removing unused software, and limiting exposed functionality.

3. Centralized Parameter Validation

   Validates input through a consistent mechanism to reduce the risk of invalid or malicious data.

4. Centralized General Security Services

   Uses shared security services, such as centralized authentication, to improve consistency and management.

5. Preparing for Error and Exception Handling

   Designs systems to handle failures safely without exposing sensitive information or allowing insecure behavior.

### Task 6 Answers

1. Turning off an insecure, non-critical server: `2` (Attack Surface Minimisation)
2. Giving a new sales representative access only to products and prices: `1` (Least Privilege)
3. Preparing an ATM to handle network disconnections and power failures: `5` (Preparing for Error and Exception Handling)

## Task 7: Zero Trust versus Trust but Verify

### Trust but Verify

Trust but Verify assumes that an entity may be trusted but that its actions should still be checked.

Logging, monitoring, and automated security controls help identify unusual activity and verify that systems behave as expected.

### Zero Trust

Zero Trust follows the principle of never trusting an entity automatically.

Every access request must be evaluated according to authentication, authorization, and applicable security policies.

Trust is not granted solely because a user or device belongs to an organization or connects from its internal network.

### Microsegmentation

Microsegmentation divides a network into small security segments. Access between segments is controlled to limit unauthorized movement and reduce the impact of a compromise.

## Task 8: Threat versus Risk

### Vulnerability

A vulnerability is a weakness in a system, application, configuration, or process that could be exploited.

### Threat

A threat is a potential cause of harm that may exploit a vulnerability.

### Risk

Risk considers the likelihood that a threat will exploit a vulnerability and the resulting impact on an organization.

### Example

A database with an unpatched vulnerability has a weakness that could be exploited.

- Vulnerability: The unpatched database software.
- Threat: An attacker attempting to exploit the weakness.
- Risk: The likelihood and business impact of a successful attack.

## Task 9: Conclusion

This room introduced fundamental security principles and models used to protect information systems.

The CIA triad describes confidentiality, integrity, and availability. The DAD triad describes disclosure, alteration, and destruction or denial.

Defence-in-Depth uses multiple security layers, while Zero Trust requires access to be verified rather than automatically trusted. ISO/IEC 19249 presents architectural and design principles that help developers and security professionals build more secure systems.

Understanding vulnerabilities, threats, and risks helps organizations prioritize security controls according to their potential impact.

### Shared Responsibility Model

Cloud security responsibilities are shared between the cloud provider and the customer. The exact division depends on the service model.

- Infrastructure as a Service (IaaS): The customer manages more of the operating system and software environment.
- Platform as a Service (PaaS): The provider manages the underlying platform, while the customer remains responsible for their applications and data.
- Software as a Service (SaaS): The provider manages most of the underlying infrastructure and application platform, while the customer remains responsible for aspects such as account access, data, and configuration.

## Key Terms

- CIA: Confidentiality, Integrity, Availability
- DAD: Disclosure, Alteration, Destruction or Denial
- Zero Trust: A security approach that verifies every access request
- Defence-in-Depth: Multiple layers of security controls
- Least Privilege: Granting only the permissions necessary
- Vulnerability: A weakness that may be exploited
- Threat: A potential cause of harm
- Risk: The likelihood and impact of a threat exploiting a vulnerability
- Authenticity: Assurance that information comes from its claimed source
- Nonrepudiation: Evidence supporting the validity of an action or transaction
- ISO/IEC 19249: A standard describing security architectural and design principles
- Shared Responsibility Model: Division of security responsibilities between cloud providers and customers

## Status

Completed
