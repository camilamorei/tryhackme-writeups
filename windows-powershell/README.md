# Windows PowerShell

## Introduction

This room introduces PowerShell, Microsoft's task automation and configuration management framework. It covers basic PowerShell syntax, file system navigation, data filtering, system and network information gathering, and basic scripting concepts.

PowerShell is especially useful in cybersecurity because it can automate administrative tasks, collect system information, analyze processes and network connections, and execute commands remotely.

## Task 1: Introduction

PowerShell is a cross-platform task automation solution that consists of:

* A command-line shell
* A scripting language
* A configuration management framework

The room covers the fundamentals of PowerShell and its applications in cybersecurity.

Prerequisites include the Windows and AD Fundamentals module and the Windows Command Line room.

## Task 2: What is PowerShell?

PowerShell was developed to address limitations of the traditional Windows command shell and batch scripting.

Unlike traditional command shells that mainly work with text, PowerShell uses an object-oriented approach. Cmdlets return objects containing properties and methods, allowing the output of one command to be processed by another command more effectively.

PowerShell was initially released as a Windows-only tool in 2006. PowerShell Core was later released as an open-source and cross-platform version, allowing PowerShell to run on Windows, macOS, and Linux.

### Basic Concepts

PowerShell commands are commonly called cmdlets and follow a Verb-Noun naming convention.

Examples:

```powershell
Get-Content
Set-Location
Get-Command
Get-Help
Get-Alias
```

### Question

What do we call the advanced approach used to develop PowerShell?

```text
Object-oriented
```

## Task 3: PowerShell Basics

PowerShell can be launched from the Windows Command Prompt by typing:

```powershell
powershell
```

Once PowerShell is running, the prompt changes to indicate that PowerShell is being used.

Example:

```text
PS C:\Users\captain>
```

The `PS` prefix indicates that the current shell is PowerShell.

### Cmdlets

PowerShell cmdlets follow the Verb-Noun naming convention.

For example:

```powershell
Get-Content
Set-Location
Get-Command
```

`Get-Command` can be used to retrieve available commands.

```powershell
Get-Command
```

It can also be filtered by command type or verb.

For example:

```powershell
Get-Command -Verb Remove
```

`Get-Help` provides information about cmdlets, including examples and parameters.

```powershell
Get-Help Get-Date -Examples
```

`Get-Alias` can be used to view aliases for PowerShell commands.

For example:

```powershell
Get-Alias
```

Some common aliases include:

```text
dir -> Get-ChildItem
cd  -> Set-Location
```

### Questions

How would you retrieve a list of commands that start with the verb `Remove`?

```powershell
Get-Command -Name Remove*
```

What cmdlet has its traditional counterpart `echo` as an alias?

```text
Write-Output
```

What is the command to retrieve some example usage for `New-LocalUser`?

```powershell
Get-Help New-LocalUser -Examples
```

## Task 4: Navigating the File System and Working with Files

PowerShell provides cmdlets for navigating directories and managing files.

### Listing Files and Directories

`Get-ChildItem` is similar to `dir` in Windows Command Prompt and `ls` in Unix-like systems.

```powershell
Get-ChildItem
```

A specific path can be provided:

```powershell
Get-ChildItem -Path C:\Users
```

### Changing Directories

`Set-Location` changes the current working directory.

```powershell
Set-Location -Path .\Documents
```

### Creating Files and Directories

`New-Item` can create both files and directories.

Create a directory:

```powershell
New-Item -Path .\captain-cabin\captain-wardrobe -ItemType Directory
```

Create a file:

```powershell
New-Item -Path .\captain-cabin\captain-wardrobe\captain-boots.txt -ItemType File
```

### Removing Items

`Remove-Item` can remove both files and directories.

```powershell
Remove-Item -Path .\captain-cabin\captain-wardrobe\captain-boots.txt
```

### Copying and Moving Items

`Copy-Item` is used to copy files and directories.

```powershell
Copy-Item -Path .\captain-cabin\captain-hat.txt -Destination .\captain-cabin\captain-hat2.txt
```

`Move-Item` is used to move files and directories.

### Reading File Contents

`Get-Content` displays the contents of a file.

```powershell
Get-Content -Path .\captain-hat.txt
```

It is similar to the `type` command in Windows Command Prompt and `cat` in Unix-like systems.

### Questions

What cmdlet can you use instead of the traditional Windows command `type`?

```text
Get-Content
```

What PowerShell command would you use to display the content of the `C:\Users` directory?

```powershell
Get-ChildItem -Path C:\Users
```

How many items are displayed by the command described in the previous question?

```text
4
```

## Task 5: Piping, Filtering, and Sorting Data

PowerShell supports piping using the `|` symbol.

Unlike traditional shells that mainly pipe text, PowerShell pipes objects. These objects contain data as well as properties and methods.

For example:

```powershell
Get-ChildItem | Sort-Object Length
```

This retrieves items and sorts them according to their `Length` property.

### Filtering Objects

`Where-Object` can be used to filter objects based on specific conditions.

Example:

```powershell
Get-ChildItem | Where-Object -Property Extension -eq .txt
```

Common comparison operators include:

```text
-eq  Equal to
-ne  Not equal to
-gt  Greater than
-ge  Greater than or equal to
-lt  Less than
-le  Less than or equal to
```

The `-like` operator can be used to match patterns.

```powershell
Get-ChildItem | Where-Object -Property Name -like ship*
```

### Selecting Properties

`Select-Object` can be used to select specific properties.

```powershell
Get-ChildItem | Select-Object Name,Length
```

