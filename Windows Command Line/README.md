# Windows Command Line

TryHackMe room: Windows Command Line

## Introduction

This room introduces the Windows command line and the `cmd.exe` command interpreter.

The command line is useful for system administration, troubleshooting, file management, process management, and remote system access.

Some advantages of using the command line include:

* Lower resource usage compared to graphical interfaces
* Automation of repetitive tasks
* Remote system management
* Faster access to certain system functions

## Task 1: Introduction

The default command line interpreter in the Windows environment is:

```text
cmd.exe
```

The room also demonstrates how to connect to a Windows machine remotely using SSH.

## Task 2: Basic System Information

Several commands can be used to obtain information about a Windows system.

### `set`

Displays environment variables, including the `Path` variable.

```cmd
set
```

### `ver`

Displays the Windows version.

```cmd
ver
```

### `systeminfo`

Displays detailed information about the operating system and computer.

```cmd
systeminfo
```

### `driverquery`

Displays installed device drivers.

```cmd
driverquery
```

The `more` command can be used to display long output page by page:

```cmd
driverquery | more
```

### `help`

Displays help information for commands.

```cmd
help
```

### `cls`

Clears the command prompt screen.

```cmd
cls
```

### Answers

What is the OS version?

```text
10.0.20348.2655
```

What is the hostname of the machine?

```text
WINSRV2022-CORE
```

## Task 3: Network Troubleshooting

Windows provides several command line tools for checking and troubleshooting network configurations.

### `ipconfig`

Displays basic network configuration information.

```cmd
ipconfig
```

For more detailed information:

```cmd
ipconfig /all
```

This can display information such as:

* IP address
* MAC address
* DHCP configuration
* DNS configuration

### `ping`

Tests whether a target can be reached over the network.

```cmd
ping target_name
```

### `tracert`

Displays the route taken to reach a destination.

```cmd
tracert target_name
```

### `nslookup`

Queries DNS information.

```cmd
nslookup example.com
```

A specific DNS server can also be used:

```cmd
nslookup example.com 1.1.1.1
```

### `netstat`

Displays current network connections and listening ports.

```cmd
netstat
```

The `-abon` options provide additional information:

```cmd
netstat -abon
```

The options mean:

* `-a`: Displays all connections and listening ports
* `-b`: Displays the executable involved in creating each connection
* `-o`: Displays the process ID
* `-n`: Displays addresses and ports numerically

### Answers

Which command can be used to look up the server's physical address (MAC address)?

```text
ipconfig /all
```

What is the name of the service listening on port 135?

```text
RpcSs
```

What is the name of the service listening on port 3389?

```text
TermService
```

## Task 4: File and Disk Management

The Windows command line can also be used to navigate directories and manage files.

### `cd`

Displays the current directory when used without parameters.

```cmd
cd
```

It can also be used to change directories:

```cmd
cd target_directory
```

To move up one directory:

```cmd
cd ..
```

### `dir`

Lists files and directories in the current location.

```cmd
dir
```

Hidden and system files can also be displayed:

```cmd
dir /a
```

To search through the current directory and its subdirectories:

```cmd
dir /s
```

### `tree`

Displays directories and subdirectories in a tree structure.

```cmd
tree
```

### `mkdir`

Creates a new directory.

```cmd
mkdir directory_name
```

### `rmdir`

Removes a directory.

```cmd
rmdir directory_name
```

### `type`

Displays the contents of a text file.

```cmd
type file.txt
```

### `more`

Displays long text files one page at a time.

```cmd
more file.txt
```

### `copy`

Copies files to another location.

```cmd
copy file.txt C:\Destination
```

Wildcards can be used to copy multiple files:

```cmd
copy *.md C:\Markdown
```

### `move`

Moves a file to another location.

```cmd
move file.txt C:\Destination
```

### `del` or `erase`

Deletes files.

```cmd
del file.txt
```

or:

```cmd
erase file.txt
```

The task also included a file located at:

```text
C:\Treasure\Hunt\flag.txt
```

The file contents were retrieved using:

```cmd
type C:\Treasure\Hunt\flag.txt
```

The flag itself is intentionally not included in this writeup.

## Task 5: Task and Process Management

Windows processes can be managed from the command line using `tasklist` and `taskkill`.

### `tasklist`

Lists currently running processes.

```cmd
tasklist
```

The output can be filtered to find a specific process.

For example:

```cmd
tasklist /FI "imagename eq sshd.exe"
```

This searches for processes with the image name `sshd.exe`.

The `/FI` option is used to specify a filter.

### `taskkill`

Terminates a running process using its process ID (PID).

For example:

```cmd
taskkill /PID 4567
```

### Answers

What command would you use to find the running processes related to `notepad.exe`?

```cmd
tasklist /FI "imagename eq notepad.exe"
```

What command can you use to kill the process with PID `1516`?

```cmd
taskkill /PID 1516
```

## Task 6: Conclusion

The room covered practical Windows command line commands for system information, networking, file management, and process management.

Some additional useful commands include:

### `chkdsk`

Checks the file system and disk volumes for errors and bad sectors.

```cmd
chkdsk
```

### `driverquery`

Displays installed device drivers.

```cmd
driverquery
```

### `sfc /scannow`

Scans Windows system files for corruption and attempts to repair them.

```cmd
sfc /scannow
```

The `/?' option can be used with most commands to display their help page.

The `more` command can be used in two useful ways:

```cmd
more file.txt
```

This displays a text file page by page.

It can also be used with a pipe:

```cmd
some_command | more
```

This allows long command output to be viewed one page at a time.

### Answers

What command can be used to restart a system?

```cmd
shutdown /r
```

What command can be used to abort a scheduled system shutdown?

```cmd
shutdown /a
```

## What I Learned

In this room, I learned how to use the Windows command line for basic system administration and troubleshooting.

I practiced commands for:

* Viewing system information
* Checking network configuration
* Troubleshooting network connections
* Managing files and directories
* Viewing file contents
* Managing running processes
* Terminating processes
* Restarting and shutting down Windows systems
* Using command help and filtering command output

This room helped me become more comfortable working with Windows systems through the command line instead of relying only on graphical tools.
