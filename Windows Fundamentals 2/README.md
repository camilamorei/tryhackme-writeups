# Windows Fundamentals 2

This room covers several Windows administration and configuration tools that can be accessed through the System Configuration (MSConfig) panel.

## Topics Covered

* System Configuration
* Advanced System Settings
* User Account Control (UAC)
* Computer Management
* System Information
* Resource Monitor
* Command Prompt
* Registry Editor

## System Configuration

MSConfig is a Windows utility used to manage system configuration and access different administrative tools.

### Useful Commands

| Tool                          | Command                          |
| ----------------------------- | -------------------------------- |
| System Configuration          | `msconfig.exe`                   |
| Control Panel                 | `control.exe`                    |
| Computer Management           | `compmgmt.msc`                   |
| System Information            | `msinfo32.exe`                   |
| Resource Monitor              | `resmon.exe`                     |
| Registry Editor               | `regedt32.exe`                   |
| User Account Control Settings | `UserAccountControlSettings.exe` |

## Advanced System Settings

The Advanced System Settings section provides access to different system configuration options, including environment variables and performance settings.

The Windows license in this system was registered to:

```text
Windows User
```

The system name was:

```text
THM-WINFUN2
```

The `ComSpec` environment variable was:

```text
%SystemRoot%\system32\cmd.exe
```

## Computer Management

Computer Management provides access to several administrative tools, including:

* Task Scheduler
* Event Viewer
* Shared Folders
* Local Users and Groups
* Device Manager
* Disk Management

A hidden shared folder found in the lab was:

```text
sh4r3dF0Ld3r
```

The `npcapwatchdog` scheduled task was configured to run:

```text
At system startup
```

## Command Prompt

The System Configuration entry for Internet Protocol Configuration uses:

```text
C:\Windows\System32\cmd.exe /k %windir%\system32\ipconfig.exe
```

To display detailed network configuration information with `ipconfig`:

```cmd
ipconfig /all
```

## Registry Editor

The Windows Registry is a hierarchical database that stores configuration information used by Windows, applications, users, and hardware.

The Registry Editor can be opened with:

```text
regedt32.exe
```

Registry changes should be made carefully because incorrect modifications can affect normal Windows operation.

## Key Takeaways

This room showed that many Windows administrative utilities can be launched directly using commands instead of opening MSConfig first.

Some useful commands from the room include:

```text
msconfig.exe
control.exe
compmgmt.msc
msinfo32.exe
resmon.exe
UserAccountControlSettings.exe
regedt32.exe
```

Learning these commands makes it faster to navigate and troubleshoot Windows systems.