It can also limit the number of objects returned.

For example:

```powershell
Get-ChildItem | Sort-Object Length -Descending | Select-Object -First 1
```

This retrieves the largest item.

### Searching File Contents

`Select-String` searches for specific text patterns inside files.

```powershell
Select-String -Path .\captain-hat.txt -Pattern hat
```

It can also work with regular expressions.

### Question

How would you retrieve the items in the current directory with size greater than 100?

```powershell
Get-ChildItem | Where-Object -Property Length -gt 100
```

## Task 6: System and Network Information

PowerShell provides several cmdlets for gathering system and network information.

### System Information

`Get-ComputerInfo` retrieves detailed information about the system, including operating system, hardware, and BIOS information.

```powershell
Get-ComputerInfo
```

### Local Users

`Get-LocalUser` lists local user accounts.

```powershell
Get-LocalUser
```

The lab contained an additional enabled account:

```text
p1r4t3
```

Its account description contained the motto:

```text
A merry life and a short one.
```

The user also had a home directory under:

```text
C:\Users\p1r4t3
```

Inside the hidden treasure directory, the treasure file was found.

### Network Configuration

`Get-NetIPConfiguration` retrieves network interface configuration, including IP addresses, DNS servers, and gateways.

```powershell
Get-NetIPConfiguration
```

`Get-NetIPAddress` provides information about IP addresses configured on the system.

```powershell
Get-NetIPAddress
```

### Questions

Other than the current user and the default `Administrator` account, what other user is enabled on the lab machine?

```text
p1r4t3
```

What is the motto in the user's account description?

```text
A merry life and a short one.
```

The treasure itself is intentionally not included in this writeup.

## Task 7: Real-Time System Analysis

PowerShell can also be used to gather information about running processes, services, network connections, and file integrity.

### Processes

`Get-Process` displays currently running processes.

```powershell
Get-Process
```

### Services

`Get-Service` displays installed services and their current status.

```powershell
Get-Service
```

This can be useful when investigating suspicious or modified services.

### TCP Connections

`Get-NetTCPConnection` displays current TCP connections.

```powershell
Get-NetTCPConnection
```

The `OwningProcess` property identifies the process associated with a connection.

### File Hashes

`Get-FileHash` can be used to calculate a file hash.

```powershell
Get-FileHash -Path .\big-treasure.txt
```

The SHA256 hash of the treasure file was:

```text
71FC5EC11C2497A32F8F08E61399687D90ABE6E204D2964DF589543A613F3E08
```

### Alternate Data Streams

PowerShell can also be used to inspect Alternate Data Streams (ADS).

```powershell
Get-Item -Path C:\House\house_log.txt -Stream *
```

The default `:$DATA` stream contains the normal file contents, while additional streams can contain hidden data.

### Service Investigation

The suspicious user modified the `DisplayName` of a service to match their account motto.

The service name found during the investigation was:

```text
p1r4t3-s-compass
```

### Questions

What is the hash of the file that contains the treasure?

```text
71FC5EC11C2497A32F8F08E61399687D90ABE6E204D2964DF589543A613F3E08
```

What property retrieved by default by `Get-NetTCPConnection` contains information about the process that started the connection?

```text
OwningProcess
```

What is the service name?

```text
p1r4t3-s-compass
```

## Task 8: Scripting

PowerShell scripting allows multiple commands to be written into a script and executed automatically.

Scripting can help automate tasks such as:

* Log analysis
* Anomaly detection
* Extracting indicators of compromise
* System enumeration
* Remote command execution
* Integrity checks
* System configuration
* Security monitoring

PowerShell is useful for both defensive and offensive security operations.

### Invoke-Command

`Invoke-Command` can execute commands on local or remote computers.

For example:

```powershell
Invoke-Command -ComputerName Server01 -ScriptBlock { Get-Culture }
```

It can also execute a script located on the local machine:

```powershell
Invoke-Command -FilePath c:\scripts\test.ps1 -ComputerName Server01
```

### Question

What is the syntax to execute the command `Get-Service` on a remote computer named `RoyalFortune`?

```powershell
Invoke-Command -ComputerName RoyalFortune -ScriptBlock { Get-Service }
```

## Task 9: Conclusion

This room introduced the fundamentals of PowerShell and demonstrated how it can be used for system administration and cybersecurity tasks.

Topics covered included:

* PowerShell fundamentals
* Cmdlets and the Verb-Noun convention
* File system navigation
* File management
* Piping
* Filtering and sorting objects
* System information gathering
* Local user enumeration
* Network configuration
* Process and service enumeration
* TCP connection analysis
* File hashing
* Alternate Data Streams
* PowerShell scripting
* Remote command execution with `Invoke-Command`

PowerShell is an important tool for cybersecurity because it provides extensive access to Windows systems and can automate both defensive and offensive security tasks.

## What I Learned

* PowerShell works with objects rather than only text.
* Cmdlets generally follow a Verb-Noun naming convention.
* `Get-ChildItem` can be used to navigate and enumerate the file system.
* `Get-Content` can read file contents.
* The pipeline allows objects to be passed between commands.
* `Where-Object` can filter objects based on their properties.
* `Sort-Object` can sort objects by their properties.
* `Select-Object` can select specific properties or limit results.
* `Get-Process` and `Get-Service` are useful for system analysis.
* `Get-NetTCPConnection` can reveal active network connections and their owning processes.
* `Get-FileHash` can be used to verify file integrity.
* `Invoke-Command` allows commands to be executed on remote systems.
* PowerShell scripting is highly useful for cybersecurity automation and system analysis.
