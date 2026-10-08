# Active Directory Basics

TryHackMe room covering the fundamental concepts of Active Directory, Windows domains, users, computers, Group Policy, authentication, trees, forests and trust relationships.

## Learning Objectives

* Understand the basics of Active Directory
* Understand Windows domains and Domain Controllers
* Learn how users, computers, groups and Organizational Units are managed
* Understand Group Policy Objects (GPOs)
* Learn about Kerberos and NetNTLM authentication
* Understand Active Directory trees and forests
* Understand trust relationships between domains

---

## Task 2: Windows Domains

A Windows domain is a group of users and computers managed by an organization.

The central repository used to store domain credentials and other information is Active Directory.

The server responsible for running Active Directory services is called a Domain Controller (DC).

### Answers

1. In a Windows domain, credentials are stored in a centralised repository called:

```text
Active Directory
```

2. The server in charge of running the Active Directory services is called:

```text
Domain Controller
```

---

## Task 3: Active Directory

Active Directory Domain Services (AD DS) stores information about objects in the network, including users, computers and security groups.

### Important Concepts

* Security Groups are used to assign permissions to resources.
* Organizational Units (OUs) are used to organize objects and apply policies.
* Machine accounts normally end with a `$`, such as `DC01$`.
* A user can belong to multiple security groups.
* A user can only belong to one OU at a time.

### Common Groups

Some default Active Directory groups include:

* Domain Admins
* Server Operators
* Backup Operators
* Account Operators
* Domain Users
* Domain Computers
* Domain Controllers

### Answers

1. Which group normally administrates all computers and resources in a domain?

```text
Domain Admins
```

2. What would be the name of the machine account associated with a machine named TOM-PC?

```text
TOM-PC$
```

3. What type of containers should be used to group Quality Assurance users so policies can be applied consistently?

```text
Organizational Units (OUs)
```

---

## Task 4: Managing Users in AD

Active Directory allows administrators to organize users into OUs and delegate administrative permissions.

OUs can also be protected against accidental deletion. Advanced Features can be enabled in Active Directory Users and Computers to manage this protection.

### Delegation

Delegation allows specific users to manage parts of Active Directory without giving them full Domain Administrator privileges.

For example, an IT support user can be delegated permission to reset passwords for users inside a specific OU.

### PowerShell

A delegated administrator can reset a user's password with:

```powershell
Set-ADAccountPassword sophie -Reset -NewPassword (Read-Host -AsSecureString -Prompt 'New Password') -Verbose
```

The user can then be required to change the password at the next login:

```powershell
Set-ADUser -ChangePasswordAtLogon $true -Identity sophie -Verbose
```

### Answer

What is the process of granting privileges to a user over some OU or other AD Object called?

```text
Delegation
```

---

## Task 5: Managing Computers in AD

When a computer joins a domain, it is normally placed in the default `Computers` container unless another OU is specified.

It is recommended to organize computers into separate OUs depending on their role.

A common structure is:

```text
Domain
├── Workstations
├── Servers
└── Domain Controllers
```

This makes it easier to apply different policies to different types of machines.

### Answers

1. After organising the available computers, how many ended up in the Workstations OU?

```text
7
```

2. Is it recommendable to create separate OUs for Servers and Workstations?

```text
yay
```

---

## Task 6: Group Policies

Group Policy Objects (GPOs) are collections of settings that can be applied to users and computers.

GPOs can contain:

* User Configuration
* Computer Configuration

GPOs can be linked to domains or OUs and can be inherited by child OUs.

### SYSVOL

The `SYSVOL` share is used to distribute Group Policy files to domain machines.

The local SYSVOL directory is located under:

```text
C:\Windows\SYSVOL\sysvol\
```

To force a machine to update its Group Policy:

```cmd
gpupdate /force
```

### Answers

1. What is the name of the network share used to distribute GPOs to domain machines?

```text
SYSVOL
```

2. Can a GPO be used to apply settings to users and computers?

```text
yay
```

---

## Task 7: Authentication Methods

Windows domains can use different authentication protocols.

Modern Windows environments primarily use Kerberos, while NetNTLM is a legacy authentication method.

### Kerberos

Kerberos uses tickets to authenticate users to services.

The basic process is:

```text
User
  |
  v
KDC
  |
  v
TGT
  |
  v
TGS
  |
  v
Service
```

The TGT (Ticket Granting Ticket) allows the user to request additional service tickets called TGS (Ticket Granting Service) tickets.

### NetNTLM

NetNTLM uses a challenge-response mechanism.

The user's password is not directly transmitted across the network.

### Answers

1. Will a current version of Windows use NetNTLM as the preferred authentication protocol by default?

```text
nay
```

2. When referring to Kerberos, what type of ticket allows us to request further tickets known as TGS?

```text
TGT
```

3. When using NetNTLM, is a user's password transmitted over the network at any point?

```text
nay
```

---

## Task 8: Trees, Forests and Trusts

As organizations grow, they may need multiple domains.

### Trees

A Tree is a group of Windows domains that share the same namespace.

For example:

```text
thm.local
├── uk.thm.local
└── us.thm.local
```

These domains belong to the same tree.

### Enterprise Admins

The Enterprise Admins group provides administrative privileges across all domains in an enterprise.

Domain Admins, on the other hand, have administrative privileges within their specific domain.

### Forests

A Forest is a collection of multiple domain trees that use different namespaces.

For example:

```text
THM
├── thm.local
│   ├── uk.thm.local
│   └── us.thm.local
│
└── mht.local
    ├── eu.mht.local
    └── asia.mht.local
```

### Trust Relationships

Trust relationships allow users from one domain to be authorized to access resources in another domain.

For example:

```text
Domain A
   |
   | Trust
   v
Domain B
```

A one-way trust means that one domain trusts another domain for authentication and authorization purposes.

A trust relationship does not automatically give users access to every resource. Permissions still need to be configured.

### Answers

1. What is a group of Windows domains that share the same namespace called?

```text
Tree
```

2. What should be configured between two domains for a user in Domain A to access a resource in Domain B?

```text
A Trust Relationship
```

---

## Key Takeaways

* Active Directory is Microsoft's directory service for managing users, computers and resources.
* A Domain Controller runs Active Directory services.
* Domain Admins have administrative privileges over a domain.
* OUs organize objects and allow policies to be applied.
* Security Groups are primarily used for permissions.
* GPOs allow administrators to centrally configure users and computers.
* SYSVOL distributes Group Policy files.
* Kerberos is the preferred authentication protocol in modern Windows domains.
* TGT is used to request TGS tickets.
* NetNTLM uses a challenge-response mechanism and does not transmit the user's password directly.
* A Tree contains domains that share a namespace.
* A Forest contains multiple domain trees.
* Trust relationships allow authentication and authorization between domains.

---

## Conclusion

This room introduced the fundamental concepts behind Active Directory and Windows domains.

Understanding domains, Domain Controllers, OUs, groups, GPOs, authentication protocols, trees, forests and trust relationships provides a foundation for learning how Active Directory is administered, secured and attacked.

The next step is to explore Active Directory security, common misconfigurations and attack techniques in more depth.
