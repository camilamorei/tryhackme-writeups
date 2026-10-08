# Windows Fundamentals 3

This room covers several built-in Windows security features and tools designed to help protect the operating system.

## Topics Covered

* Windows Update
* Windows Security
* Virus & threat protection
* Firewall & network protection
* App & browser control
* Device security
* Trusted Platform Module (TPM)
* BitLocker
* Volume Shadow Copy Service (VSS)
* Living Off The Land

## Windows Update

Windows Update provides security updates, feature enhancements, and patches for Windows and other Microsoft products.

Updates are typically released on the second Tuesday of each month, known as Patch Tuesday. Critical updates can also be released outside of this schedule when necessary.

The Windows Update settings can be accessed using:

```text
control /name Microsoft.WindowsUpdate
```

Two definition updates were installed on:

```text
5/3/2021
```

## Windows Security

Windows Security provides several built-in security features.

The main protection areas are:

* Virus & threat protection
* Firewall & network protection
* App & browser control
* Device security

The status icons indicate the security state:

* Green - No recommended actions
* Yellow - A security recommendation needs review
* Red - Immediate attention is required

The area requiring immediate attention in the lab was:

```text
Virus & threat protection
```

## Virus & Threat Protection

Virus & threat protection provides antivirus and malware protection through Microsoft Defender.

### Scan Options

* Quick scan
* Full scan
* Custom scan

### Threat History

* Last scan
* Quarantined threats
* Allowed threats

### Protection Settings

Important settings include:

* Real-time protection
* Cloud-delivered protection
* Automatic sample submission
* Controlled folder access
* Exclusions
* Notifications

The setting that was turned off in the lab was:

```text
Real-time protection
```

Real-time protection should normally remain enabled on personal Windows devices unless another security product provides equivalent protection.

## Firewall & Network Protection

A firewall controls network traffic entering and leaving a device through network ports.

Windows Firewall provides three firewall profiles:

* Domain
* Private
* Public

The three profiles are used for different types of networks.

For example, airport Wi-Fi would use the:

```text
Public network
```

The Windows Defender Firewall can be opened with:

```text
WF.msc
```

## App & Browser Control

App & browser control includes Microsoft Defender SmartScreen and exploit protection.

Microsoft Defender SmartScreen helps protect against:

* Phishing websites
* Malware websites
* Malicious applications
* Potentially malicious downloads

SmartScreen can be configured to warn or block potentially dangerous content.

Exploit protection is another built-in Windows security feature designed to help protect the system against attacks that attempt to exploit vulnerabilities.

## Device Security

Device security includes hardware-based and system-level security features.

### Core Isolation

Memory Integrity helps prevent malicious code from being inserted into high-security processes.

### Trusted Platform Module

TPM stands for:

```text
Trusted Platform Module
```

A TPM is a hardware-based security component designed to perform cryptographic operations and provide additional protection against tampering.

## BitLocker

BitLocker is a Windows data protection feature designed to protect data from theft or exposure if a computer is lost, stolen, or improperly decommissioned.

BitLocker provides stronger protection when used with a TPM.

On systems without a TPM version 1.2 or later, a removable USB drive can be used during startup. The removable drive contains a:

```text
Startup key
```

## Volume Shadow Copy Service

VSS stands for:

```text
Volume Shadow Copy Service
```

VSS creates consistent point-in-time copies of data that can be used for backups and system recovery.

Volume Shadow Copies are stored in the `System Volume Information` folder on drives where protection is enabled.

VSS can be used to:

* Create restore points
* Perform system restores
* Configure restore settings
* Delete restore points

From a security perspective, attackers and malware can attempt to delete Shadow Copies to prevent victims from recovering files after attacks such as ransomware.

## Living Off The Land

Attackers can abuse legitimate Windows tools and utilities to perform malicious activities while attempting to avoid detection.

This technique is known as:

```text
Living Off The Land
```

Understanding legitimate Windows utilities is therefore important for both system administration and cybersecurity.

## Key Takeaways

This room introduced several important Windows security mechanisms, including:

* Windows Update
* Microsoft Defender
* Windows Firewall
* SmartScreen
* Exploit protection
* TPM
* BitLocker
* Volume Shadow Copy Service

Understanding these built-in security features is useful for both defensive security and understanding how attackers may abuse legitimate Windows functionality.
