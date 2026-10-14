# TryHackMe - Metasploit: Introduction

**Room:** [Metasploit: Introduction](https://tryhackme.com/room/metasploitintro)  
**Category:** Exploitation  
**Topics:** Metasploit Framework, Modules, Payloads, Msfconsole, Module Options, Sessions

---

## Task 1 - Introduction

This room introduces the Metasploit Framework, a penetration testing platform used to find and exploit vulnerabilities in authorized lab environments.

Metasploit organizes functionality into modules. The main module types introduced in this room include:

- Exploit modules, which attempt to exploit vulnerabilities.
- Auxiliary modules, which perform supporting tasks such as scanning.
- Payloads, which provide code or functionality to run on a target after successful exploitation.
- Post-exploitation modules, which are used after access has been obtained.

## Task 2 - What is Metasploit?

Metasploit provides modules for different stages of a penetration test. A typical workflow is to find an appropriate module, configure it for the target, and run it.

The `msfconsole` interface is used to search for modules, select them, configure options, and execute them.

### Searching for Modules

Use `search` followed by a keyword to find relevant modules:

```text
search apache
```

### Staged and Single Payloads

Payloads can be staged or single:

- Staged payloads are delivered in multiple parts. A small initial payload connects back and then receives the remaining stage.
- Single payloads contain the functionality in one payload.

The room's example `windows/x64/pingback_reverse_tcp` is categorized as a single payload.

## Task 3 - Msfconsole

`msfconsole` is the primary command-line interface for Metasploit. Commands are entered at the Metasploit prompt.

To select a module, use:

```text
use auxiliary/scanner/ssh/ssh_login
```

The prompt changes to show the selected module's context. The provider listed for `auxiliary/scanner/ssh/ssh_login` in the room is `todb`.

## Task 4 - Working with Modules

### Selecting a Module and Viewing Options

Select a module with `use` and inspect its parameters with:

```text
show options
```

A module may require parameters before it can run. Always review the options and confirm that the values match the authorized lab target.

### Common Options

| Option | Meaning |
| --- | --- |
| `RHOSTS` | Remote target host or hosts |
| `RPORT` | Port of the service on the target |
| `PAYLOAD` | Payload selected for an exploit |
| `LHOST` | Local address used for a reverse connection |
| `LPORT` | Local port used for a reverse connection |
| `SESSION` | Existing session identifier used by some modules |

### Setting and Clearing Options

Set a value for the current module:

```text
set LPORT 6666
```

Set a global value that can be reused by other modules:

```text
setg RHOSTS 10.10.19.23
```

Remove a specific option:

```text
unset PAYLOAD
```

Clear all options for the current module context:

```text
unset all
```

Remove a global setting:

```text
unsetg RHOSTS
```

### Running a Module

The commands `exploit` and `run` can execute a module. `exploit -z` attempts to run an exploit and backgrounds a session if one opens.

Some modules support a `check` command to test whether a target appears vulnerable without actually exploiting it.

### Navigating Contexts and Managing Sessions

Use `back` to leave the current module context and return to the main Metasploit prompt.

A session is a communication channel established with a target after a successful operation. Useful session commands include:

```text
sessions
sessions -i 2
```

The first lists active sessions; the second interacts with session ID 2. The ID will depend on the sessions created in the lab.

Use `background` or `Ctrl+Z` to put an interactive session in the background.

## Task 5 - Summary

The room summarizes the basic exploitation workflow:

1. Find an appropriate exploit.
2. Configure it for the target.
3. Run it against the vulnerable service in the authorized lab.

The room also recommends trying the `ms17_010_eternalblue` exploit against the attached target VM as a practical exercise.

## Key Takeaways

- Use `search` to find modules.
- Use `use` to select a module.
- Use `show options` to review required and optional parameters.
- Use `set` for module-specific values and `setg` for global values.
- Use `unset` and `unsetg` to clear module-specific and global settings.
- Use `exploit` or `run` to execute a module.
- Use `sessions` to list and interact with sessions.

All commands and exploitation exercises should be performed only in authorized environments, such as the TryHackMe lab.
